---
title: Crafting World Models for Driving Scene Reconstruction via Online Restoration (ReconDreamer)
date: 2025-05-11T10:15:01+02:00
categories: [conference]
tags: [Deep Learning, Computer Vision, CVPR, Gaussian Splatting, Diffusion]
language: en
cover:
    image: "covers/recondreamer.png"
    alt: 'Crafting World Models for Driving Scene Reconstruction via Online Restoration'
    caption: "recondreamer"
slug: recondreamer
---
> Re-direct to the full [**PAPER**](https://arxiv.org/abs/2411.19548), [**PROJECT PAGE**](https://recondreamer.github.io/) and [**CODE**](https://github.com/GigaAI-research/ReconDreamer)

Closed-loop simulation is crucial for end-to-end autonomous driving. Existing sensor simulation methods (e.g., NeRF and 3DGS) reconstruct driving scenes based on conditions that closely mirror training data distributions. However, these methods struggle with rendering novel trajectories, such as lane changes. Recent works have demonstrated that integrating world model knowledge alleviates these issues. Despite their efficiency, these approaches still encounter difficulties in the accurate representation of more complex maneuvers, with multi-lane shifts being a notable example. Therefore, we introduce ReconDreamer, which enhances driving scene reconstruction through incremental integration of world model knowledge. Specifically, DriveRestorer is proposed to mitigate artifacts via online restoration. This is complemented by a progressive data update strategy designed to ensure high-quality rendering for more complex maneuvers. To the best of our knowledge, ReconDreamer is the first method to effectively render in large maneuvers. Experimental results demonstrate that ReconDreamer outperforms Street Gaussians in the NTA-IoU, NTL-IoU, and FID, with relative improvements by 24.87%, 6.72%, and 29.97%. Furthermore,ReconDreamer surpasses DriveDreamer4D with PVG during large maneuver rendering, as verified by a relative improvement of 195.87% in the NTA-IoU metric and a comprehensive user study.

# Methodology

## Architectures 
![pipeline](images/pipeline_recondreamer.png)


# Cite 

If you find this work useful in your research, please cite:

```bash
@InProceedings{Ni_2025_CVPR,
    author    = {Ni, Chaojun and Zhao, Guosheng and Wang, Xiaofeng and Zhu, Zheng and Qin, Wenkang and Huang, Guan and Liu, Chen and Chen, Yuyin and Wang, Yida and Zhang, Xueyang and Zhan, Yifei and Zhan, Kun and Jia, Peng and Lang, Xianpeng and Wang, Xingang and Mei, Wenjun},
    title     = {ReconDreamer: Crafting World Models for Driving Scene Reconstruction via Online Restoration},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2025},
    pages     = {1559-1569}
}
```

