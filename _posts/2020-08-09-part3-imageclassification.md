---
layout: post
title:  Part 3 - Model Testing — Image Classification with YonoHub & Tensorflow V2.0 Series
date:   2020-08-09 16:40:16
description: Developing effective deep learning is not an easy task. The deep learning researchers are competing to benchmark their models against many datasets. One can design an object detection model for…
tags: Image_Classification Tensorflow
categories: Yonohub
---

<p align="center">
  <a href="https://algotrading101.com/learn/what-is-overfitting-in-trading/"><img src="https://cdn-images-1.medium.com/max/2000/1*LC0B80A8Y6Y-YjxQ-J5MbQ.png" width="800px" title="Tensorflow Series" alt="Tensorflow Series"></a>
</p>

Developing effective deep learning is not an easy task. The deep learning researchers are competing to benchmark their models against many datasets. One can design an object detection model for autonomous driving and benchmark it against Kitti, nuScenes, Waymo, etc.… Another one creates an image classification model and makes sure to achieve high performance against COCO, ImageNet, etc.… But why is that?

Actually, it is not for a single reason; however, there is a motive, which drives all these eager researchers, which is reaching the generality of their model. To have a model that is not locally optimally according to the trained data provided is the target.

Various problems need to be tackled to reach such a performance. One common challenge which is famous in the machine learning/ deep learning community is the overfitting. Your model is too complicated to the extend of memorizing all the answers from your training dataset.

Many solutions have been provided to solve such an issue, starting from having much bigger data to regulate your training loop. However, a first step before solving the problem is to know how to detect it. As the chief needs to taste their food before serving, the deep learning developer needs to check the overfitting before serving the model as a solution for the targeted problem. Testing the model on a separated unseen dataset is the way to do so. If your model performs on the test dataset roughly similar, in terms of accuracy, on the training one, you are ready to go.

This is why in this tutorial we wanted to cover how to do testing using a test split unseen by our trained model. Using the same pipeline from the previous [tutorial](https://medium.com/yonohub/part-2-model-implementation-training-image-classification-with-yonohub-tensorflow-v2-0-f74e72878e77) with some slight changes discussed below to validate our model and check if there is overfitting or not.

In this series of tutorials, we will go through a deep learning journey, especially for **Image Classification**, starting from streaming a dataset till the deployment. The tutorials cover how to use Tensorflow in Yonohub by using the blocks offered within YonoArc for a fast and easy way of development and deployment.

## Upgrading the Model YonoArc block

The training loop in YonoArc is divided into a dataset player and a model. Each implemented and encapsulated within a block. Similar to the previous tutorial the dataset player publishes the CIFAR-10 dataset continuously in batches with a specific frame rate. Previously, we chose the train split, however, this time a test split will be selected instead.

The model block was by default operated in a training mode. A droplist is provided to select the operating mode of the model either for training or testing. For the newly added testing mode, we add similar functions for the block’s source code, *testing*, and *test_step* function as shown below,

<script src="https://gist.github.com/AhmedMagdyHendawy/eeccf2cc2ac39fa5571bbd546652b258.js"></script>

The functions are similar to the normal functions used by TensorFlow in addition to some pieces of code to publish the results to the user in terms of an INFO alert as well as port messages. We used the model parameters trained from the previous tutorial to be loaded and ready for testing.

## TensorFlow Testing in Yonohub

You can follow the next video tutorial to replicate the steps required to perform the testing loop. However, you can download the .arc file of the pipeline and open it in YonoArc, from [here](https://github.com/YonoHub/Model-Testing), directly without worrying about even setting the above parameters. Although, you need to freely purchase all the blocks used in the article from YonoStore.

<p align="center">
  <a href="https://www.youtube.com/watch?v=qDcUm8kyZQE"><img src="http://img.youtube.com/vi/qDcUm8kyZQE/0.jpg" width="800px" title="Tensorflow Testing in Yonohub
" alt="Tensorflow Testing in Yonohub
"></a>
</p>

<p align="center">
	Tensorflow Testing in Yonohub

</p>

## Conclusion

As the above video tutorial demonstrates, the percentage of the testing is approximately 71% which is very close to training accuracy from the previous tutorial. Now, our model is ready to be deployed on hardware to be tested in a real-life scenario.

Using Yonoarc for testing facilitates the idea of validating your model against different real-life datasets by just replacing the Image Classification Dataset Player by any other dataset player to cover a larger distribution of data during testing of your trained model.

## About Yonohub
>  *Yonohub is a web-based cloud system for development, evaluation, integration, and deployment of complex systems, including Artificial Intelligence, Autonomous Driving, and Robotics. Yonohub features a drag-and-drop tool to build complex systems, a marketplace to share and monetize blocks, a builder for custom development environments, and much more. YonoHub can be deployed on-premises and on-cloud.*

Get $25 free credits when you sign up now. For researchers and labs, contact us to learn more about Yonohub sponsorship options.

If you liked this article, please consider following us on Twitter at [@yonohub](https://twitter.com/YonoHub), [email us directly](mailto:info@yonohub.com), or [find us on LinkedIn](https://www.linkedin.com/showcase/yonohub). I’d love to hear from you if I can help you or your team with how to use Yonohub.

## References

[1] [https://www.tensorflow.org/tutorials/images/cnn](https://www.tensorflow.org/tutorials/images/cnn)

## References

[1] [https://www.tensorflow.org/tutorials/images/cnn](https://www.tensorflow.org/tutorials/images/cnn)
