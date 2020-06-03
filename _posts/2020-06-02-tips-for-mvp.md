---
layout:     post
title:      "Getting started with your MVP"
subtitle:   "From Zero to Production"
date:       2020-06-02 10:00:00
author:     "Luís Duarte"
---

# Preamble
This article assumes that you're a Technical person like me. And shows you my view from a Tech Lead perspective of a Software Product/MVP.

# Main Article

In the past 4 years, i’ve been working on several different Startups on every product stage and i managed to form an opinion on how to quickly build an MVP (Minimum Viable Product).

Before building a Product MVP there’s one thing to have in consideration:

> Will someone actually pay for this?

I know i’m being very cold regarding monetization, but the bottom line is this, either people pay for the product or you have no product. 

Now, before creating an MVP you need to make a small Pitch on what problem are you trying to solve and the most important part, Target Audience. Let’s face it, there’s a big chance that there are at least 2 or 3 products trying to solve the same problem but with a different approach and audience, so be as opinionated as you can, and be pushy on that. If you’re just copying the others, you don’t have differentiation.

Your Product must bring value. e.g.: If you're charging 10 EUR/month/user, the customer needs to at least transform those 10 EUR/month/user into an income of 15/20 EUR/month/user.

# Build a Prototype
So, assuming that you’ve spoken to a couple of people, they are willing to pay for your product and you see a market fit, let’s discuss the Technical Part.

## Tech Stack
Be very careful with the Tech Stack you chose. I will not say that Python or Ruby or Go or Java or C is better, you should not be religious when it comes to this. My top criteria for chosing a Tech Stack is available Talent in your area. I’ve recently worked in a Startup Studio that has chosen Python/Django for all Backend development due to the Data Engineering Libraries available, which is a fair point, but this is what i all “Premature Optimization”, since they were thinking way ahead of the Product Journey. You only start to worry about Data Warehouse and Analytics when you have a well established Product and a couple of successful Funding Rounds. We ended up having lots of problems hiring Talent to help us develop the Product, because where we were based (Lisbon) there’s not many Experienced Python Developers available and the ones that are, are over your Salary Budget, we've tried to have the 1 Senior + 1 or 2 Intermediate + Juniors approach. We either got very Senior or very Junior.

```
Lesson #1: Check out LinkedIn, talk to your friends, former colleagues/managers and try to get a sense of what Tech Stacks are used across Local Companies. DON’T BE RELIGIOUS!
```

Regarding the choice for using Python, this is what i call “Premature Optimization”, since in terms of strategy we were thinking way ahead of the current step in the Product Journey. You should only start to worry about Data Warehouse and Analytics when you have a well established Product and a couple of successful Funding Rounds.

```
Lesson #2: Keep your feet on the Ground, don’t start flying until you have an Airplane ready. Premature Optimization will kill your Product.
```

Next Criteria would be to carefully analyze which Frameworks are you going to use. For example, i’ve developed 2 MVP’s using Kotlin + Spring Boot (JVM). Spring Ecosystem brings a whole lot of value out-of-the-box, you can very easily create an REST API + ORM (Hibernate).
As a side note, there’s been a lot of buzz regarding ORM’s, especially Hibernate. Best advice i can give you about that is Don’t try to develop your own Framework, **YOU WANT TO FOCUS ON YOUR BUSINESS LOGIC**. Remember, The Business Case is what will bring you money, not Tech Stack, so again. **DON’T BE RELIGIOUS**.

```
Lesson #3: Focus on your Business Logic, not technicalities.
```

Try to chose a well maintained Framework. Go to Github, check the Commit History, check the released versions, assess the average time to close PR’s + Issues. Also and very important, check for community support and plugins.

```
Lesson #4: Choose a well maintained Framework (e.g.: Hibernate, Spring Boot, Django, SQLAlchemy, Ruby On Rails, etc….). Don’t try reinvent the wheel.
```

One final advice on this, and try to take this very seriously, don’t try to hack around a Framework. The moment you do that, that Framework no longer fits your purpose.

If you for some reason "Reinvent the wheel", don't forget you'll probably endup with a Framework that **YOU** need to support and only **YOU** will use, and this diverts efforts from focusing on your Business Case (Unless your Business Case is a Framework) and you'll just be wasting time, brain cells and resources.

Another thing to have into consideration is to have an Identity Provider (IdP), this is the basis of your product. I recommend that you use a 3rd Party provider for starter (Auth0, Okta, etc…) or Host your own with pre-build solutions (Keycloak, Ory Kratos, etc….).


### Frontend Frameworks
Regarding Frontend Frameworks you can read my [previously written article]({{ site.baseurl }}{% link _posts/2020-06-01-frontend-frameworks.md %}) on my opinion about the most trending Frontend Frameworks available.

## Hosting your product
If you’re just still showing off to a small circle of users, i recommend that you just use a 5 USD Machine from Digital Ocean or AWS EC2 small instance, it provides you with everything you need.

# Growing your product
Ok, assuming that in this Product Journey you now have an established product (even if it's just a couple of users), now you need to scale it.

## Billing Provider
First thing you’ll need is to use a Billing Provider, i recommend Stripe, they charge a fixed percentage on each transaction but they give you a Payment Gateway and all necessary banking compliances out-of-the-box, so that percentage is worth every cent, trust me on that. Again, focus on your Business Case.

## Hosting your product
By reading all kinds of articles around you'll most likely be very tempted to chose Kubernetes as host for your App. My advice is, DON'T do this yet.
Go for AWS ECS, Google App Engine, Digital Ocean Droplets, etc... . For now (assuming that you'll only have one or two backend services) you just want a place to run the Production/Dev containers.

### Provider
Google, Amazon, Digital Ocean, Openshift, Azure. Personally, i prefer Google's simplicity on their Cloud Offering, but AWS offers a much broader and complete toolset, but way more complex than Google's. You just try them out, choose one and go with it. This part i leave it up to you.

## Feature Flags
Every feature that you develop, ensure that you have a Feature Flag for the end-user, you want to do phased release for your features, like a Beta Program. Use that “small circle” of customers that you have to test your new features before making them GA (General Availability). You don't want "Oops..." moments on this, when you're still in very early stages, the worst thing you can have is a customer to Rage Quit.

## Iterating your product
I recommend that you publish your app on AppSumo[https://appsumo.com/] and offer a couple of Voucher discounts to get you started. For now you just need to get your product out there, even if you give 80% off discounts, you need to start iterating on your product and improving it. Without users using it, you can’t collect data, and without data, you can’t improve.

## Security
This is the most important part for me. Your company having Customer Data is almost the same as a Bank having Customer Money. The Customer trusts the Bank to hold their money safely. The moment the Bank starts to have suspicious activity (in the Press, in the Regulators, by the Government, etc...), Customer will most likely no longer trust the Bank and will withdraw all money from there, ending the relationship. Same thing will happen with Customer Data.

Couple of years ago i gave a talk about HashiCorp’s Vault product, which is basically a Secrets Management Service. I highly recommend that you have a Secret Management Tool for your Services (Most providers have a Managed Version).

Here’s a simple use case: An employee leaves the company and you’ll have to renew all of the Secrets, update all configurations and redeploy all your services. With Vault you can do this with a simple command, no need for redeployment.

Also, ensure that your Backoffice and Internal Infrastructure is behind a VPN.



I wrote this article to show what i have learned from my previous work experience and to show you some insights on everything to consider before starting a MVP/Company.