---
title: 'Using NPM to create a build that just works'
description: 'In recent years Javascript tooling has put the peddle to the floor. We’ve seen the emergence of package managers, and the growth (and decline) of numerous task runners —and then there’s Webpack…'
pubDate: 'Jul 01 2017'
location: 'London'
duration: '4 minute read'
---

In recent years Javascript tooling has put the peddle to the floor. We’ve seen the emergence of package managers, and the growth (and decline) of numerous task runners—and then there’s Webpack…

All this tooling felt like a luxury; I remember feeling excited to finally hack Grunt in to my first project. As library owners started creating wrappers for their tools Grunt grew in popularity and eventually had enough of an eco-system that made it a smart choice for large applications.

Then Gulp arrived on the scene and told us that Grunt just didn’t cut it. Streams were the next big thing and our builds just weren’t coherent without them. We gratefully obliged and jumped ship.

## A low point

I think the state of Javascript tooling, and task runners in particular, hit a low point around 2015. As a collective we were far from reaching consensus.

The tools that we’d grown reliant upon became out of date with their Grunt/Gulp counterparts. The problem first became obvious to me when the then latest version of [node-sass](https://github.com/sass/node-sass) lost version parity with it’s Gulp wrapper, it caused some headaches for a while.

## We've come a long way

Nowadays all of that is behind us. We seemed to have found our knight in shining armour in NPM.

It seemingly solves a lot of the frustrations that we felt with previous contenders. It’s lightweight, doesn’t require independently versioned library wrappers, and most conveniently it’s bundle with Node.

_I’m ignoring Yarn here. For the purposes of build tools, and task runners, Yarn and NPM are one in the same, feel free to pick your poison._

I first gave NPM a shot in 2016 and I’ve not looked back since. It definitely has some kinks and can be unsightly if you don’t employ basic principles, but hopefully I’ll outline some gems for you here.

The danger we need to avoid with NPM is script-overload, just take a look at [react-redux-universal-hot-example](https://github.com/erikras/react-redux-universal-hot-example/blob/master/package.json) if you want to know what I’m talking about. A project shouldn’t need 13 separate scripts to run efficiently in development and production, it’s unbearable for new developers trying to understand your application.

## Use environment configuration

Environment configuration to the rescue. Tools like [dotenv](https://github.com/motdotla/dotenv) can be life-savers here and can sometimes remove the need for separate development and production scripts all together.

Just remember that configuration should be environment based, if the values are static between development, staging, and production, it doesn’t belong here.

## No more scary scripts

Writing complex scripts embedded JSON, à la package.json, is never a great idea — they’re hard to read to say the least. A common approach to adopt is creating a separate scripts directory at the root of your project to house all of that automated goodness.

But remember, we’re Javascript developers not BASH developers. Most front end developers would have a hard time reading a BASH script let alone writing one. Using tools such as [shelljs](https://github.com/shelljs/shelljs) we can make these scripts seem oddly familiar.

## Command Line Interfaces

The beauty of all of this is that we’re no longer using wrappers for our tools. Why use gulp-webpack when I can just use webpack. The eco-system of command line tools, within NPM, is vast and always will be. We can be sure that it’s not going away anytime soon.

My only recommendation here is the be smart about the tools you choose to use. I find tools such [npms.io](https://npms.io/) helpful here.

## The future is bright

I’m pleasantly optimistic about the state of Javascript build tools and task runners these days. Huge open source projects such as [Angular](https://github.com/angular/angular) and [React](https://github.com/facebook/react) have adopted these principles, which is a rubber stamp as far as I’m concerned.

If you’re wondering what all of this looks like, here’s the package.json scripts object from one of my side projects:

```
"scripts": {
  "build": "node ./scripts/build",
  "dev": "node ./scripts/dev",
  "lint": "eslint . --ignore-path ./.gitignore",
  "start": "node ./scripts/start.js",
  "test": "jest"
},
```

As Node proliferates through our technology stack we can be confident that it’s doing so with some level of predictability.

_I encourage you to check out Yarn, or NPM bundled with Node v8.x.x. We’ve made leaps in terms of speed and substantial improvements on shrinkwrapping._
