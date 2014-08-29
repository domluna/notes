js memory masterclass notes
===========================

## Source

https://speakerdeck.com/addyosmani/javascript-memory-management-masterclass

## Good rules to follow

* Avoid long-lasting refs to **DOM elements** you no longer need
* Avoid **circular** object refs
* Use appropriate **scope**
* Unbind **event listeners** that are not needed anymore
* Manage **local cache** of data. Use an aging mechanism to get rid of old objects.

### WeakMaps!
In ES6, WeakMaps can be used to remedy many strong reference problems. **If the only references
to an object are weak then the GC can collect the object**.

### Object Pitfall

In regular JS objects, do

```js
obj.x = null;
# rather than
delete obj['x']
```

V8 uses hidden classes to optimize JS. By deleting an object property we are
actually de-optimizing this optimization. Leading slower runtimes and increased
memory usage.

## What do we want?

We wawnt 16ms to do everything, what is everything?

1. Handle Input
2. Javascript
3. Layout
4. Paint
5. Composite

This is 60 frames/sec performance.

## Memory management basics

### Core Concepts

* What types of values are there?
* How are values organized in memory
* What is garbage?
* What is a leak?

### Four primitive types

1. boolean
  * true or false
2. number ( no ints yet :(  )
  * double precision IEEE 754 number
3. string
  * UTF-16 string
4. objects
  * key value maps
  * key = string
  * value = any var type

### The value graph

The graph starts with a root, the root is probably the browser "window" or a global object or
a Node module.

Root Node -> {Object Node, Scalar Node}
Object Node -> {Object Node, Scalar Node}
Scalar Node (leaf)

### So Garbage?

Garbage is all values which cannot be reached from the root node.

Steps:
1. Find all live values
2. Return memory used by dead values to system

### Memory Leaks!

"Gradual loss of available computer memory." 
  
![Think death by spoon](https://www.youtube.com/watch?v=9VDvgL58h_Y)

## Performance Tools

> performance.memory

```js
jsHeapSizeLimit # the amount of memory (bytes) that the JS heap is limited to
totalJSHeapSize # the amount of memory currently being used
usedJSHeapSize # the amount of memory (bytes) that the JS heap has allocated, including free space
```

## Use Chrome DevTools

## Is it worth it?

### GMail Case Study

> Through optimization, we reduced our memory footprint by 80% or more for power-users and
  50% for average users. - Loreena Lee, GMail

## Sanity Checklist Questions

* How much memory is your page using?
* Is your page leak free?
* How frequently are you GCing? (sawtooth pattern)

## More resouces

[v8 perf](https://thlorenz.github.io/v8-perf)


