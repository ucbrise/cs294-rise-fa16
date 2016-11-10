---
layout: page
title: "Data Context Metadata"
description: "Data Context, Metadata and Ground"
use_math: true
---

 Data analytics researchers like to focus on new engines and algorithms. But most data analytics organizations 
 have a different and more fundamental problem: their analysts operate in a desperately information-poor environment. We are missing so much rich contextual metadata in our projects: what data we have, why we have it, how and by whom it gets used, and how all these aspects evolve over time. One problem is that we haven't been capturing and recording this information. A second is that we have yet to apply data science to the behavior of data scientists. It is time to get serious about capturing, recording, and analyzing the work people do with data and computation and the contextual human knowledge they bring to those tasks. This *data context* problem raises interesting systems challenges while also suggesting  opportunities for new applications and algorithms to significantly improve the efficiency of data analysts.

## Reading lists:

1. *Halevy, Korn, Noy, et al.*  [**Goods: Organizing Google’s Datasets.**](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45390.pdf) In SIGMOD 2016.

1. *Hellerstein, Sreekanti, Gonzalez, et al.* 2016. [**Establishing Common Ground with Data Context.**](https://github.com/ground-context/ground/blob/master/CIDR17.pdf) In CIDR'17. [[direct pdf link](https://github.com/ground-context/ground/raw/master/CIDR17.pdf)]


1. *Vu Lee and Sumit Gulwani.* 2014. [**FlashExtract: A Framework for Data Extraction by Examples**](http://msr-waypoint.com/en-us/um/people/sumitg/pubs/pldi14-flashextract.pdf) In PLDI'14.

    * **Optional Reading**: *Sumit Gulwani, José Hernández-Orallo, Emanuel Kitzelmann, Stephen H. Muggleton, Ute Schmid, and Benjamin Zorn* 2015 [**Inductive Programming Meets the Real World**](http://cacm.acm.org/magazines/2015/11/193326-inductive-programming-meets-the-real-world/fulltext) [[pdf version](http://cacm.acm.org/magazines/2015/11/193326-inductive-programming-meets-the-real-world/pdf)] In CACM'15.

1. *Marco D. Adelfio and Hanan Samet* 2013. [**Schema Extraction for Tabular Data on the Web**](http://www.vldb.org/pvldb/vol6/p421-adelfio.pdf) In VLDB'13.


### Questions:

1. How do Ground and Goods differ in goals and design? Can either one grow up to serve the goals of the other or are they fundamentally divergent?

2. Ground proposes that both graph data and usage (log) data are key to establishing context. Do you think a single storage system would be plausible for both? What might be a challenging task that requires looking at both kinds of data?

3. Google Goods has chosen a certain front-end usage scenario--what the Ground paper would refer to as "above-ground" applications. Do you think this is the right first choice for Google? For others? What other application scenarios would be worth pursuing, particularly in the context of the RISE lab?

4. Google Goods exists within the restricted Google ecosystem of applications, protocols and APIs. What research opportunities might arise in trying to work with 3rd-party systems?

4. The Gulwani CACM '15 article argues that Inductive Programming is particularly useful for "small data", where "the number of examples is small but the hypothesis space is large (Turing-complete)". How do you view that claim vis-a-vis other learning techniques we've seen? How does it relate to application scenarios we foresee in the RISE lab?

5. FlashExtract and the Adelfio/Samet work address similar problems but make different assumptions about user interaction. What are those differences? Do the techniques depend critically on their choices of inputs/outputs, and if so how? 


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



