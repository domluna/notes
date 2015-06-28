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

## Dispatch Chains

Polymorphic inline caches.

Idea is to have a cache called a dispatch chain which keeps track of methods
being called so that reflecive properties don't have to be recomputed on each
call.

Also it seems Metaprogramming in the context of the paper is doing reflection
type things such as method/field getters. So it doesn't cover the Lisp type of 
Metaprogramming.

The main insight is that dispatch chains can be used to remove the overhead of reflective
operations and MOPs.
