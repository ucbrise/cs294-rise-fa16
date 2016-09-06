---
layout: page
title: "Securing distributed computation and leakage vectors"
description: "Securing distributed computation and leakage vectors (Raluca)"
use_math: true
---

In this lecture, we discuss how we can use SGX to secure distributed systems such as MapReduce (as in the VC3 system): the cloud performs the MapReduce computations without seeing the data or being able to tamper with the computation. Then, we will discuss various types of leakage in SGX and approaches (such as ORAM and GhostRider) to address these issues.


### Reading list:


<a href="https://www.microsoft.com/en-us/research/publication/vc3-trustworthy-data-analytics-in-the-cloud/">VC3: Trustworthy data analystics in the cloud</a>, Schuster et al

<a href="https://www.cs.utexas.edu/~yxu/files/xu15oakland.pdf">Controlled-channel attacks: deterministic side channels for Untrusted Operating Systems</a>, Xu et al


<a href="http://www.cs.umd.edu/~mwh/papers/ghostrider15.pdf">GhostRider: A Hardware-Software System for Memory Trace Oblivious Computation,
</a> Liu et al


### Optional reading:

<a href="https://www.youtube.com/watch?v=mPT_vJrlHlg">Path ORAM: An Extremely Simple Oblivious RAM Protocol</a>, Stefanov et al


### Questions:

TBA

<!--
![ML-Lifecycle](assets/images/ml-lifecycle.jpg){:width="400px"}

While much of the focus of machine learning research is on the process of training models (i.e., learning) there are a unique set of challenges around the process of serving and updating those models that is often overlooked.
In this lecture we will explore the bigger machine learning life-cycle and discuss the challenges around serving predictions.

## Reading lists:

### Prediction Serving Systems [?Student Presenters?]
1. *Deepak Agarwal, Bo Long, Jonathan Traupman, Doris Xin, and Liang Zhang.* 2014. [**LASER: a scalable response prediction platform for online advertising.**](http://dl.acm.org/citation.cfm?id=2556252) In Proceedings of the 7th ACM international conference on Web search and data mining (WSDM '14).


### Managing the ML Lifecycle [?Student Presenters?]
1. *Xinran He, Junfeng Pan, Ou Jin, Tianbing Xu, Bo Liu, Tao Xu, Yanxin Shi, Antoine Atallah, Ralf Herbrich, Stuart Bowers, and Joaquin Quiñonero Candela.* 2014. [**Practical Lessons from Predicting Clicks on Ads at Facebook.**](http://dl.acm.org/citation.cfm?id=2648589) In Proceedings of the Eighth International Workshop on Data Mining for Online Advertising (ADKDD'14).

1. *D. Sculley, Gary Holt, Daniel Golovin, Eugene Davydov, Todd Phillips, Dietmar Ebner, Vinay Chaudhary, Michael Young* 2014. [**Machine Learning: The High Interest Credit Card of Technical Debt**](http://research.google.com/pubs/pub43146.html). SE4ML: Software Engineering for Machine Learning (NIPS 2014 Workshop)


### Questions:

1. What differentiates serving machine learning models from standard data serving?

1. Name one way in which algorithmic advances simplify model serving and one way in which they add additional challenges.

 -->

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



