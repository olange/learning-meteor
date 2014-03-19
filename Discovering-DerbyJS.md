# Discovering DerbyJS

### Basics

* [MIT License](http://opensource.org/licenses/MIT)
* Packaging with [npm](http://npmjs.org/)
* Module dependencies with [npm](http://nodejs.org/api/modules.html) (builds upon [CommonJS](http://wiki.commonjs.org/wiki/Modules)) and [Browserify](https://github.com/substack/node-browserify)
* Deployment to any Node.js server (includes Heroku)
* Datastores: swapping in MongoDB, Riak, Postgres, CouchDB, or another service, should be straightforward, without modifying application code
* Propagation of changes: PubSub
* Server static rendering
* Firing of the onload event: less than 200ms for simple apps
* Templating with [Handlebars](http://handlebarsjs.com); two-way [data bindings](http://derbyjs.com/#bindings)
* Asynchronous callback style of Node.js server code
* **Works offline**
* _Instant redeployment?_ seems to handle it out of the box
* _Client and server logging?_
* _Module authentification?_ (TODO)

### Releases

* 20130704 Derby 0.5.0 (Racer, ShareJS)
* 20120403 Derby 0.3.1 (LESS, Express)
* 20120325 Derby 0.1.10 (improves templates and event bindings)
* 20120309 Derby 0.1.9 (easier installation without Redis; automatic reloading)

### Who's who

[Lever](https://lever.co/), San Francisco

* [Nate Smith](https://github.com/nateps), Google Search
* [Brian Noguchi](https://github.com/bnoguchi)
* [Joseph Gentle](https://github.com/josephg), Google Wave + ShareJS

### Quelques composants notables

* [ShareJS](http://sharejs.org) _an Operational Transform (OT) library for NodeJS & browsers. It lets you easily do live concurrent editing in your app. [...] OT is a class of algorithms that do multi-site realtime concurrency. OT is like realtime git. It works with any amount of lag (from zero to an extended holiday)._
* [Racer](https://github.com/codeparty/racer/tree/0.5), ShareJS, LiveDB, Redis, MongoDB

### From the Blog

* [Derby 0.5.0](http://blog.derbyjs.com/2013/06/04/derby-v0-dot-5-0/) 04.06.2013 « _We’re happy to release the brand-spanking-new Derby 0.5! We’ve completely rewritten Racer, Derby’s realtime model layer on top of ShareJS. Derby 0.5 is the first full-featured web app framework with all data synced via Operational Transformation. It is also the first framework like it to support horizontal scaling to multiple servers. And while not new, Derby is still the only realtime framework with full support for server and client rendering with no extra code._ »
* [Our take on Derby vs. Meteor](http://blog.derbyjs.com/2012/04/14/our-take-on-derby-vs-meteor/) 14.04.2012 « […] _But despite finally using the same language, few Node.js applications to date deliver on the amazing ability to share code. Even with a common language, there are still a lot of issues including very different latency and connection stability, separate ways of dealing with URLs on the server and in the browser, the existence of a DOM in the browser and not on the server, and direct access to a filesystem only on the server._ »

### Arguments pour ce style de développement

* In order to have a responsive web app, it is critical to both render pages on the server and in the browser
* [When doing that] Adding new features typically involves changing both server and client code, often *in different languages*
* [Having the same language on the server and the client] We also want to avoid duplicating *rendering code* and *manually synchronizing changes* in client and server code bases
* Derby simplifies adding dynamic interactions by running the same code in server and browsers, and syncs data automatically.

### Différences entre Meteor et Derby

Source: [Our take on Derby vs. Meteor](http://blog.derbyjs.com/2012/04/14/our-take-on-derby-vs-meteor/)

* « Derby’s goal _is to make it possible for any developer to write apps that **load as fast** as a search engine, are as interactive as a document editor, and **work offline**._ »
* « Meteor’s goal _is to create “a ‘mass-market’ app platform that could be used for 90% of the sites on the web, and for that 90%, make web development faster and within reach of more people._ »

