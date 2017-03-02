Webpack It's Not Magic
----------------------

@naomicodes
[slides](https://naomijacobs.github.io/WebpackTalk)

How I learned it
================

* tried using it on a few side projects
* Mavenlink (company where she works) started using it

Why this talk?
==============

* We are happier when we demystify our tools

What is Webpack
===============

* takes stuff that is nice for you to write and makes it into stuff that is nice for your browser to read

What problems does it solve
===========================

* namespacing
* files need to be changed before they can go to the client
* send code to the browser efficiently

Note
====

* this is not the first solution
* other solutions require rolling completely from scratch or piecing together on a rather intense level

How I thought it worked
=======================

* checked dependencies
* cranked out one optimized file
* This is not how it works

How does it work
================

* takes path to entry file (starting file)
* find dependencies
* apply loaders
* implement modules (part of loader system)
* creating final asset

Finding dependent files
=======================

* tracks dependencies in array
* entry file is first entry
* read dependencies in entry
* validate dependencies
* if it leads to a valid path, add to array
* recurse

Apply loaders
=============

* a function that takes source, makes changes, returns code
* they can be added using npm
* use in config with regex selective calls
* can be chained
* examples: transpile, uglify, minify, polyfill
* module system

CommonJS
========

* system of writing js that allows files to declare dependencies on each other by importing and exporting modules from those files
* import modules by requiring them require('module')
* export modules by assigning them to module.exports = blah
* standard, not a library

Module system
=============

* wrap each file in a function
* replace each require instance to webpackRequire(index of file array where require target is located)

Create Final asset
==================

* start with a function that accepts an array of modules
* wrap it in iife (immediately invoked function expression)
* define webpackRequire inside iife
* define module, as a plain object with a key of 'exports' with an empty object
* load file we need based off of index from webpackRequire index parameter
* cache modules
* check cache
* call file as function with (modules, webpackRequire)
* return module.exports
* ultimately, kick off by invoking webpackRequire(0)

How did this solve our problems?
================================

* We have a single entry for the page
* all dependencies managed for us
* variables are scoped to their own files and only expose what they put on the exports object
* module privacy is possible by just not exporting
* browser gets plain javascript
