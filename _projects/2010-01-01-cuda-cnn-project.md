---
title: 'CUDACNN Library'
subtitle: 'Convolutional Neural Networks library with GPU training support'
date: 2010-01-01 00:00:00
featured_image: '/images/projects/mnist.png'
---

![](/images/projects/cnn_matlab2.png)

CUDACNN (I'm not great at naming obviously) is an implementation of convolutional neural networks in C++ and CUDA with Matlab interface. If you're asking why would anyone write another GPU accelerated neural network library the answer is because well in 2008 there was none. 

#### History
I started working on implementation of the Convolutional NN in 2005 for my PhD. At that point the only implementation of ConvNets I knew of was in [Lush language](http://lush.sourceforge.net/). I didn't want to commit to a language with unclear future (sorry Yann) and frankly I wasn't that good at reading someone else's code at that time. Besides Matlab was really cool back then.

So I implemented purely Matlab version of the library that supported convolutional, pooling and fully connected layers with SGD and Levenberg-Marquardt training (back then it was a thing). It also had a nice UI showing training plots and visualizing MNIST recognition.
After trying few thing I realized that the inference speed is too slow for robotics applications, besides offline modeling.
Around that time I've learned about new cool thing called CUDA - acceleration of parallel computations with GPUs. So I've implemented GPU acceleration using CUDA v2 as Matlab mex files and later published it on [Matlabcentral](https://www.mathworks.com/matlabcentral/fileexchange/24291-cnn-convolutional-neural-network-class). Library turned out to be quite succesfull at one point getting into top 10 downloaded packages from Matlabcentral. 
Later I realized that having only Matlab API is not very convenient and implemented C++ version design of which was inspired by OpenCV.

Originally the library was published on [bitbucket](https://bitbucket.org/intelligenceagent/cudacnn-public/src/default/) and later I cloned it to the [github](https://github.com/sirotenko/cudacnn).

In 2013 proprietary version of the library was forked and used to build [automatic view planning for MRI](/project/automri) for Samsung.

#### CUDACNN Facts
* Library features
  * Training methods: Stochastic gradient, Stochastic Levenberg-Marquardt
  * Layers: Convolutional, Pooling (max, average), Fully-connected
  * Activation functions: Linear, Tansig, Tansig_mod (variance normalized version of tansig)
  * C++ and CUDA versions
  * Almost all dependencies are optional
  * Cross-platform: tested on Windows 7 64-bit, Ubuntu 12.04, Ubuntu 11.04
* Library used template template C++ construct to abstract away underlying hardware. Later this approach was used in some other NN libraries. I also gave [this answer on stackoverflow](https://stackoverflow.com/a/6726127/460436) about using template template which became fairly popular.
* Proprietary version of the library also supported unsupervised training approaches including [Predictive sparse decomposition](https://cs.nyu.edu/~yann/research/sparse/index.html).
* 50% of the code was written in the Moscow subway.
