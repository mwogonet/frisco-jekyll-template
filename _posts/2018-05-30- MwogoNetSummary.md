---
title: MwogoNet summary
date: 2018-05-30
description: Overview of entire process from data collection to application development.
categories:
  - General overview
image: https://mwogonet.github.io/images/1.jpg
author_staff_member: Gloria
---

As team, we went out there to the field to collect data on how cassava farmers and agricultural experts do cassava disease diagnosis. We figured that most,if not all farmers use their naked eyes to come to a conclusion on which disease the cassava crop is being affected with while the agricultural experts do take leaf or tuber samples  to the laboratory so as to carry out disease diagnosis.<br/>

We then decided to come up with an alternative i.e. the Mwogonet android mobile application platform that will be able to localize and classify common diseases in cassava crops such Cassava Mosaic Disease, Cassava Brown Streak Virus and Cassava Bacterial Blight based on the visual signs portrayed on the cassava leaves.<br/>
We also considered leaf segmentation using Enet to remove background noise.This gave us an option of training on both cropped and uncropped images to see how well the model learns for cropped images and uncropped images for the different diseases.<br/>
We used the pre-trained VGG16 Convolutional Neural Network(This model is trained on a subset of the ImageNet database which is used in the ImageNet Large-Scale Visual Recognition Challenge (ILSVRC).<br/><br/> The reason as to why we used VGG16 include;<br/> 
1. It can be trained on a large dataset therefore makes the model learn more.

2. The model has learned rich feature representations for a wide range of images.

3. Accuracy.The VGG16 model has blocks with same filter size applied multiple times to extract more complex and representative features making it more accurate.<br/> 

We trained on both the cropped and uncropped images for the diseased(Cassava Mosaic Disease, Cassava Bacterial Blight, Cassava Brown Streak Disease and Cassava Green mite Disease) as a whole versus healthy images to train the model on which leaves are diseased and which are not. We also trained it on a single disease versus the healthy and for each classification, we got different weights which reflect how well the model has learnt i.e.<br/>
Let X be the Performance(Categorical_accuracy).

1. X<60% - Bad

2. 61%<=X>=75% - Fairly Good

3. 76%<=X>=85% -Good

4. 86%<=X>=100% - Very Good

The above weights are then saved as an Hierachical Data Format (HDF) of which we saved ours using version 5 i.e. HDF5 file. We used the Hierachical Data Format because it is a set of file format that is designed to store and organize large amounts of data i.e.thousands of datasets can be stored in a single file.<br/>
In the HDF5 file,Metadata is stored in the form of user-defined, named attributes attached to groups and datasets.The groups are container structures which hold datasets while the datasets are multidimensional arrays of a homogeneous type.It is saved in the form "Final_weights_0.89.hdf5"
After getting the weights in the form of HDF5, we were required to deploy it on android and this could only be done by converting the h5 graph to a protocol Buffer(PB) file because running the model on android Tensorflow can be done using the ".pb" extension only.The graph is then frozen as a .pb and can be able run on android.<br/>
Kotlin programming language was then in android studio used to come up with the android interface and functionality. A simple report and manual are provided on the application to help farmers and agricultural experts use the MwogoNet application easily.
