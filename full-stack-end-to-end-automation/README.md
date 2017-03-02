Full Stack End to End Automation
--------------------------------

[slides](http://github.comairware/webdriver-mocha-async-await-example)

Test pyramids
=============

* lower test costs less
* higher costs more (more overhead)
* in this case first three were visual, ui, and http rest api
* REST used testing endpoints
* UI used Selenium node libs
* visual diff using applitools.com

Timeline
========

* Nightwatch - the phrasing of functions with promises did not allow for breaking, ended up not using
* ended up on ES7
* Async Await
* Babel
* ESLint + StandardJS
* Flowtype (facebook)
* selenium-webdriver
* request lib (async await solved most problems)

Recipe for a node/selenium framework
====================================

What is useful?
* Representation of the page
* Readable tests
* Frontend testability
* Robust backend API
  * Clients to work with the API
* De-async your code
* Visual tests (visual diffs)
* Accurate and descriptive reporting - who gets the errors, what errors to report

POM - page object model
=======================

* a way to build a model of a page
* represent page as an object or model
* page object abstracts away driver interaction
* one page, one page component

Readable Tests
==============

* abstract away any sort of driver interaction with the test
* may lead to long method names (as long as it clarifies the test)

Frontend testability
====================

* use css selectors
* cook data models into your elements (for test tracking)
* break down ui interaction to only the functionality being tested
  * use API/backend to set up data to allow frontend to navigate to specific destination for test
  * bootstrap test state if backend cannot be engineered that way

De-asyncing tests
=================

* How to write async actions in a sync manner
* selenium webdriver - promise manager - not readable, not agnostic, not standard
* async await - awaits fulfilled values from promises, available natively in node 7
* is this available in some form using mocha?

Writing the test
================

* after driver methods are abstracted into pagemodel, test is list of actions
* use pagemodel methods for each desired page
* evaluate based on selectors established in test

Reporting
=========

* discuss what team needs most
* failures first
* flakiness vs failure - what is actually broken?
  * prioritize failure for devs
  * flakiness for test engineers
* assertion messaging (translate assertion values)
* screenshots
* video if possible
