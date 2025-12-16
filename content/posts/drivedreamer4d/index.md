---
title: World Models Are Effective Data Machines for 4D Driving Scene Representation (DriveDreamer4D)
date: 2025-05-11T10:15:01+02:00
categories: [conference]
tags: [Deep Learning, Computer Vision, CVPR, Gaussian Splatting, Diffusion]
language: en
cover:
    image: "covers/drivedreamer4d.png"
    alt: 'World Models Are Effective Data Machines for 4D Driving Scene Representation'
    caption: "drivedreamer4d"
slug: drivedreamer4d
---
> Re-direct to the full [**PAPER**](https://arxiv.org/abs/2410.13571), [PROJECT PAGE](https://drivedreamer4d.github.io/) and [**CODE**](https://github.com/GigaAI-research/DriveDreamer4D)

Closed-loop simulation is essential for advancing end-to-end autonomous driving systems. Contemporary sensor simulation methods, such as NeRF and 3DGS, rely predominantly on conditions closely aligned with training data distributions, which are largely confined to forward-driving scenarios. Consequently, these methods face limitations when rendering complex maneuvers (e.g., lane change, acceleration, deceleration). Recent advancements in autonomous-driving world models have demonstrated the potential to generate diverse driving videos. However, these approaches remain constrained to 2D video generation, inherently lacking the spatiotemporal coherence required to capture intricacies of dynamic driving environments. In this paper, we introduce DriveDreamer4D, which enhances 4D driving scene representation leveraging world model priors. Specifically, we utilize the world model as a data machine to synthesize novel trajectory videos, where structured conditions are explicitly leveraged to control the spatial-temporal consistency of traffic elements. Besides, the cousin data training strategy is proposed to facilitate merging real and synthetic data for optimizing 4DGS. To our knowledge, DriveDreamer4D is the first to utilize video generation models for improving 4D reconstruction in driving scenarios. Experimental results reveal that DriveDreamer4D significantly enhances generation quality under novel trajectory views, achieving a relative improvement in FID by 32.1%, 46.4%, and 16.3% compared to PVG, S3Gaussian, and Deformable-GS. Moreover, DriveDreamer4D markedly enhances the spatiotemporal coherence of driving agents, which is verified by a comprehensive user study and the relative increases of 22.6%, 43.5%, and 15.6% in the NTA-IoU metric.

# Methodology
## Architectures
![pipeline](images/pipeline_drivedreamer4d.png)

# Cite 

If you find this work useful in your research, please cite:

```bash
@inproceedings{zhao2025drivedreamer4d,
  title={Drivedreamer4d: World models are effective data machines for 4d driving scene representation},
  author={Zhao, Guosheng and Ni, Chaojun and Wang, Xiaofeng and Zhu, Zheng and Zhang, Xueyang and Wang, Yida and Huang, Guan and Chen, Xinze and Wang, Boyuan and Zhang, Youyi and others},
  booktitle={Proceedings of the Computer Vision and Pattern Recognition Conference},
  pages={12015--12026},
  year={2025}
}
```

