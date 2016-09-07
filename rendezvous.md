---
layout: page
title: "Data-Centric Programming"
description: "Data-Centric Programming: Rendezvous, Bloom and CALM (Joe)"
---

Computer scientists have figured out how to build scalable distributed systems for analyzing data in parallel. But we haven't really cracked the general-purpose distributed programming problem. Could we translate our success with distributed data analytics back to solve the "hard parts" of distributed programming? Today we'll dig deep into that question.

To start, we'll observe that many aspects of computing systems depend on "rendezvous": bringing things together in the right place at the right time. This idea plays out in topics from messaging to code execution to interrupt handling to directory services and join processing. We'll break this down to the basics, and build up from there to a data-centric view of computing that revolves around asynchronous processing of event streams and state tables. We'll explore the advantages of "everything is data" for system-building by going deep into a line of exploratory systems and languages we've built at Berkeley.

Having turned our notion of programming on its head, some familiar mechanisms seem to become a bit odd. In a world of event stream processing, what is the role of coordination mechanisms like barriers, locks and consensus. *How* do we use them in our programs? *When* should we use them in our programs? What were they doing for us in our traditional languages anyhow? Can we avoid them? The CALM Theorem shows that these questions hinge on the notion of Monotonicity---a key that unlocks robustness and scalability for distributed systems. We'll talk about surface and intrinsic notions of monotonicity, and how we can expose them to programmers.

## Reading lists:

### Data-Centric Distributed Systems
1. *P Alvaro, T Condie, N Conway, et al.* 2010. [**BOOM Analytics: Exploring data-centric, declarative programming for the cloud.**](http://db.cs.berkeley.edu/papers/eurosys10-boom.pdf) In Eurosys 2010.

### Bloom and the CALM Theorem
1. *P Alvaro, N Conway, JM Hellerstein, WR Marczak* 2012. [**Consistency Analysis in Bloom: a CALM and Collected Approach.**](http://dl.acm.org/citation.cfm?id=2648589) In CIDR 2012.

### Logic and Lattices
1. *N Conway, WR Marczak, P Alvaro, et al.* SoCC 2012. [**Logic and lattices for distributed programming**](http://db.cs.berkeley.edu/papers/socc12-blooml.pdf). In SOCC 2012.


### Questions:

1. Explain how buffers enable rendezvous in time, in the case of both asymmetric and symmetric rendezvous.

1. List as many advantages as you can for the strategy of representing all system state as first-class data in tables. Disadvantages?

1. Why are MapReduce and Spark "easy" to parallelize? To make fault tolerant?

1. How do Overlog and Bloom differ from MapReduce and Spark?

1. Finding the exact count of items in a set requires coordination (blocking). Testing whether the count of items in a set is above some threshold does not require coordination. Why? How can lattices and monotone functions make this explicit and testable in a program?

1. Lattices support a commutative, associative, idempotent merge operator. Does that make them monotonic?  Why (or why not)?

1. Are immutable objects monotonic? Are monotonic objects immutable?

1. Give a strategy to represent immutable key/value pairs in a lattice abstraction. Can you also give a strategy to represent mutable key/value pairs?

1. Experienced programmers tend to find Bloom unfamiliar (and Overlog impenetrable). Can you imagine repackaging the lessons of Bloom in a more traditional programming model?

## Answer the questions

<iframe src="https://docs.google.com/a/berkeley.edu/forms/d/e/1FAIpQLScZjGkuxikWf0VfTI0iG2D5UhFpFKetVr3Wz2PXkZKgXLDkZA/viewform?embedded=true" width="760" height="600" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>

<!--

Formatting with Kramdown (github style markdown):

https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

# heading 1
## heading 2
### heading 3


# A list

1. a
1. b
1. c

*italic*
**bold**

```scala
// this is scala
def f(x) = x + 3
```

```bash
%> echo "the end" | less
```


# An inline equation without number:

this is all about $x$ and $\alpha$:

$$
3x + 5
$$

# An inline equation with numbering

\begin{align}
y \propto \frac{x \sin x} {\int_0^\infty x \sin x}
\end{align}
 -->

<!-- {: style="text-align: center"} -->



