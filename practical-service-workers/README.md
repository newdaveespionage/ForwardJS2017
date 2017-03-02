# Practical Service Workers

@jemyoung @ netflix
front end happy hour

* loves dogs
* loves cats (they don't love him)
* big fan of fast and furious


## Building the web

* the web is weird
* we can build something amazing with the building blocks of coding
* service worker is a building block

## Service worker

* event-based proxy
* twitter facebook linkedin use them
* pulls in web data on an event basis
* completely asychronous
* https only (does work local without cert)
* no access to local storage (local storage is synchronous)
* event-based
  * install ( after download )
  * activate
  * fetch
    * returns a promise
    * used in modern browsers
    * think jQuery.get() ish
  * cache
    * a map where the keys are requests, values are responses
    * have to use CacheStorage
    * open the cache
    * then put in the cache (cache.add)
  * message
  * sync (not yet ready)
  * push (not yet ready)

## Web workers

* Why? Because Javascript has events
* The event loop (only happens in UI thread)
* paints fail during expensive computations if they're on the UI thread
* runs in separate thread, so does not interrupt the UI thread

## Lifecycle and events

* register it if it's in window.navigator
* event.waitUntil(Promise) - keeps service works alive
* will die if you don't waitUntil
* open cache
* check cache
* cache.addAll (in example, array of urls) on initialize
* event.respondWith(function to respondWith) - receive response from waitUntil worker
* using promises, return either response, or fetch
* fetch, then clone response, direct access breaks

## Practical Examples

* cloud to butts
* er... cats to dogs
* er... error page
  * check if fetch returns ok
  * else return fail page
* transpiling ES2015 on the client
  * is it fetching js
  * is it necessary to transform it?
  * run it through transpiler and return
  * else just return fetch

## Unsolicited Advice

* don't cache the service worker
* leverage devtools
* service workers can be scoped, know where yours is
