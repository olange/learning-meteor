# Discovering Meteor

### Somes basic facts

* [MIT License](http://opensource.org/licenses/MIT) (originally released with GPL License)
* _Meteorite package system_ (TODO)
* _Module dependencies?_ (TODO)
* _i18n?_ traductions des interfaces, formatage des nombres et dates: quelques modules basiques, mais pas sûr qu'ils fassent les dates (https://github.com/jerico-dev/meteor-i18n, https://github.com/subhog/meteor-just-i18n)
* _Deployment?_ (TODO) « _easy to create and deploy a Meteor app to their hosting service, but much harder to use Meteor as a module of a more traditional Node.js server._ » Nath Smith/DerbyJS, 14.08.2012
* _Datastore_ MongoDB principalement, dont ils exploitent le mécanisme spécifique d'_Op Log Tailing_ pour propager les changements rapidement; ils utilisaient plus tôt un mécanisme de _database diff-and-polling_, plus générique à mon avis, mais qui imposait un délai de 10-15 sec. avant propagation des changements dans le datastore; très orientés _object store_ avec documents semi-structurés; dénormalisation des données et modèle dicté par l'usage (qui peut différer des recommendations de modélisation de MongoDB même d'après ce que j'ai compris); en conclusion: Meteor fonctionne au mieux avec MongoDB à ce stade, il faut le prendre comme un donné
* _Propagation of changes?_ LiveMongo Database Polling (writes to the database, and polls it frequently for the data in use by every connected client)
* _Server static rendering_? (TODO)
* _Indexable by search engines?_ seems to, using the _Spiderable_ package
* _Static URI space?_ (TODO)
* _Firing of the onload event?_ (TODO)
* _Templating? two-way data bindings?_ (TODO)
* _Support for working offline?_ (TODO) important
* Synchronous server Node.js code with [Fibers](https://github.com/laverdet/node-fibers)
* _Instant redeployment of modules?_ (TODO)
* _Client and server logging?_ (TODO)
* _Module authentification?_ (TODO)

### Documentation

* [Meteor Documentation](http://docs.meteor.com)
* [A study plan for Meteor](https://www.discovermeteor.com/blog/study-plan-meteor-1-3/) Sacha Greif, 01.04.2016
* [Learn Meteor](http://www.meteor.com/learn-meteor) liste des ressources recommandées
* [Discover Meteor Book](www.discovermeteor.com) ouvrage en ligne qui couvre l'apprentissage de Meteor
* [Meteor Roadmap](https://trello.com/b/hjBDflxp/meteor-roadmap) tableau Trello, très intéressant; v1.0 prévue pour early 2014; [i18n](https://trello.com/c/FCIRLtdN/38-i18n) pour 1.1+ (y'a un [sondage](https://www.surveymonkey.com/s/MZZZPHW) en cours)
* [Meteor Usermap](http://usermap.meteor.com)
* [Meteor DDP Specification](https://github.com/meteor/meteor/blob/devel/packages/livedata/DDP.md) « _DDP is a protocol between a client and a server that supports two operations: 1. Remote procedure calls by the client to the server; 2.The client subscribing to a set of documents, and the server keeping the client informed about the contents of those documents as they change over time._ »

### Channels

* [Meteor Google Group](https://groups.google.com/forum/#!forum/meteor-talk)
* [Meteor StackOverflow](http://stackoverflow.com/questions/tagged/meteor)
* [Meteor GitHub](http://github.com/meteor/meteor)

### Talks on fundamentals

* [Meteor -- Web Development Like You Never Seen](http://www.infoq.com/presentations/meteor) InfoQ, Matt DeBergalis, 22.07.2013, video 48min.
* [Meteor Intro Screencast](http://meteor.com/screencast) meteor.com, video 10min.
* [Meteor Authentication Screencast](http://meteor.com/authcast) meteor.com, video 10min.
* [An Interview with Nick Martin](http://book.discovermeteor.com/interview/nick-martin) Discover Meteor Premium Edition kit, MP3 22 min. « _[...] SCALING MATTERS: Scaling is really very app dependent and very dependent on the data load, the way you use data in your queries. Meteor, as it ships, stock, only runs one node process for your app. With only one process, it's taking only one core, and node doesn't do multi-threading, so it's really just one CPU core. There is only so far the app can scale. [...] RAM vs CPU: Meteor does right now keep in memory on a server all of the output from all of the subscriptions to be able to do the diffing. The total sum of all of the data for all of the clients, with deduplication, will be a memory limit. [...]_ »
* [An Interview with Matt DeBergalis](http://book.discovermeteor.com/interview/matt-debergalis) Discover Meteor Premium Edition kit, MP3 25 min. « _[...] AN IMPOSSIBLE CHOICE: They were trying to build websites that felt as good as Google+ and Facebook that had these rich interactive experiences where the browser felt almost like a desktop application. But it turns out that writing those apps takes a lot of time. They were also in a hurry because anybody starting a new product wants to get something out the door quickly and see if it resonates, if they're going in the right direction. [...] The reason for that is that there wasn't a standard platform for writing client-side JavaScript applications. [...] METEOR VS FIREBASE: Firebase is really interesting. It's a real-time database that's provided as a service on the Web. So, Meteor and Firebase can actually be very complementary because a big part of Meteor is this idea of real-time data, of being able to watch documents change over time. [...] NEXT STEPS: There are a couple things on the short term horizon for us. One big one is that we are working on a forms system so that it's easy to build complex forms, and a meteor application, forms that have different validations on the fields, that let you save everything at once, or maybe, save as you type, have different behaviors around how they interact with the rest of the database. [...] MAKING MONEY: I think what we're going to be doing is, people build larger and larger Meteor apps. There's going to be a class of companies, typically larger companies with operations teams, that want to buy additional software to help them run those applications. A lot of companies don't want to build those things by hand and they don't want to manage those things by hand. Our focus right now is on the open source Meteor SDK, but over time, we'll build some tools to help those companies with those problems. [...] _ »

### Articles

* [Meteor Load Test](https://github.com/alanning/meteor-load-test) _Load testing tool for Meteor applications, Adrian Lanning. Based on [load-testing-with-clojure](https://github.com/locopati/load-testing-with-clojure) by Andy Kriger which load-tests stateless websites. Uses [The Grinder](http://grinder.sourceforge.net) to manage agents and record performance metrics. Uses the [java-ddp-client](https://github.com/kenyee/java-ddp-client) by Ken Yee to communicate with the target Meteor server. Evolved from discussion on the meteor-talk google group: [Load Testing Meteor](https://groups.google.com/forum/#!topic/meteor-talk/M9waYvcFufs)._ Voir aussi l'intéressante définition de la terminologie de la performance dans cette page (transcrite dans notre [nomenclature](nomenclature)).
* [How to connect meteor to an existing backend?](http://stackoverflow.com/questions/19893387/how-to-connect-meteor-to-an-existing-backend/19910190#19910190) Question sur StackOverflow #meteor, avec réponses qui suggèrent de partager instance MongoDB entre appui Clojure et Meteor
* [Meteor js as front end, what use for backend?](http://stackoverflow.com/questions/14921576/meteor-js-as-front-end-what-use-for-backend) Quelques pistes à tracer

