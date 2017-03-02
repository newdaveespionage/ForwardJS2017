# Webpack

https://github.com/freddyrangel/webpack-101

## Why webpack?

*   highly configurable and extendable build system for front-end (and back-end for Nodejs)
*   webpack 1 used commonjs modules (not statically analyzable) 2 uses es6 modules ("include", "module exports")
*   splits codebase into optimized loadable modules
*   uses loaders to preload and analyze codebase
*   tree shaking (tries to remove duplications created by mutual dependencies)
*   can preload fonts, styles, etc. and put into build directories as needed

## Why not?

*   Learning curve can be steep (took me two days, a week of tweaks)
*   Focused on Javascript for the web (if you're not doing this, this isn't what you need)
*   Can cause feature overload (doing things just because you can, not because you need)

## Things about optimizing

*   webpack wraps things in function scope, so you don't have to

## Changes from Webpack 1

*   used commonjs vs es6 modules
*   modules configuration section was much more complex... surprisingly

## Dev server

*   webpack-dev-server loads everything in memory (not visible in filesystem while running)
*   can consume a lot of memory if your codebase is large
*   elixir as a substitute?
*   allows hot reload, since it's in memory (not having to have a separate thread to watch for changes to trigger build)

## Config

*   ProvidePlugin allows easy translation of commonly used utilities, libraries, or base classes so that you do not have to explicitly include them
*   Configs can be specified, extensible using webpack-merge to create build-specific configurations, similar to maven configuration variations
*   Can bundle css / fonts, to allow for guaranteeing availability of libraries used, similar to ProvidePlugin but for the browser

## ES6 modules

*   less overhead for creating portable code modules
*   sensible importing, similar to java class imports (including *, though... ew)
*   allows for tree-shaking, ensuring singular inclusion and packaging of code when used multiple times, reducing duplication
*   removes dependency on globals soley for passing modular code around

## Testing (outside scope of webpack)

*   possible to integrate tests easily with Jest,
*   allows for package.json / .babelrc config of test env
