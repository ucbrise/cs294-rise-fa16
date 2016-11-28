---
layout: page
title: "Realtime Systems"
description: "Realtime Systems (Ion)"
use_math: true
---

Much of the focus of the Real-time Systems research is on resource allocation and scheduling that ensure that jobs meet their timeline guarantees. In this lecture, we will go over several papers that touch on the main challenges and tradeoffs. These include handling bursty (interactive) workloads, heterogenous traffic, parallel jobs, and multitenancy.

### Basic real-time scheduling
*C. L. Liu, J Layland.* 1973. [**Scheduling algorithms for multiprogramming in a hard real-time environment.**](http://igm.univ-mlv.fr/~masson/pdfANDps/liulayland73.pdf) Journal of the ACM, 20 (1): 46–61.

### Handling bursty traffic and hierarchical allocation
*Ion Stoica, Hui Zhang, T. S. Eugene.* 1997. [**A Hierarchical Fair Service Curve Algorithm for Link-Sharing, Real-Time and Priority Service.**](https://www.cs.cmu.edu/~hzhang/papers/SIGCOM97.pdf) SIGCOMM'97.

### Handling multiple types of resources
*Ali Ghodsi, Matei Zaharia, Benjamin Hindman, Andy Konwinski, Scott Shenker, Ion Stoica.* 2011. [**Dominant Resource Fairness: Fair Allocation of Multiple Resource Types.**](https://www.cs.berkeley.edu/~alig/papers/drf.pdf) NSDI'11.

### Low latency schgeduling of dependent tasks
*Dror G. Feitelson, Larry Rudolph.* 1992. [**Gang Scheduling Performance Benefits for Fine-Grain Synchronization.**](http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.79.7070) Journal of Parallel and Distributed Computing. 16: 306–318.

### Questions
Questions are available [here](https://goo.gl/forms/bWfRhOm37KkZ73Ft1).


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

1. Name one way in which algorithmic advances simplify model serving and one way in which they add additional challenges. -->



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



