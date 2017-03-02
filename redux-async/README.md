# Redux Async

https://github.com/freddyrangel/async-in-redux-workshop

## Generators

* Generators can be async, woo!
* if you yield a generator, add star (*)

## Redux-Saga

* Implementation of Saga Pattern, instead of thunks, all side effect (async) logic in one place
* Failure management pattern
* Multi-workflow, compensating actions for every step of the workflow where it can fail
* Like daemons, long-living processes for orchestrating transactions and handling recovery from failures
* functions takeEvery takeLatest (direct), call put (redux-saga/effects)
* redux-saga has it's own control flow
* root saga gathers all effects

## Redux-Saga Functions

* call
  * accepts a function, and returns value of function in object (an effect)
  * can test without api calls happening, just assert that it returns an effect
* put
  * creates an effect? (look up info)
* takeEvery
  * is a generator
  * like a reducer, for each of something, do this thing
* takeLatest
  * creates a buffer of size 1 (ish)
  * for multiple calls, takes last, cancels all previous
  * is a generator
