---
layout:     post
title:      "My take on Frontend Libraries/Frameworks"
subtitle:   "What to choose"
date:       2020-06-01 10:00:00
author:     "Luís Duarte"
---

Being a Fullstack Developer makes me to research and keep up with Tech Trends in order to keep myself up-to-date.

I've seen a lot of buzz and a lot of posts with titles "React is better than Angular", "Angular is better than React", "Vue is better than React and Angular".

I'm not going to get into the game and say which one is better. All of them have Pros and Cons, you just need to choose wisely and leave your personal "religion" aside.

# Framework vs Library
First of, let me remind you all when you're comparing Vue or React with Angular, you're comparing two totally different things, the first two are Libraries and the latter one is a Framework.
The way I see this is through this scenario: 

Let's imagine a Car. React and Vue (Libraries) are the Engine, which means, you need to pick a Chassis, a Car glass, Tyres, Rims, Muffler, etc.... and Angular (Framework) is like going to a Car Dealer and just buying a Car, they'll just give you a key and you start driving it. But you can still change the Tyres to better ones, get more efficient Rims, get a better Engine.

Vue's value proposition is it's size and it's simple nature. Ok... good selling point, but makes no sense in comparing Vue with Angular. Vue is only one small part of a bigger piece of engineering. Even if you choose Vue, you're going to need Routing, probably some sort of Redux Framework, you'll also probably want Typescript, Themes, etc... (I'm not saying Vue doesn't come with some of these features), but in the end, after you finish building "your car", you'll probably endup with a similar size as Angular, Angular just makes most of those decisions for you.

# What should i choose?
You should choose what's best for your reality. I know this looks ambiguous, but for example, I've previously worked in a Startup Studio where we chose Angular for all of our Frontend Development. The key factors that we've considered were the following:
 - It must have active support (Google in this case)
 - It must have good community support (there's lots of plugins)
 - It must have Typescript
 - It must not need extra libraries for it to work like an SPA.
 - It must have separate files for HTML, CSS and Component Code
In our case, our UX/UI Specialist could concurrently work with the Frontend Engineers in the HTML+CSS (SCSS in our case) while the latter would develop the Component functionality. And it worked like a charm for us.

# Don't be religious
Angular has an HTML-Centric Approach, which it made sense for our use-case, but if you want to go on a Full JS-Centric Approach, i suggest you go React. But the setup will take more time, and most of the components you chose will be community supported (This is a risk, trust me), because the maintainers may at any step decide not to continue develop anymore and you'll eventually need to switch.
Vue is a Hybrid of Angular and React but uses some kind of HTML-Centric approach with a custom HTML5 Schema with inline code. Think of it more similar to Polymer Project.

# Bottom line
I'll just give you my opinion straight away. If you have an MVP/Startup and just want to get things started, up and running with good scaling without worrying about what libraries and parsers to chose, you should go Angular. Why? Because Angular Core components (with everything you need) are fully and actively supported by Google and since you just want to focus on Business Case without worrying too much about underlying stuff. Remember the Car analogy? You just want to start the Engine and start driving (Business Case).
You may see more React community libraries on Npm, but Angular has pretty decent support for the major ones, so don't worry about that.
