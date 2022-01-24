---
layout: post
title:  Using YonoHub to Participate in the nuScenes Tracking Challenge
date:   2019-12-02 16:40:16
description: The nuScenes package, in YonoArc, facilitates the participation in the nuScenes Tracking Challenge.
tags: nuScenes Object_Tracking
categories: Yonohub
---

<p align="center">
  <a href="https://www.youtube.com/watch?v=6qslqVRR2kM"><img src="http://img.youtube.com/vi/6qslqVRR2kM/0.jpg" width="800px" title="nuScenes Package Overview" alt="nuScenes Package Overview"></a>
</p>

<p align="center">
	nuScenes Package Overview
</p>

A large-scale dataset, which is called [nuScenes](https://www.nuscenes.org), was published by Aptiv Autonomous Mobility (formerly nuTonomy) on the 27th of March 2019, to help the autonomous driving community during the development, and evaluation stages. nuScenes dataset is one of the most promising datasets which facilitate the developing of new autonomous driving algorithms for 3D object detection and 3D object tracking as well.

Consequently, the nuScenes team organized a [3D Object Detection Challenge](https://www.nuscenes.org/object-detection?externalData=all&mapData=all&modalities=Any) at the last CVPR conference. This challenge aimed to motivate the developers, in the field of the autonomous driving, to benchmark their 3D object detections algorithm against the nuScenes dataset.

After the success of the 3D Object Detection challenge, another challenge is recently organized for [3D Object Tracking](https://www.nuscenes.org/tracking?externalData=all&mapData=all&modalities=Any). It will be held during the next NIPS conference.

At the same time, the [YonoHub](https://yonohub.com/) team has created a nuScenes package that can be used inside the YonoHub platform. The package is in the form of blocks that encapsulate specific functions. The package is used within the main YonoHub application, [YonoArc](https://yonohub.com/yonoarc/). In addition, the nuScenes dataset is available as an extracted version on this cloud-based platform, you do not need to download the dataset with this huge size. You can freely purchase the dataset from [YonoStore](https://store.yonohub.com) as well as all the nuScenes package blocks.

Accordingly, the nuScenes package became a new method to benchmark your algorithm against the nuScenes dataset for the upcoming nuScenes Tracking Challenge. Just by drag and drop some blocks, you will be able to interact with the dataset.

In addition to the blocks, Yonohub provides sponsored credits (up to $1000) to work on nuScenes 3D Tracking Challenge. Apply using [this form](https://yonohub.com/nuscenes-package-and-sponsorship/) to receive the sponsored credits directly in your account.

Let’s discuss how can you start working with the package!

## How does it work?

As a first step, you need to get the nuScenes dataset as well as the nuScenes blocks for YonoArc development. YonoStore is the place where you can purchase a dataset, block, or even environment. There are different datasets other than nuScenes, for example, Kitti Dataset, Comma.ai, etc..

After purchasing the assets, you will find the nuScenes Dataset in your YonoStoreDataset folder, however, the nuScenes blocks in your YonoArc blocks.

The nuScenes package enriches of different kinds of blocks. The last update of the package consists of 10 blocks as listed below,

* **Dataset Player**: used to stream all the sample data for all kinds of sensors as well as the metadata of the nuScenes dataset.

* **Sample Annotations to Eval Boxes**: used to convert the sample annotation box format to eval box format.

* **Boxes Frame Transformer**: used to transform the reference frame of the boxes to another one.

* **Lidar Point Cloud Converter**: ****used to convert the reference frame of the lidar point cloud from nuScenes lidar frame to Kitti lidar frame or vice versa.

* **Eval Boxes Preprocessing**: ****used to perform the preprocessing over the eval boxes before the evaluation process.

* **Predictions Appender**: used to append/ batch all the predicted boxes as a JSON file for submission.

* **Predictions Loader**: used to load the results saved as JSON file for the evaluation/visualization process.

* **Tracking Benchmark**: used to perform the tracking evaluation bench-marking of the predicted boxes against the ground truth boxes from the dataset.

* **Boxes to Markers**: used to convert the boxes to markers format for proper visualization in [Rviz](http://wiki.ros.org/rviz) (Purchase Rviz block from YonoStore).

* **Draw 3D Boxes**: used to draw the boxes over one of the camera output images.

NOTE: To learn more about the block’s settings, functionality, as well as input/output ports, check the description associated with the item in YonoStore or through the Help tab in the block’s settings in YonoArc.

After reading the brief description of each block in the package, we need to illustrate how to use it in YonoArc. We can check the following series of tutorial videos which are very useful to understand the bench-marking cycle in YonoArc. For a more detailed description regarding the following tutorials, please read the corresponding tutorial in the [docs](https://docs.yonohub.com/docs/yonohub/nuscenes-package/).

### Getting Started with nuScenes

In this tutorial, we learn how to interact with the nuScenes dataset through the Dataset Player block. Streaming the raw images of one of the dataset’s camera sensors and visualize it using the Dashboard in YonoArc.

<p align="center">
  <a href="https://www.youtube.com/watch?v=jLYU5-gqp9Y"><img src="http://img.youtube.com/vi/jLYU5-gqp9Y/0.jpg" width="800px" title="Tutorial 1: Getting Started with nuScenes
" alt="Tutorial 1: Getting Started with nuScenes"></a>
</p>

<p align="center">
	Tutorial 1: Getting Started with nuScenes
</p>

### Visualize the nuScenes Dataset

In this tutorial, we deal with the different visualization methods, which are offered through the nuScenes package in YonoArc. At the end of this tutorial, you learn how to,

* Draw the 3D Ground Truth Boxes on the raw images captured by Camera sensors.

* Visualize the Radar/Lidar point cloud in Rviz with a different number of sweeps.

* Convert the 3D Ground Truth Boxes to [Markers](http://docs.ros.org/melodic/api/visualization_msgs/html/msg/Marker.html) to visualize it in Rviz on the top of the Lidar point cloud.


<p align="center">
  <a href="https://www.youtube.com/watch?v=XWoKT2rp1ck"><img src="http://img.youtube.com/vi/XWoKT2rp1ck/0.jpg" width="800px" title="Tutorial 2: Visualize the nuScenes Dataset" alt="Tutorial 2: Visualize the nuScenes Dataset"></a>
</p>

<p align="center">
	Tutorial 2: Visualize the nuScenes Dataset
</p>

### Predict and Save Your Results

In this tutorial, you take your first steps regarding the involvement in the nuScenes Tracking Challenge. At the end of this tutorial, you learn how to,

* Load the detection results of one of the [supported algorithms](https://www.nuscenes.org/tracking/#baselines) by the nuScenes Challenge, for example, MEGVII.

* Use a pre-implemented tracking algorithm like AB3DMOT. You can develop your own algorithm as a YonoArc block using [this](https://docs.yonohub.com/docs/yonohub/tutorials/custom-python3-block/) tutorial.

* Append your results after doing the preprocessing stage as a JSON file with the same nuScenes Tracking Challenge format.

NOTE: You can purchase the AB3DMOT tracking algorithm from YonoStore.

<p align="center">
  <a href="https://www.youtube.com/watch?v=ZZEltqiXgao"><img src="http://img.youtube.com/vi/ZZEltqiXgao/0.jpg" width="800px" title="Tutorial 3: Predict and Save Your Results
" alt="Tutorial 3: Predict and Save Your Results
"></a>
</p>

<p align="center">
	Tutorial 3: Predict and Save Your Results
</p>


### Benchmark Your Tracking Algorithm

In this final tutorial, we construct an evaluation/bench-marking loop for the challenge. At the end of this tutorial, you learn how to,

* Load your own tracking results from the previous tutorial.

* Benchmark your algorithm against the nuScenes Dataset.

<p align="center">
<a href="https://www.youtube.com/watch?v=nCp-T6JIynw"><img src="http://img.youtube.com/vi/nCp-T6JIynw/0.jpg" width="800px" title="Tutorial 4: Benchmark Your Algorithm" alt="Tutorial 4: Benchmark Your Algorithm"></a></p>

<p align="center">
    Tutorial 4: Benchmark Your Algorithm
</p>

NOTE: You can find all the previous YonoArc pipelines in [this](https://gitlab.yonohub.com/YonoTeam/nuscenes_package_tutorials) repository.

## Conclusion

Finally, you are ready to participate in the nuScenes Tracking Challenge with an easy-to-use drag and drop interface. You do not need to download this huge sized dataset on your local machine, just freely purchase the dataset and you get it in no time. All the development can be done on YonoHub using different machine capabilities.

It’s easy to try out Yonohub. New users receive $50 free credits. For nuScenes Challenges, Yonohub provides sponsored credits (up to $1000) to work on nuScenes 3D Tracking Challenge. Apply using [this form](https://yonohub.com/nuscenes-package-and-sponsorship/) to receive the sponsored credits directly in your account. Sign up on Yonohub!
