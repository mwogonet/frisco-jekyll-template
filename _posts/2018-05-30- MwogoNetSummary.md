
---

title: MwogoNet Summary
date: 2018-05-30
description: Overview of entire process from data collection to Application development.
categories:
  - General overview
image: https://www.dropbox.com/s/ef0e4h8qjc2tomd/env_effect.png
author_staff_member: Gloria

---

As team, we went out there to the field to collect data on how cassava farmers and agricultural experts do cassava disease diagnosis. We figured that most,if not all farmers use their naked eyes to come to a conclusion on which disease the cassava crop is being affected with while the agricultural experts do take leaf or tuber samples  to the laboratory so as to carry out disease diagnosis.<br/>
We then decided to come up with an alternative i.e. the Mwogonet android mobile application platform that will be able to localize and classify common diseases in cassava crops such Cassava Mosaic Disease, Cassava Brown Streak Virus and Cassava Bacterial Blight based on the visual signs portrayed on the cassava leaves.<br/>

We also considered leaf segmentation using Enet to remove background noise.This gave us an option of training on both cropped and uncropped images to see how well the model learns for cropped images and uncropped images for the different diseases.We used the pre-trained VGG16 Convolutional Neural Network(This model is trained on a subset of the ImageNet database which is used in the ImageNet Large-Scale Visual Recognition Challenge (ILSVRC).<br/><br/> The reason as to why we used VGG16 include;<br/> 
1. It can be trained on a large dataset therefore makes the model learn more.<br/>
2. The model has learned rich feature representations for a wide range of images.<br/>
3. Accuracy.The VGG16 model has blocks with same filter size applied multiple times to extract more complex and representative features making it more accurate.<br/> 


