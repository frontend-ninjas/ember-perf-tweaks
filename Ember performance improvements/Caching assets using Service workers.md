# Caching assets using Service workers

Service workers have magical powers. To know more, [read here](https://web.dev/service-workers-cache-storage/).

If you are building Ember apps for your users who would be accessing them from mobile networks, it could mean they have extremely slow network connections on the move. In order to load your apps faster, service workers could be an effective strategy. `ember-service-worker` is an Ember addon that takes care of service worker registrations, asset caching, etc.

To install `ember-service-worker` in your Ember apps, go ahead and perform the following command:

    ember install ember-service-worker

Doing the above, and starting your Ember app, you would see that your app has registered a service-worker.

![Caching%20assets%20using%20Service%20workers/Untitled.png](Caching%20assets%20using%20Service%20workers/Untitled.png)

Notice the `sw-registration.js` file? You should also notice the following message that says “Service worker registration succeeded”.

![Caching%20assets%20using%20Service%20workers/Untitled_1.png](Caching%20assets%20using%20Service%20workers/Untitled_1.png)

In order to start asset caching, you need to install an `ember-service-worker` plugin called `ember-service-worker-asset-cache`.

    ember install ember-service-worker-asset-cache

Once this addon is installed, inspect the Network tab on Chrome and you should see the assets (CSS and JS) are now served from “ServiceWorker”.

![Caching%20assets%20using%20Service%20workers/Untitled_2.png](Caching%20assets%20using%20Service%20workers/Untitled_2.png)

But if you notice, [localhost](http://localhost/) (index.html) file is not cached. Don’t worry, another `ember-service-worker` plugin called `ember-service-worker-index` has got you covered.

    ember install ember-service-worker-index

![Caching%20assets%20using%20Service%20workers/Untitled_3.png](Caching%20assets%20using%20Service%20workers/Untitled_3.png)

Well, you can now turn off your “Internet” and refresh the page, your app will still load. Apparently, your app is now “Offline first”.

Now that your assets and index.html files are cached, they should be faster on mobile networks that are slow.

---

### PRO Tip

1. If you had followed the above, step-by-step, you might not have seen some things don’t work as mentioned in the screenshots. This is likely because the service workers we installed along with the caching plugins, would have cached your assets. In Google Chrome, you can toggle the “Update on Reload” setting from the “Application” tab of Developer tools. Another way is to find your service worker from “Application” tab of Developer tools and hit “Unregister” and reload the page. Second time reload should resolve the issue.

    ![Caching%20assets%20using%20Service%20workers/Untitled_4.png](Caching%20assets%20using%20Service%20workers/Untitled_4.png)

2. Do not fingerprint service-worker files. By default, `sw-registration.js` file will not be fingerprinted. This is to make sure your app’s service worker registration and asset cache are not lost on rebuild and reload.
