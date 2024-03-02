**Translation:**
>* Original Article Link: [10 steps to better hybrid apps](https://medium.com/net-magazine/10-steps-to-better-hybrid-apps-e8e33831ea5e#.4fh1wbsy9)
* Original Author: [Oliver Lindberg](https://medium.com/@oliverlindberg)
* Translated by: [Yves X](https://github.com/Yves-X)
* Proofreaders: [Malcolm](https://github.com/malcolmyu), [circlelove](https://github.com/circlelove)

# 10 Steps to Create a Great Hybrid App

**As the popularity of hybrid apps grows, more and more tools are being created to help developers efficiently build cross-platform applications.** [**James Miller**](https://twitter.com/jimhunty) **presents 10 suggestions to help you achieve the best results.**

![Illustration by Luke O’Neill](http://lukeoneill.co.uk)

**1. Planning**

Planning your app before starting development can help you avoid many pitfalls and lead to a more successful outcome. Many situations that arise during the development process should be considered during the planning phase.

Hybrid apps use a web view that is essentially a scaled-down browser. You need to anticipate that issues existing in traditional browsers will also be present here. Understanding your target audience and their expectations helps clarify the technical shortcomings of your app. This, along with device analysis, can help you discover potential performance improvements and achieve higher performance benchmarks.

Once you know what your target audience wants, you need to consider distribution channels. Google Play and Apple's App Store are the two largest ecosystems. To list your app on these stores, you must ensure your app complies with their guidelines.

Google Play offers more leniency in app review and relatively easy distribution. However, reports can lead to your app being removed. Following these [guidelines](https://play.google.com/about/developer-content-policy.html?rd=1) increases the chances of your app being featured.

Apple has stricter [guidelines](https://developer.apple.com/app-store/review/guidelines/) and can be challenging. You need to integrate native features of the phone, not just build a web app. Features to integrate include the camera, location, and others, and they can be called through JavaScript plugins within the appropriate framework. Don't add features just to comply with store guidelines; make sure they are genuinely desired by users.

![Avoid Violations](https://cdn-images-1.medium.com/max/800/1*KpdzFI7j0VnryX4qGKWIkQ.jpeg)

**2. Market Considerations**

Applications are a global product, but unlike the web, they are mainly available in the app stores of specific countries. Each country has its own culture and laws. Don't assume your app is globally accepted; it's essential not to harm your brand by launching in an inappropriate country.

Equally important is considering the network limitations of the countries you want to target. Not every place has lightning-fast mobile internet access or Wi-Fi hotspots. Even if your app is not targeting emerging markets, network connectivity remains an issue. Keep the network requests of your app lightweight and try to minimize them.

**3. Scalability**

Whether it's logging in or updating data, most applications need a network component. This requires some form of server and API. As your app captures more users, this pressure will be applied to your backend, and issues like timeouts and errors will escalate. To avoid this problem, planning how your backend will scale is essential. Your API should follow a REST-style interface to establish a working standard. Consider adding authentication, as an open API may be prone to abuse. Terminals must also be managed correctly because once the app is released, it may take weeks for updated versions to run due to the review process.

Perhaps one day your API will receive too many requests and crash. Instead of rushing to invest in more servers, there are plenty of backend-as-a-service (BaaS) options available, including [Parse](http://parse.com) and [Firebase](http://firebase.com), which can help you address this issue. They store your data and often provide standardized APIs based on your data structure and authentication method. There are also many usage-based free plans. With global coverage, excellent technology, and robust network support, you know your app's network components will perform well.

![Parse](https://cdn-images-1.medium.com/max/800/1*RslHAZKu3bZscXv6ERaHZQ.jpeg)

**4. Performance**

In hybrid apps presented with web views, issues related to the varying support of multiple browsers and operating systems may arise. Progressive enhancement, a strategy used on the web, can also be applied to hybrids to provide a smooth cross-platform experience.

Having too many background processes will gradually drain the battery and reduce performance. Consider using frameworks like AngularJS or Ember.js to build your app as a single-page application. This will structure your code, making your app more maintainable. This common practice ensures better performance and reduces the risk of memory leaks. Frameworks like Ionic, which includes Cordova, AngularJS, and its own UI components, are suitable for building both rapid prototypes and final products.

On mobile devices, CSS animations perform better than JavaScript. Aim for 60 frames per second for a native feel, and use hardware acceleration where it can make animations more impactful.

![Ionic](https://cdn-images-1.medium.com/max/800/1*dKzEwQWP3ArLAUfSJh5ZWg.jpeg)

**5. Interaction Design**

Almost all mobile devices rely primarily on touch interactions. Based on this understanding, think beyond web limitations and use simple gesture-based interactions for an intuitive app experience. Touchscreen devices don't have a hover state, so consider using visual cues like active and visited states.

> Think beyond web limitations and use simple gesture-based interactions for an intuitive app experience.

On touchscreen devices, there is a 300-millisecond delay between a user touching the screen and the event being triggered. This is because web views wait to confirm whether it's a single tap or a double tap. Although not lengthy, this delay is noticeable. To overcome it, add the [FastClick](http://github.com/ftlabs/fastclick) script library to your project and instantiate it on the body.

**6. Responsive Design**

Today, devices have various screen sizes, covering a wide range of resolutions. Fortunately, responsive design principles still apply to hybrid apps and tablets. Within your chosen device range, focus on the smallest screen size, then select breakpoints for the sizes you want to cover. Consider both landscape and portrait views. Lock them in while building the app to reduce complexity and guide user behavior.

Consider how you will use app design patterns: pop-up menus, fixed headers, and list designs. Limited screen sizes are suitable for using icons instead of text for communication, but appropriate labels still help improve accessibility. Although users expect specific elements, don't let this limit your design.

**7. Images**

High-resolution screens are the preferred choice for mobile device manufacturers. But don't forget that many users still use older devices with lower screen resolutions. Choose appropriate images for the devices in your target market and ensure each image looks as good as possible. When images are frequently reused, store them on the device. File size can be larger than what you usually use on a mobile website, but also consider device memory size. For Retina screens, consider using SVG to maximize visual output, but be mindful of device support.

**8. Network**

Adopt an offline-first approach. With mobile devices, users will inevitably encounter times when they have no network connection, and the user experience should not be compromised. Optimize the experience when the signal is weak or nonexistent by locally caching network requests.

> Adopt an offline-first approach. Optimize the experience when the signal is weak or nonexistent by locally caching network requests.

Save scripts locally. In web development, external scripts improve performance because they are more likely to be cached. This doesn't work well in applications—even without a network, the app must function. Scripts often don't burden file size and connection speed but bring faster loading times and a native feel. If your user paths are predictable, consider preloading data for a seamless experience.

**9. Plugins**

As mentioned earlier, extending your web-based app with native features such as the camera, location, or social sharing significantly improves the user experience. Usually, you cannot invoke native features through a mobile web browser, but this can be achieved with plugins in hybrid apps.

Cordova is a hybrid app wrapping tool with many related plugins that can be called using JavaScript. See [Plugreg](http://plugreg.com) for their directory.

Be cautious with third-party plugins. Mobile operating systems evolve rapidly, and unsupported third-party plugins can cause issues, reduce battery life, and make your app unstable. Look for projects with high praise and active development on Github.

**10. Testing**

The core of hybrid apps is built with web technology. This means non-device functionality can be tested in a browser. Use task runners like gulp or Grunt to launch tools like LiveReload for an effective parallel development and testing workflow.

The next step is simulation. Google Chrome provides a [mobile emulator](https://developer.chrome.com/devtools/docs/device-mode) so you can test various screen resolutions on popular devices, which is helpful for designing breakpoints. Apple provides an [iOS simulator](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/iOS_Simulator_Guide/Introduction/Introduction.html) as part of Xcode, and Google provides an [Android emulator](http://developer.android.com/tools/help/emulator.html) as part of its developer tools.

This provides you the opportunity to test your app on simulated devices, faster than setting up on physical devices, and means you can test native device features. However, emulator performance depends on your machine, and the Android emulator is particularly slow. This led to [Genymotion](http://genymotion.com) creating a competitor that simulates Android much faster.

You shouldn't release an app that has never been fully tested on at least one real device. The real device environment is as useful as the emulator; it can highlight performance issues and pain points in user interaction.

**Conclusion**

These 10 suggestions provide a good starting point for turning your concept into a fully functional mobile app. However, in all aspects of web development, the pace of hybrid app development is so rapid. As the community grows, new tools and technologies emerge almost every day.

If you are truly committed to delving into the world of hybrid apps, the community will be one of your most valuable resources. Attending conferences and meetups is valuable; it keeps you up to date with the latest developments and allows you to share your creations. We look forward to seeing your insights!

**Popular Hybrid App Frameworks**

[CORDOVA](http://cordova.apache.org)  
The original and most popular open-source hybrid framework. JS APIs can call native phone features. It provides a CLI to assist in developing cross-platform apps.

[PHONEGAP](http://phonegap.com)  
PhoneGap is an Adobe product built on Cordova. Both are essentially the same, but PhoneGap offers additional services, including cloud-based app building and cross-channel distribution.

[IONIC](http://ionicframework.com)  
Ionic adds AngularJS and its own UI framework to Cordova for business logic and design guidelines. It is based on Cordova's CLI and adds services like LiveReload for deploying to devices. [Ionic Creator](http://creator.ionic.io) allows creating apps using its web interface.

[APPCELERATOR](http://appcelerator.com)  
It provides a unified platform for building native and web apps, supplemented with automated testing tools, real-time analytics, and BaaS. It aims to provide everything you need to deploy and scale your app, and these services are free until your app is launched.

[COCOONJS](http://ludei.com/cocoonjs)  
It provides an app wrapping tool with a built-in or modified Canvas and WebGL engine. This makes it an ideal environment for writing iOS and Android games using web technology.
