---
layout: page
title: "Prediction Serving"
description: "Prediction Serving"
use_math: true
---

![ML-Lifecycle](assets/images/ml-lifecycle.jpg){:width="400px"}

While much of the focus of machine learning research is on the process of training models (i.e., learning) there are a unique set of challenges around the process of serving and updating those models that is often overlooked.  In this lecture we will explore the bigger machine learning life-cycle and discuss the challenges around serving predictions.

## Reading lists:

### Prediction Serving Systems [Daniel Crankshaw]

1. *Deepak Agarwal, Bo Long, Jonathan Traupman, Doris Xin, and Liang Zhang.* 2014. [**LASER: a scalable response prediction platform for online advertising.**](http://dl.acm.org/citation.cfm?id=2556252) In Proceedings of the 7th ACM international conference on Web search and data mining (WSDM '14). [[direct pdf link](http://dl.acm.org/ft_gateway.cfm?id=2556252&ftid=1432320&dwn=1&#URLTOKEN#)]

#### Optional Reading

1. *Daniel Crankshaw, Xin Wang, Giulio Zhou, Michael J. Franklin, Joseph E. Gonzalez, Ion Stoica* [**Clipper: A Low-Latency Online Prediction Serving System**](assets/papers/clipper_latest_draft_nsdi.pdf). This paper is still under review.

1. *Daniel Crankshaw, Peter Bailis, Joseph E. Gonzalez, Haoyuan Li, Zhao Zhang, Michael J. Franklin, Ali Ghodsi, Michael I. Jordan* [**The Missing Piece in Complex Analytics: Low Latency, Scalable Model Management and Serving with Velox**](http://arxiv.org/abs/1409.3809). The Conference on Innovative Database Research (CIDR'2015).

1. Mert Akdere, Ugur Cetintemel, Matteo Riondato, Eli Upfal, and Stan Zadonic. [**The Case for Predictive Database Systems: Opportunities and Challenges**](http://cidrdb.org/cidr2011/Papers/CIDR11_Paper20.pdf). The Conference on Innovative Database Research (CIDR'2011).

### Managing the ML Lifecycle [Giulio Zhou]

1. *D. Sculley, Gary Holt, Daniel Golovin, Eugene Davydov, Todd Phillips, Dietmar Ebner, Vinay Chaudhary, Michael Young* 2014. [**Machine Learning: The High Interest Credit Card of Technical Debt**](http://research.google.com/pubs/pub43146.html). SE4ML: Software Engineering for Machine Learning (NIPS 2014 Workshop) [[direct pdf link](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43146.pdf)]

#### Optional Reading

1. *Xinran He, Junfeng Pan, Ou Jin, Tianbing Xu, Bo Liu, Tao Xu, Yanxin Shi, Antoine Atallah, Ralf Herbrich, Stuart Bowers, and Joaquin Quiñonero Candela.* 2014. [**Practical Lessons from Predicting Clicks on Ads at Facebook.**](http://dl.acm.org/citation.cfm?id=2648589) In Proceedings of the Eighth International Workshop on Data Mining for Online Advertising (ADKDD'14). [[direct pdf link](https://pdfs.semanticscholar.org/daf9/ed5dc6c6bad5367d7fd8561527da30e9b8dd.pdf)]

1. *H. Brendan McMahan, Gary Holt, D. Sculley, Michael Young, Dietmar Ebner, Julian Grady, Lan Nie, Todd Phillips, Eugene Davydov, Daniel Golovin, Sharat Chikkerur, Dan Liu, Martin Wattenberg, Arnar Mar Hrafnkelsson, Tom Boulos, and Jeremy Kubica.* [**Ad click prediction: a view from the trenches.**](http://dl.acm.org/citation.cfm?id=2488200) In Proceedings of the 19th ACM SIGKDD international conference on Knowledge discovery and data mining (KDD '13) [[direct pdf link](https://www.eecs.tufts.edu/~dsculley/papers/ad-click-prediction.pdf)]

### Prematerialized Predictions [Noah Golmant]

1. *M. Levent Koc and Christopher Re* 2014. [**Incrementally Maintaining Classification Using an RDBMS**](http://dl.acm.org/citation.cfm?id=1952380) Proc. VLDB Endow. 4, 5 (February 2011).[[direct pdf link](http://www.cs.stanford.edu/people/chrismre/papers/hazy-classification-vldb11.pdf)]

### Additional Optional Reading:

1. **Cascades for fast predictions:** Paul Viola and Michael Jones [**Rapid Object Detection using a Boosted Cascade of Simple Features**](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/viola-cvpr-01.pdf) CVPR 2001.

   * This landmark paper introduced a simple but efficient and accurate algorithm for face detection which is widely used.  I have included this class paper because illustrates the advantages of cascades.

   * Viola and Jones inspired later work by David Weiss and Ben Taskar in the design of [**Structured prediction cascades**](http://homes.cs.washington.edu/~taskar/pubs/aistats10cascades.pdf) which address the challenges of graphical model inference.

1. **Speech recognition:** *Xuedong Huang, James Baker, Raj Reddy* [**A Historical Perspective of Speech Recognition**](http://cacm.acm.org/magazines/2014/1/170863-a-historical-perspective-of-speech-recognition/fulltext).  This survey summarizes the development in speech recognition, an actively deployed area of prediction serving.  Unfortunately, while the article does discuss the key developments in speech recognition it only briefly discuss some of the developments in serving speech recognition models.

   * *Baidu Research* [**Deep Speech 2: End-to-End Speech Recognition in English and Mandarin**](https://arxiv.org/abs/1512.02595).  This is a fairly comprehensive description of both the model and systems used by Baidu for their English and Mandarin ASR systems.  To the best of my knowledge this is the most complete public description of a state-of-the-art ASR system.

   * *Anuj Kumar, Anuj Tewari, Seth Horrigan, Matthew Kam, Forian Metze, and John Canny* [**Rethinking Speech Recognition on MObile Devices**](http://repository.cmu.edu/cgi/viewcontent.cgi?article=1122&context=lti).  This paper explores the challenges of speech recognition in the developing world on mobile devices with limited connectivity.

   * Hosted speech service [**Google's Cloud Speech API**](https://cloud.google.com/speech/).  Any papers on this system???


## Questions

<iframe src="https://docs.google.com/a/berkeley.edu/forms/d/e/1FAIpQLSc2oIL3H-1WcC10VJDKqK-2wab-U1YEubunNx6x8eVbRDAAkQ/viewform?embedded=true" width="760" height="600" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>




<!-- {: style="text-align: center"} -->



