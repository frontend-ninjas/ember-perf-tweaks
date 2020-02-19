# SEO friendly pages

SEO friendly pages would help optimize for search engine results ranking. While you create a new Ember app from ground-up, and run Lighthouse for validating it, you should see the score at 90.

![SEO%20friendly%20pages/Untitled.png](SEO%20friendly%20pages/Untitled.png)

The reason being:

1. Ember CLI's ember new command adds `<meta name="viewport">` tag with the required set of values.
2. The index.html file created has a proper `<title>` tag with your application's name.
3. `robots.txt` file is added by default to your `dist/` path. Once you host your app, it is ready for Search engines to start crawling.

However, if you have noticed, your page does not have:

1. a proper `lang` attribute on the `<html>` tag.
2. It does not contain a proper description in the `<meta name="description" content="">` tag. go ahead and add them both.

Once you have done these steps, you should see

![SEO%20friendly%20pages/Untitled%201.png](SEO%20friendly%20pages/Untitled%201.png)

When you start building big applications that need to be SEO friendly like blogs, you should have the document title to change based on the page your users visit. In order to get this up and running, you can use an addon called `ember-page-title`. To install this addon, just say:

    ember install ember-page-title

And then all you need to do is

    {{title "Ember app"}}

You should see this `<title>` tag in your DOM now.

![SEO%20friendly%20pages/Untitled%202.png](SEO%20friendly%20pages/Untitled%202.png)

## Server side rendering

SSR in Ember is achieved using [Fastboot](https://ember-fastboot.com/). This addon performs initial render in the server and makes your Ember apps accessible to Search Engines. Also, users see content faster which would be much more like your app worked without Javascript.

Fastboot uses Node in the background to execute your Ember apps within it. 

Before we install and run Fastboot for your ember app, here's what your page source would be for a bare minimal Ember app. Let's create a new ember app using:

    ember new ember-app

You can notice that the `<body>` tag only contains the 3 script tags

![SEO%20friendly%20pages/Untitled%203.png](SEO%20friendly%20pages/Untitled%203.png)

To get started with `ember-cli-fastboot` run the following command:

    ember install ember-cli-fastboot

This should install the addon and list it in your package.json file. To start your Fastboot server, you can still continue to use

    ember s

Now you should see the HTML content (doing a "View page source") being inlined as below for a sample app that we built

![SEO%20friendly%20pages/Untitled%204.png](SEO%20friendly%20pages/Untitled%204.png)

PS: The above DOM content is from the `<WelcomePage />` component that comes added into your `application.hbs` when you run the command `ember new sample-app`

### Pro tip:

You could also try [empress-blog](https://github.com/empress/empress-blog) if you want to build a blog engine.