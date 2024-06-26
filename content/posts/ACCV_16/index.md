---
title: Zigzagnet- Efficient deep learning for real object recognition based on 3D models
date: 2016-09-01T10:15:01+02:00
categories: [conference]
tags: [deep learning, computer vision, quantization, ACCV]
language: en
slug: accv16
---

# Abstrarct

Effective utilization on texture-less 3D models for deep learning is significant to recognition on real photos. We eliminate the reliance on massive real training data by modifying convolutional neural network in 3 aspects: synthetic data rendering for training data generation in large quantities, multi-triplet cost function modification for multi-task learning and compact micro architecture design for producing tiny parametric model while overcoming over-fit problem in texture-less models. Network is initiated with multi-triplet cost function establishing sphere-like distribution of descriptors in each category which is helpful for recognition on regular photos according to pose, lighting condition, background and category information of rendered images. Fine-tuning with additional data further meets the aim of classification on special real photos based on initial model. We propose a 6.2 MB compact parametric model called ZigzagNet based on SqueezeNet to improve the performance for recognition by applying moving normalization inside micro architecture and adding channel wise convolutional bypass through macro architecture.  Moving batch normalization is used to get a good performance on both convergence speed and recognition accuracy. Accuracy of our compact parametric model in experiment on ImageNet and PASCAL samples provided by PASCAL3D+ based on simple Nearest Neighbor classifier is close to the result of 240 MB AlexNet trained with real images. Model trained on texture-less models which consumes less time for rendering and collecting outperforms the result of training with more textured models from ShapeNet.

# Cite

If you find this work useful in your research, please cite:

```bash
@inproceedings{wang2016zigzagnet,
  title={Zigzagnet: Efficient deep learning for real object recognition based on 3D models},
  author={Wang, Yida and Cui, Can and Zhou, Xiuzhuang and Deng, Weihong},
  booktitle={Asian Conference on Computer Vision},
  pages={456--471},
  year={2016},
  organization={Springer}
}	
```

