# Ember performance improvements

In this collection you will learn tips and tricks on making your Ember apps faster, accessible and perfectly awesome!

## Introduction

### What is Ember?

Ember is an ambitious web framework for ambitious web developers. It is free, opensource and always will be. Here’s a [quickstart to learning Ember](https://emberjs.com/learn). In order to get used to this collection, you should be already familiar with Ember and the ecosystem.

### The ecosystem:

#### 1. [Ember CLI](https://ember-cli.com/):
Ember CLI is the official command line toolkit for developing Ember apps. It is a powerful CLI that comes in baked in with loads of options and configs to choose from. Whether you are building an app or an addon, ember-cli is the first and foremost toolkit you would need.

#### 2. Ember Inspector:
It is a browser extension that helps inspect Ember apps available in both Chrome and Firefox.

1. [Chrome](https://chrome.google.com/webstore/detail/ember-inspector/bmdblncegkenkacieihfhpjfppoconhi)
2. [Firefox](https://addons.mozilla.org/en-US/firefox/addon/ember-inspector/)

If you are looking to debug ember apps with ease, this is the go-to tool that helps inspect components, routes, data, promises, etc.

#### 3. [Ember twiddle](https://ember-twiddle.com/):
Like JSFiddle, JSBin, etc, ember twiddle is the playground for trying out and experimenting with Ember code on the browser. It helps quickly share ember snippets as github gists.

#### 4. [Ember Engines](https://ember-engines.com/):
As stated by the ember-engines website, ember-engine is an addon that allows multiple logical units of Ember apps to be composed together into a single app from the user’s perspective. If your ember application is constructed of multiple logical units that don't possibly inter-depend on each other, then you should start giving ember-engines a try. Here's another [blog that I wrote](/ember-engines-part-1).

#### 5. [Fastboot](https://ember-fastboot.com/) and [Prember](https://github.com/ef4/prember):
Server-side rendering (SSR) is popular technique that helps to render client-side only single page apps (SPA) on the server. It then sends a fully rendered page to the client as HTML markup. The biggest advantage or benefit of using SSR is having search engines like google or bing's robot crawl the app for its content. Single page applications don't serve content while depend on Javascript to render the content dynamically. On the other hand, crawlers don’t execute JavaScript code. In order to bridge the gap, SSR techniques are introduced where search engine robots can crawl content of your apps. This can help with SEO and with providing meta data to social media channels. In ember world, this is achieved through [Fastboot](https://ember-fastboot.com/) and [Prember](https://github.com/ef4/prember).

#### 6. [Liquid fire](https://ember-animation.github.io/liquid-fire/):
This is the animation toolkit for Ember apps. If you are using Ember 3.8 and above, you can also check out to [ember-animated](https://github.com/ember-animation/ember-animated).

#### 7. [Ember observer](https://emberobserver.com/):
Building ember apps are easier as a lot of smaller units, also called addons, are readily available. ember-observer is the marketplace for ember addons but available free of cost. This is by the community. If you build an addon that you think does not exist in the ember ecosystem yet, feel free to create one. Pro-tip: Make sure you have [ember-cli-addon-docs](https://ember-learn.github.io/ember-cli-addon-docs/) to add documentation to your addon for emberoberserver to crawl your addon and add a rating to it.

### Understanding working on Performance for Ember apps

Key areas to optimize Ember apps:

1. Improving on build size.
2. Improving assets cache.
3. Building and optimising your Ember app for SEO.
4. Improving accessibility of your Ember apps.
5. Making your Ember apps installable.
6. Improving your Ember build timelines.

### Building a sample app:

1. To install ember-cli globally, run `npm i -g ember-cli`. To ensure ember-cli is installed, run the command `ember -v`. I'm on version 3.18.0-beta.1 and this is what I see and you should also see something like this:

```
ember-cli: 3.18.0-beta.1
```
This confirms that ember-cli is installed in your machine globally.

2. To create a new ember app, run `ember new <application-name>`. This should create the folder in your application name and add a boilerplate codebase with a minimal folder structure. It would also install the npm packages it needs.

You would be displayed with a boilerplate files and folder structure of what would be created under your new application path and it should display something like this:

```
$ cd sample-app-2
$ npm start
```

3. As the instructions mentions, let's do `cd <application-name>` and say `npm start`.

```
Build successful (5300ms) – Serving on http://localhost:4200/
...
```

4. You should now be able to access your application at [http://localhost:4200](http://localhost:4200/).

### Getting started with Performance optimisations

Here're the topics that will be covered in this series:

1. [Improving speed](Ember%20performance%20improvements/Speed.md)
2. [Caching assets using Service workers](Ember%20performance%20improvements/Caching%20assets%20using%20Service%20workers.md)
3. [SEO friendly pages](Ember%20performance%20improvements/SEO%20friendly%20pages.md)
4. [Improving Accessibility](Ember%20performance%20improvements/Improving%20Accessibility.md)
5. [Creating installable Ember apps](Ember%20performance%20improvements/Creating%20installable%20Ember%20apps.md)
