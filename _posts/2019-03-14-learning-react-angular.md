---
layout: post
title: "My ongoing attempt to learn React and Angular: Part I"
date: 2019-03-14 14:00:00
image: '/assets/img/'
description: "Jumping into the world of full-stack development and a beginner's perspective on the React vs. Angular debate"
tags:
- angular
- react
- frontend
- vue
categories:
- Frontend development
twitter_text: 'My ongoing attempt to learn React and Angular: Part I'
---
**tl;dr: As someone with little to no JavaScript experience, React feels like the better frontend tool to get started with. But, if you choose one tool over the other and change your mind, it's not like you're starting over from nothing.**

I've never really had the time to sit down and dive into JavaScript--it's one of those languages I feel like you don't pick up until you need to learn it, and I've always tended to prefer writing backend code. I'm not sure I've ever met someone who *started out* with JavaScript as opposed to Python, Java, C, or almost anything else. That being said, It's hard to build really cool personal tools without at least some basic frontend proficiency, so I feel like now is a good time to dive in. And of course JavaScript is a super applicable skillset in 2019, especially with all its associated frameworks and libraries in widespread use (Node, Angular, React, Express, Vue) plus all the superset languages like CoffeeScript, TypeScript, etc. It seems like it's everywhere.

# Angular vs. React for frontend noobs?
The great challenge in learning a frontend framework/library of course, is finding where you stand on the constant Angular vs. React vs. (now as of 2017) Vue debate and choosing something to start with. Initially, I was drawn in by the scaffolding and quick onboarding process provided by Angular, and so it had been my tool of choice when working with web frontends for small school projects. I ended up using Angular in my first iteration of a web app I've recently been working on, [LyrAssist](https://www.lyrassist.com).

I recognize it's probably best to really understand vanilla JavaScript first before getting into using fancy tools, but I'm trying to gain solid functional knowledge rather than become a god of frontend development, and with that being the goal I definitely think its possible to learn both at the same time using some caution.

## Why I've started to like React
For someone **in my position** though, I've started to have a few issues with Angular:
* While the structure provided and enforced by *angular-cli* is really cool, and encourages good design principles and best practices suggested by [Google's Angular docs](https://angular.io/docs/), it tends to rob you of the learning experience that self-scaffolding/architecting a project provides. It feels kind of like using a calculator before you totally understand how to do long division yourself. React allows for much more design freedom (and opportunities to mess up and learn why not to do it that way, firsthand).
* For someone who doesn't already understand JavaScript really well, I've had some issues intuitively grasping TypeScript syntax. I don't know enough yet about the enhanced features TypeScript brings to the table to fully elaborate on this, but as I try to figure out how to do certain things in Angular it feels like a lot of things are being thrown at me at once, whereas since I've started tinkering with React, I can usually much more easily follow what is going on even though React uses its own JavaScript flavor called [JSX](https://jsx.github.io/).

These are definitely common tropes that have been said before, but I've definitely experienced them too. I think they are really important considerations for someone jumping into serious frontend development for the first time as I am right now. With apologies to Vue (it hasn't quite caught up in terms of its use across the industry yet, but maybe it will), I'm definitely preferring getting started with React.

I totally understand the value in increased rigidity and better scaffolding provided by Angular, especially on large collaborative projects where different developers may have their own ideas of design patterns and best practices. I haven't played with React's command-line scaffolding tool and angular-cli alternative [create-react-app](https://github.com/facebook/create-react-app) yet, but in reading the documentation and sample code it doesn't seem to be nearly as robust as angular-cli. I suspect that is by design; React is only a library and is lighter weight, while Angular is a full-blown framework.

I'm currently following an awesome course called [Learn React for free](https://scrimba.com/playlist/p7P5Hd) provided by Bob Ziroll on [Scrmba](https://scrimba.com), which I strongly recommend as well! Scrimba is great because video guides are interactive, allowing you to play with the project code sandbox in the middle of the video, as if you were pair programming with the instructor. Awesome. I'll be posting progress as I move through the course in the next few days/weeks!

One last thing: although I've just scratched the surface with each of these tools, I doubt that learning one will take you on a completely divergent learning path, so a lot of the skills you pick up will translate if you change your mind later.