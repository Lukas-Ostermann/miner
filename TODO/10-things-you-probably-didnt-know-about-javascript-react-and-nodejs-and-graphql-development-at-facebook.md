**Translation:**
>* Original Article Link: [10 things you probably didn't know about JavaScript, React, and Node.js, and GraphQL development at Facebook](https://hashnode.com/post/10-things-you-probably-didnt-know-about-javascript-react-and-nodejs-and-graphql-development-at-facebook-cink0r0e500h5io53fpl7ediu)
* Original Author: [Sandeep Panda](https://hashnode.com/@sandeep)
* Translated by: [Jack](https://github.com/Jack-Kingdom)
* Proofreaders: [DeadLion](https://github.com/DeadLion), [Joddiy](https://github.com/joddiy)

# 10 Things You Probably Didn't Know about JavaScript, React, and Node.js, and GraphQL Development at Facebook

Recently, Lee Byron from Facebook ([@leebyron](https://hashnode.com/@leebyron)) hosted an [AMA](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda) (Ask Me Anything) on Hashnode. Many interesting questions were raised, and Lee revealed some amazing facts and details about how Facebook uses React, GraphQL, and React Native in their development environment. I've read through his answers in the AMA, pondered, and summarized ten interesting highlights.

So, let's get started.

## What Inspired React?

React was partially inspired by [XHP](https://github.com/facebook/xhp-lib), created by Marcel Laverdet from Facebook in 2009 for modularizing Facebook's user interface. Check it out [here](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda#cin120uib00edlv533i6d8yd7).

## Is Facebook Planning to Rewrite its Mobile App with React Native?

Well, the answer is: _they already did_. Some parts of Facebook's app are built using React Native, and some are not. Get detailed answers in this [discussion](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda#cin6vg5r201wqjh53ne77tao1).

## Where is Immutable.js Being Used at Facebook?

* Ads Manager and their React Native Android and IOS apps.
* Messenger website ([messenger.com](https://hashnode.com/util/redirect?url=http://messenger.com))
* New articles written with Draft.js.
* All comments on the Facebook News Feed.

## How Does Facebook Write CSS for React Components?

Lee revealed that they prohibit importing CSS rules into any file other than React components. This ensures a component exposes the correct API via formatted props, and other components cannot override it by importing a rule. Additionally, they don't need to use JavaScript tricks to import CSS files. Instead, they follow the convention of `Button.js` being adjacent to `Button.css`. See [here](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda#cin5qpdbv01apk85319o2c1fx) for more details.

## Will Facebook Update React Components with Every Major Release?

* Yes, they will.
* Facebook usually deploys the React **master** branch to production.
* Since 2012, there haven't been many major changes to the React API. Therefore, the React team rarely faces situations where they have to update components.
* If there's a sudden update, Ben Alpert from the React team takes care of all the syncing work in the codebase.
* They also use automated tools like [jscodeshift](https://github.com/facebook/jscodeshift) to simplify the process.

## What's the Story Behind GraphQL?

GraphQL emerged in 2012 when Lee was working on the IOS team focused on the News Feed. At that time, Facebook was rapidly growing in areas with poor network conditions. Therefore, GraphQL was initially designed to address slow mobile connections. Soon, when Relay was ready to be open-sourced, they realized it wouldn't make much sense without GraphQL. Simultaneously, they acknowledged the cleverness of the GraphQL service and realized most companies outside Facebook hadn't used it. So, they decided to release it by writing a language-agnostic specification. That's the story behind GraphQL. Read more [here](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda#cin1gw37n00kwlv53rretxpe8).

## In What Scenarios is Facebook Using GraphQL?

Facebook's Android and IOS apps heavily rely on GraphQL. In some cases, like Ads Manager, the entire app is built using Relay + GraphQL.

Yes, Facebook heavily depends on SSR. However, Lee mentioned that they rarely have scenarios where they render React components on the server. It mostly depends on their server environment.

## Does Facebook Use Node.js?

Lee mentioned they have many client-side tools written in JavaScript and run via Node. [Remodel](https://github.com/facebook/remodel) is an example of such a tool installed through npm. All their internal GraphQL client tools on IOS and Android use Node. However, they don't use Node much on the server side, as there hasn't been a strong demand so far. Even if they decide to use JavaScript on the server side (e.g., server-side rendering with React), they would directly use the V8 engine rather than Node.

## How Does Falcor (by Netflix) Compare to GraphQL?

According to Lee, both tools are trying to solve similar problems. When the GraphQL team first heard about Falcor, they had a meeting with the Netflix team and exchanged some ideas. Nevertheless, there are many differences between Falcor and GraphQL. Read more [here](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda#cinj7lim4002lid53x47g060n).

I hope you enjoy this very brief summary. For detailed answers and discussions, please visit the [AMA page](https://hashnode.com/ama/with-lee-byron-cin0kpe8p0073rb53b19emcda).
