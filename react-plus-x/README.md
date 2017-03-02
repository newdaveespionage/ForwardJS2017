# React Plus X

Mars, senior software engineer at Netflix
@marsjosephine

## Why build a UI component library?

* breaking out of the monolith, new repos, different frameworks & build systems
* brand & UX consistency across multiple teams and codebases

A UI component consists of one or more element that a user uses

## Why React?

* Less files per component
* markup is a function of state and props - ui components can be independent of data source, but still have full control over interactions
* easily ported into different frameworks
  * for instance: use a react component in a backbone view

## What makes a UI component reuseable

* self-sufficient
  * do one thing
  * do one thing well
  * do one thing consistently
  * no bootstrapping just to get it up and running
  * allow state to be initialized* enough state to be useful
* easy to integrate with
  * make component interface easy to understand
  * leverage propTypes
  * specify what types of props component expects
  * specify which props are required
  * leverage warning system
  * gulp-react-docs
  * as few props as possible
    * reduces cognitive load for consumer devs
    * fewer touchpoints
  * multiple types for one prop (oneOfType)
  * decouple when part of a component is optional
    * example: no tabs by not supplying any rather than a 'hideTabs' prop
  * Remove backdoors
    * explicit functionality calls, rather than allowing a free-for-all when consumers pass in functionality
  * Fill container element, assume consumer will be putting component in a container
  * Publish assets intelligently
    * support as many build systems and development evironments as possible
    * publish to multiple sources (npm and cdn, for instance)
    * make sure components are versioned (package.json, version-specific locations on cdn)
    * transpile to lowest supported version
    * remove relative urls in asset files (css), create absolute urls on destinations
    * namespacing
    * explicitly document dependencies (what needs to be installed to be run)

### resulting in driving adoption
