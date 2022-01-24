---
layout: post
title:  Image Classification using Torchvision Pre-trained Models in a Single YonoArc Block
date:   2019-09-25 16:40:16
description: YonoHub series of tutorials which mimic the PyTorch for Beginners tutorials in a single reusable block.
tags: Image_Classification Torchvision
categories: Yonohub
---

<p align="center">
  <img src="https://cdn-images-1.medium.com/max/2724/1*4qKMqWYD401zdUPsptB8lA.jpeg" width="800px" title="Overview" alt="Overview">
</p>

Recently, I decided to learn how to implement machine learning (ML) algorithms, especially in the computer vision field, using the well-known package [**Pytorch**](https://pytorch.org). One of the useful resources, to break the ice with such a powerful ML package, is the [**PyTorch for Beginners**](https://www.learnopencv.com/learn-pytorch/) series of tutorials offered by [**Learn OpenCV**](https://www.learnopencv.com). The series contains some core topics that should be understood by the computer vision developers who are using Pytorch.

I follow the second tutorial with the title: [**PyTorch for Beginners: Image Classification using Pre-trained models**](https://www.learnopencv.com/pytorch-for-beginners-image-classification-using-pre-trained-models/). I am surprised by the amount of the architectures supported by the [**Torchvision**](https://pytorch.org/docs/stable/torchvision/index.html) module for image classification.
>  **Torchvision** package consists of popular datasets, model architectures, and common image transformations for computer vision. Basically, if you are into Computer Vision and using PyTorch, Torchvision will be of great help!

I thought it will be a beneficial idea to use YonoArc App in the [**YonoHub**](https://yonohub.com) platform to encapsulate all the supported image classification architectures, by torchvision package, in a single block. The developers will have the facility of using only one YonoArc block to evaluate and benchmark the different performances of the well-known classifiers with its pre-trained weights.
>  **YonoHub** is the first cloud-based system for designing, sharing, and evaluating complex systems, such as Autonomous Vehicles, ADAS, and Robotics. Yonohub features a drag-and-drop tool to build complex systems consisting of many blocks, a marketplace to share and monetize blocks, a builder for custom environments, and much more.

## How does the block work?

To have a good hand-on example, I use in the following demo the nuScenes dataset which can be streamed in the YonoArc pipeline using its supported player block. For more information about nuScenes-YonoArc package, you can read my previous article [here](https://medium.com/@ahmedmagdyattia1996/nuscenes-using-yonohub-to-develop-evaluate-and-benchmark-over-the-cloud-94c06685c168).

<p align="center">
  <img src="https://cdn-images-1.medium.com/max/2592/1*Otk5RtkP7NVDhZ-qYBtUAA.jpeg" width="800px" title="Image Classification Demo" alt="Image Classification Demo">
</p>

<p align="center">
	Image Classification Demo
</p>

**Torchvision Image Classifier** YonoArc block has one input which intuitively of type Image. The source of the input images is the **nuScenes Dataset Player** as shown above. On the other hand, the block has two different outputs. The first output port is an image after writing the classes that the model is certain about. The other port is the classes associated with its confidence that the model predicted. The type of this output port is a custom ROS message which is included in the [**perception_msgs**](https://gitlab.yonohub.com/AhmedHendawy/perception-msgs) package I implemented for interacting with the YonoArc blocks in the field of computer vision.

The image classifier block has a property of choosing the model which you want to evaluate. As shown below, you have a drop list, under the title **Model** **Options, **with 31 different image classification models. You can reach this drop list by clicking on the setting icon of the block.

<p align="center">
  <img src="https://cdn-images-1.medium.com/max/2594/1*fHJC3qdYWbYsa7ae0U35Cg.png" width="800px" title="Image Classification Model Options" alt="Image Classification Model Options">
</p>

<p align="center">
	Image Classification Model Options
</p>

One great thing about YonoArc is that each block can use different resource models in the same pipeline. For example, the image classifier block uses GPU as a resource model. However, an eight-core CPU is the resource model of both the nuScenes player and the video viewer blocks.

## Source Code

During the implementation of the presented block, I make use of the LearnOpenCV tutorial code. I manipulate it to be general and suitable for the YonoArc blocks code structure. [**YonoHub Docs**](https://docs.yonohub.com) is very useful to understand how to make a python 3 API YonoArc block. You can read this [part](https://docs.yonohub.com/docs/yonohub/yonoarc/yonoarc-python3-api/) of the docs to understand the changes happen to the tutorial code. You can check the source code below,

 <script src="https://gist.github.com/AhmedMagdyHendawy/a002b062dcde6d3111257019b62dfad4.js"></script>

## Results

After running the above pipeline, the below results have been produced. AlexNet model is chosen to predict the shown estimated classes.

<p align="center">
  <img src="https://cdn-images-1.medium.com/max/2000/1*-lvQb1kJ4zxnLdBR3CTnkw.gif" width="800px" title="Image Classification Results" alt="Image Classification Results">
</p>

<p align="center">
	Image Classification Results
</p>

Finally, I tried to demonstrate how to use YonoArc App in the YonoHub platform to implement the image classification tutorial by Learn OpenCV. Merging the benefits of both Pytorch, especially Torchvision, and YonoArc App to have an encapsulated image classification library of models in the shape of a block. You can purchase the **Torchvision Image Classifier** block for free, through [**YonoStore**](https://store.yonohub.com/product/torchvision-image-classifier/), and try the different models available without dealing with the code details. In addition, you can clone the above source code from [here](https://gitlab.yonohub.com/AhmedHendawy/torchvision_image_classifier) to reuse it for such blocks. Follow the steps in the referred [tutorial](https://docs.yonohub.com/docs/yonohub/tutorials/custom-python3-block/) to learn how to implement a YonoArc block.

Next, I will work on the semantic segmentation tutorial to have a similar reusable YonoArc block. It’s easy to try out Yonohub. New users receive $25 free credits. Sign up on [Yonohub](https://yonohub.com/)!
