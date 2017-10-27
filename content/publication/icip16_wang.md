+++
abstract = "CNN has shown excellent performance on object recognition based on huge amount of real images. For training with synthetic data rendered from 3D models alone to reduce the workload of collecting real images, we propose a concatenated self-restraint learning structure lead by a triplet and softmax jointed loss function for object recognition. Locally connected auto encoder trained from rendered images with and without background used for object reconstruction against environment variables produces an additional channel automatically concatenated to RGB channels as input of classification network. This structure makes it possible training a softmax classifier directly from CNN based on synthetic data with our rendering strategy. Our structure halves the gap between training based on real photos and 3D model in both PASCAL and ImageNet database compared to GoogleNet."
abstract_short = "For training with synthetic data rendered from 3D models alone to reduce the workload of collecting real images, we propose a concatenated self-restraint learning structure lead by a triplet and softmax jointed loss function for object recognition. Locally connected auto encoder trained from rendered images with and without background used for object reconstruction against environment variables produces an additional channel automatically concatenated to RGB channels as input of classification network."
authors = ["Yida Wang, Weihong Deng"]
date = "2016-08-19"
image_preview = "objectrec.svg"
math = true
publication_types = ["1"]
publication = "In *Image Processing (ICIP)*, IEEE."
publication_short = "In *ICIP*"
selected = true
title = "Self-restraint object recognition by model based CNN learning"
tags = ["deep-learning", "computer-vision"]
url_code = ""
url_dataset = ""
url_pdf = "https://www.researchgate.net/publication/307515952_Self-restraint_object_recognition_by_model_based_CNN_learning"
url_project = "project/deep-learning/"
url_slides = ""
url_video = ""

+++

![objectrec](/img/objectrec.svg)
![reconstruction](/img/reconstruction.svg)

Synthetic | Real
:----:|:----:
![recon_model](/img/recon_model-eps-converted-to.svg) | ![recon_real](/img/recon_real-eps-converted-to.svg) 