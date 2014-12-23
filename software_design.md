Software Design
---------------

This doc contains some things I have read or picked up on
throughout the passage of time.

### Generic vs. Specific

Should this solution be generic or specific?

A generic system is designed to have one system that solves
many problems.

A trivial but good example nonetheless is an array data structure.
A generic array can be used to solve many problems due its ability
to deal with variable types (homogenous setting). Data structure 
implementations are probably the killer system for generic problem solving.

After data structures the generic approach to problem solving is significantly more
unclear.

In spite of this we have a mindset where we try to make everything generic. Write
a library for X, this makes our code modular and resuable! Now I have to define
what I mean by library here. I mean something like jQuery or Esprima or Express.
Something that can be widely used by hundreds of other projects/applications.

I personally have fallen into this trap many times, the issue is that the problem
is very likely to not require a solution like jQuery nor is it more helpful to have.

There's also the caveat that the more generic something is, the harder to optimize
it is as well. If you can optimize a generic solution well it is because it was a
generic problem to begin with.

We are introduced into introductory algorithms classes to very generic problems and data structures.
In the real world generic algorithms often aren't performant enough for the application or add
significant complexity. Algorithms that focused on solving instances of general problem sets are
becoming more popular for these very reasons.

Not to mention solving the problem generically might be infeasible (time/space costs).

#### Closing Thoughts

Write modular/composable code, but don't make things generic for no reason. This code solves
your problem not the everyone's.

If you need an ostrich for ostrich things. Don't teach it to fly just for the sake of it.
