---
layout: post
title:  "Convolutional neural network class"
date:   2019-10-01 01:41:36 +0500
image:  /public/images/projects/cnn.jpg
---

## Notice

This version of convolutional neural network library is the old one and implemented mostly in pure Matlab. And it's not developed for a long time. The most recent version writen on C++/CUDA with Matlab wrapper can be found [here](https://sites.google.com/site/mihailsirotenko/projects/cuda-cnn?authuser=0).

![](/public/images/pictures/cnn-picture.png)

## Project descriprion

This project provides matlab class for implementation of convolutional neural networks. This networks was created by Yann LeCun and have sucessfully used in many practical applications, such as handwritten digits recognition, face detection, robot navigation and others (see references for more info). Because of some architectural features of convolutional networks, such as weight sharing it is imposible to implement it using Matlab Neural Network Toolbox without it's source modifications. That's why this class works almost independently from NN toolbox (coming soon full independence).

This release includes sample of handwritten digits recognition using CNN. If you just want to try it run cnet_tool. You'll see a simple GUI. It loads pretrained convolutional neural net from cnet.mat and recognizes image of digit either painted in painting area or downloaded from MNIST database.

The significant improovement in the latest version is a presence of cudacnn mex-file, which speeds up the training up to 44 times using NVidia's CUDA technology.You'll need a CUDA-capable graphic card and CUDA SDK. The source of cudacnn.mex is not included by now, but I plan to do It in future. Currently only stochastic gradient is supported by CUDA-training, but Hessian approximation is going to be soon also.

If you interested in training you should open train_cnn.m, set all parameters following to comments and start learning by runing it.

The action sequence for creation of arbitrary convolutional neural network is following:

1. Create cnn object.
2. Set archtecture (number of layers, weights, training parameters, etc).
3. Call init method.
4. Define connection matrices for layers if necessary.
5. Load training data.
6. Preprocess training data.
7. Start training.
8. Test neural net.

There're several limitations in current version:
1. Network can have only one input for image (e.g. no stereo images simulateously).
2. You have to set connection matrix after the initialization.
3. MNIST database of handwriten digits not included in this distribution, you can download it from [here](http://yann.lecun.com/exdb/mnist/index.html)

References:
1. Y. LeCun, L. Bottou, G. Orr and K. Muller: Efficient BackProp, in Orr, G. and Muller K. (Eds), Neural Networks: Tricks of the trade, Springer, 1998 URL: [yann.lecun.com](http://yann.lecun.com/exdb/publis/index.html)
2. Y. LeCun, L. Bottou, Y. Bengio and P. Haffner: Gradient-Based Learning Applied to Document Recognition, Proceedings of the IEEE, 86(11):2278-2324, November 1998 URL: [yann.lecun.com](http://yann.lecun.com/exdb/publis/index.html)
3. Patrice Y. Simard, Dave Steinkraus, John C. Platt: Best Practices for Convolutional Neural Networks Applied to Visual Document Analysis URL: [research.microsoft.com](http://research.microsoft.com/apps/pubs/?id=68920)
4. Thanks to Mike O'Neill for his great article, wich is summarize and generalize all the information in 1-3 for better understandig for programming: URL: [www.codeproject.com](http://www.codeproject.com/KB/library/NeuralNetRecognition.aspx)
5. Also thanks to Jake Bouvrie for his "Notes on Convolutional Neural Networks", particulary for the idea to debug the neural network using finite differences URL: [web.mit.edu](http://web.mit.edu/jvb/www/cv.html)


News and some interesting information about this project in my blog: [aisirotenko.blogspot.com](http://aisirotenko.blogspot.com/)
Note that a problems was reported when using CudaCNN with CUDA driver ver 3.0. So it's recomended to use 2.3 version.

## Changes log

#### Ver 0.8:
New features:
- cudacnn function added, providing support of CUDA-accelerated simulation and training of convolutional neural networks;
- GUI added, providing RMSE, MCR plots, training and Hessian calculation progress bars, etc;
- Ability to choose from 3 training modes added, including stochastic gradient, Hessian running estimate calculation and batch Hessian calculation(!);
- Added version of cnn_tool improoved by Nikolay Chumerin (submission #25247);

Bug fixes:
- Class constructor can create cnn objec from struct;
- Extra FLayer creation fixed;
- In MNIST training exaple fixed the number of kernels in 4th layer.

#### Ver 0.72:
- Sample GUI added, demonstrating use of convolutional network for handwriten digits recognition.
- Training runs 20% faster. 

#### Ver 0.71: 
Bug fix:
- training was stoping after 1 epoch.

#### Ver 0.70: 
- First release.

## To do list
- Add support of RBF functions
- Speed up training by change the way Hessian is computed
- Add NORB dataset example
- Add arbitrary inputs number support
- Add separete subsampling rate for x and for y

## Downloads
Version 0.8
Version 0.72 

This lib on matlabcentral: [mathworks.com](http://www.mathworks.com/matlabcentral/fileexchange/24291-cnn-convolutional-neural-network-class)

## Additional files

Because matlabcentral do not allows to include mex-files into submission, you'll be not able to use CUDA for the class downloaded from there. Here you can download these files:
- For Win32
- For Win64
- For Linux32