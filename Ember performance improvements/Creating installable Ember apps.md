# Creating installable Ember apps

To make your Ember app installable, there is yet another simple addon called `[ember-web-app](https://zonkyio.github.io/ember-web-app/)`. So let's go ahead and create a new ember app and add this addon.

    ember new ember-app
    
    ember install ember-web-app

The second command should have installed ember-web-app addon and added config/manifest.js file. You would also see your index.html file modified with these lines

![Creating%20installable%20Ember%20apps/Untitled.png](Creating%20installable%20Ember%20apps/Untitled.png)

Navigate to `config/manifest.js` and you should see a predefined set of values prefilled something like below:

![Creating%20installable%20Ember%20apps/Untitled%201.png](Creating%20installable%20Ember%20apps/Untitled%201.png)

For a list of properties you can use, [check this out](https://zonkyio.github.io/ember-web-app/docs/manifest/available-properties).

Let's run PWA on Lighthouse and see the results. And the following is what you would see

![Creating%20installable%20Ember%20apps/Untitled%202.png](Creating%20installable%20Ember%20apps/Untitled%202.png)

## Let's fix the offline pointer.

This is pretty straightforward as stated in "Caching assets using service workers" segment.

    ember install ember-service-worker
    
    ember install ember-service-worker-asset-cache
    
    ember install ember-service-worker-index

Let's check Lighthouse measurements now and here's what you would see

![Creating%20installable%20Ember%20apps/Untitled%203.png](Creating%20installable%20Ember%20apps/Untitled%203.png)

## More fixes

1. In order to fix "Does not provide fallback content when JavaScript is not available", let's add and that should be green.

        <noscript>Some content here for your page without JavaScript</noscript>

2. To fix the PNG icon, you can just add an image in your config/manifest.js and it should be resolved. This is the config that I have added to the config/manifest.js. Make sure to replace the images with your Ember app's.
```
    'use strict';
    
    module.exports = function(/* environment, appConfig */) {
      // See https://zonkyio.github.io/ember-web-app for a list of
      // supported properties
    
      return {
        name: "ember-app",
        short_name: "ember-app",
        description: "",
        start_url: "/",
        display: "standalone",
        background_color: "#fff",
        theme_color: "#fff",
        icons: [{
          src: 'ember-welcome-page/images/construction.png',
          sizes: '192x192'
        }, {
          src: 'ember-welcome-page/images/construction.png',
          sizes: '280x280',
          targets: ['apple']
        }, {
          src: 'ember-welcome-page/images/construction.png',
          sizes: '512x512'
        }],
        ms: {
          tileColor: '#fff'
        }
      };
    }
```
Based on the above fixes you should have most green except for the HTTPS redirection.

![Creating%20installable%20Ember%20apps/Untitled%204.png](Creating%20installable%20Ember%20apps/Untitled%204.png)
