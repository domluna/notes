# Zero Runtime Overhead Metaprogramming

[Paper](http://stefan-marr.de/papers/pldi-marr-et-al-zero-overhead-metaprogramming/)

### Definitions

Metaprogramming -> Reflection, dynamic proxies, MOPs

MOP -> Meta object protocol

## Background

Previous solutions either:

1. reduce expressiveness of metaprogramming techniques
2. burden the application and library developers with applying
optimizations

Trace-based compilation can optimize reflective method invocation
or field accesses. However, MOPs still require further optimizations.

Trace-based compilation also has issues. Programs with many unbiased branches
can result cause trace explosion and performance degrades rapidly. Another issue
is integrating tracing into multi-tier JITs.

### Misc

Polymorphic inline caches. Keep a cache of the argument types a method is called
with. Essentially we're using a specialized method for particular argument types.
This avoids looking up the method several times with similar arguments.

Dispatch chains generalize this behaviour to more than methods and provide a mechanism
to cache arbitrary values as part of AST nodes. 
