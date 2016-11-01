---
layout: page
title: "Deep Learning"
description: "Deep Learning"
use_math: true
---

This lecture will cover an overview of developments in deep learning and then we will dive into several recent papers on developments in deep learning related to convolutional networks, model compression, time-series modeling, and distributed deep learning.

### Lecture Slides:

1. Joseph Gonzalez *Overview of Deep Learning* [[pptx](assets/slides/overview_of_deep_learning_final.pptx)][[pdf](assets/slides/overview_of_deep_learning_final.pdf)]

   * TensorFlow Example [[direct link](assets/slides/two_hidden_layers_tensorflow_example.ipynb)][[view](https://github.com/ucbrise/cs294-rise-fa16/blob/gh-pages/assets/slides/two_hidden_layers_tensorflow_example.ipynb)]

   * Symbolic Algebra [[direct link](assets/slides/symbolic_algebra.ipynb)][[view](https://github.com/ucbrise/cs294-rise-fa16/blob/gh-pages/assets/slides/symbolic_algebra.ipynb)]

1. Francois Belletti *Principles of Neural Network Design*  [[pdf](assets/slides/principles_of_neural_network_design.pdf)]

1. Xin Wang *Deep Model Compression* [[pdf](assets/slides/ModelCompression_RISE.pdf)]

1. Sammy Sidhu *Scalable Deep Learning* [[pdf](assets/slides/scalable_deep_learning_cs294.pdf)]



---

# Notes

For those who want a good introduction to big ideas in deep learning checkout the following links:

1. The Stanford [CS231n Convolutional Neural Networks for Visual Recognition](http://cs231n.stanford.edu) course has excellent [Exercises and Tutorials](http://cs231n.github.io) and some good [slides](http://cs231n.stanford.edu/syllabus.html) as well.
   1. [Linear Regression and Softmax](http://cs231n.github.io/linear-classify/)
   1. [Gradient Descent](http://cs231n.github.io/optimization-1/)
   1. [Backpropagation as Dynamic Programming](http://cs231n.github.io/optimization-2/)
   1. [Network Architecture and Terminology](http://cs231n.github.io/neural-networks-1/)
   1. [Convolution](http://cs231n.github.io/convolutional-networks/)


1. Chris Olah's blog has some good tutorials as well:
   1. [Backpropagation](http://colah.github.io/posts/2015-08-Backprop/)
   1. [Types of Neural Networks](http://colah.github.io/posts/2015-09-NN-Types-FP/)
   1. [Recurrent Neural Networks and LSTMs](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) and [More advanced RNNs and Turing Machines](http://distill.pub/2016/augmented-rnns/)
   1. [Convolutional Networks](http://colah.github.io/posts/2014-07-Conv-Nets-Modular/)


1. The WildML Blog and [Glossary](http://www.wildml.com/deep-learning-glossary/)
   1. [Recurrent Neural Networks](http://www.wildml.com/2015/09/recurrent-neural-networks-tutorial-part-1-introduction-to-rnns/)



## Reading List:

### Important Neural Architectures [Francois Belletti]

1. *Alex Krizhevsky, Ilya Sutskever, and Geoffrey E. Hinton* [**ImageNet Classification with Deep Convolutional Neural Networks**](http://papers.nips.cc/paper/4824-imagenet-classification-w), NIPS'12.

1. Blog post. [Recurrent Neural Networks and LSTMs](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)


#### Optional Reading

1. *Y. LeCun, B. Boser, J. S. Denker, D. Henderson, R. E. Howard, W. Hubbard, and L. D. Jackel.* [**Backpropagation applied to handwritten zip code recognition**](http://yann.lecun.org/exdb/publis/pdf/lecun-89e.pdf). Neural Comput. 1, 4 (December 1989)


1. *Szegedy et al.* [**Going Deeper with Convolutions**](https://www.cs.unc.edu/~wliu/papers/GoogLeNet.pdf), CVPR'15.
   There is also a shorter [inception blog post](https://research.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html).

1. *Jiquan Ngiam, Aditya Khosla, Mingyu Kim, Juhan Nam, Honglak Lee, and Andrew Y. Ng* [**Multimodal Deep Learning**](http://www.andrewng.org/portfolio/multimodal-deep-learning/), ICML'11.

1. *Nitish Srivastava, Geoffrey Hinton, Alex Krizhevsky, Ilya Sutskever, and Ruslan Salakhutdinov.* [**Dropout: A Simple Way to Prevent Neural Networks from Overfitting**](http://www.jmlr.org/papers/volume15/srivastava14a.old/source/srivastava14a.pdf), JMLR'14.

1. *Shaoqing Ren, Kaiming He, Ross Girshick, and Jian Sun.* [**Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks**](http://papers.nips.cc/paper/5638-faster-r-cnn-towards-real-time-object-detection-with-region-proposal-networks), NIPS'15.

1. *Felix A. Gers, Jürgen A. Schmidhuber, and Fred A. Cummins.* [**Learning to Forget: Continual Prediction with LSTM.**](ftp://ftp.idsia.ch/pub/juergen/FgGates-NC.pdf) Neural Comput. 12, 10 (October 2000), 2451-2471.

1. *Junyoung Chung, Caglar Gulcehre, KyungHyun Cho, Yoshua Bengio* [**Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling**](https://arxiv.org/abs/1412.3555), NIPS'14 Deep Learning Workshop.




### Scalable Training Systems [Sammy Sidhu]

1. *Martín Abadi et al.* [**TensorFlow: Large-Scale Machine Learning on Heterogeneous Distributed Systems**](https://arxiv.org/abs/1603.04467), arXiv only 2016.

#### Optional Reading

1. *Martín Abadi et al.* [**TensorFlow: A system for large-scale machine learning**](https://arxiv.org/abs/1605.08695), arXiv only 2016.

1. For those interested in learning more about TensorFlow checkout the [tutorials](https://www.tensorflow.org/versions/r0.11/tutorials/index.html).

1. *Forrest N. Iandola, Khalid Ashraf, Matthew W. Moskewicz, and Kurt Keutzer* [**FireCaffe: near-linear acceleration of deep neural network training on compute clusters**](https://arxiv.org/abs/1511.00175) CVPR 2016. [[Forrest's Slides](https://cs.stanford.edu/~jhoffman/yahooJapan_Mar2016_talks/Forrest_FireCaffe_Yahoo_2016-03-20.pdf)], arXiv only

1. [**Caffe Tutorial**](http://caffe.berkeleyvision.org/tutorial/)





### Model Quantization and Compression [Xin Wang]

1. *Geoffrey Hinton, Oriol Vinyals, Jeff Dean* [**Distilling the Knowledge in a Neural Network**](https://arxiv.org/abs/1503.02531), ICLR'16.

#### Optional Reading

1. *Song Han, Huizi Mao, William J. Dally* [**Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding**](https://arxiv.org/abs/1510.00149), ICLR'16.


1. *Wenlin Chen, James T. Wilson, Stephen Tyree, Kilian Q. Weinberger, Yixin Chen* [**Compressing Neural Networks with the Hashing Trick**](https://arxiv.org/abs/1504.04788), ICML 15.


1. *Forrest N. Iandola, Song Han, Matthew W. Moskewicz, Khalid Ashraf, William J. Dally, Kurt Keutzer* [**SqueezeNet: AlexNet-level accuracy with 50x fewer parameters and <0.5MB model size**](https://arxiv.org/abs/1602.07360) arXiv only





### Questions

<iframe src="https://docs.google.com/a/berkeley.edu/forms/d/e/1FAIpQLSdeBCh5tunG5L5Aa2HKagsmDohmUMNP90MmKIuCdtPiOM0nmw/viewform?embedded=true" width="760" height="500" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>



<!--
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



