## Promises/A+
Spec of common, standardised behaviour 
https://promisesaplus.com/

Notes:

Events are great for things that can happen 
multiple times on the same object — keyup, touchstart etc.
async success/failure
A promise can only succeed or fail once. It cannot succeed or fail twice, 
neither can it switch from success to failure or vice versa
If a promise has succeeded or failed and you later add a success/failure 
callback, the correct callback will be called, even though the event took place earlier


A promise can be:

*fulfilled*
    The action relating to the promise succeeded
*rejected*
    The action relating to the promise failed
*pending*
    Hasn't fulfilled or rejected yet
*settled*
    Has fulfilled or rejected

*thenable*: object that is promise-like, with a `then` method

*Promises/A+*: common, standardised behaviour (spec)

*must not change* means immutable identity (i.e. ===), but does not imply deep immutability.

## Promise implementations

- *Q*: https://github.com/kriskowal/q
- *Bluebird*: https://github.com/petkaantonov/bluebird
- *RSVP*: https://github.com/tildeio/rsvp.js
- *ES6 Polyfill*: https://github.com/jakearchibald/es6-promise


## Promise API

*RSVP*

- promise.js
- /Promise 
    - all.js
    - race.js
    - reject.js
    - resolve.js
    
- events.js
    - mixin
    - on
    - off
    - trigger
- config.js
    - EventTarget['mixin'](config); //extends config object with EventTarget methods
- utils.js
    - Array.isArray(obj) // Little known fact: Array.prototype itself is an array
    - Using Polyfill `Object.prototype.toString.call(x)` to detect object class 
        - [object Date]
        - [object String]
        - [object Math]
        - [object Undefined] // Since JavaScript 1.8.5
        - [object Null] // Since JavaScript 1.8.5
- instrument.js
    - instrument(): scheduleFlush() when first queue memeber is stored.
- -internal.js
    - new TypeError([message[, fileName[, lineNumber]]])
    - Define CONSTANT value: PENDING (0), FULFILLED (1), REJECTED (2)
    - [Spec]: throw error is `then` function is not available for Promise 
    - getThen()
    - tryThen()
- node.js
    - getThen()
    - tryApply(f, s, a)
    - wrapThenable(then, promise)
- race.js
- enumerator.js



