---
title: Hierarchy Unified Gaussian Primitive for Large-Scale Dynamic Scene Reconstruction (Hierarchy UGP)
date: 2025-06-27T10:15:01+02:00
categories: [conference]
tags: [Deep Learning, Computer Vision, ICCV, Gaussian Splatting]
language: en
cover:
    image: "covers/ugp.png"
    alt: 'ugp'
    caption: "Hierarchy UGP: Hierarchy Unified Gaussian Primitive for Large-Scale Dynamic Scene Reconstruction. Approaching the road goalpoint **g** from an airial starting point **s** above the district."
slug: ugp
---
> Re-direct to the full [**PAPER**](https://openaccess.thecvf.com/content/ICCV2025/papers/Sun_Hierarchy_UGP_Hierarchy_Unified_Gaussian_Primitive_for_Large-Scale_Dynamic_Scene_ICCV_2025_paper.pdf), [PROJECT PAGE](https://sunhongyang10.github.io/Project_Page_HierarchyUGP/) and [**CODE**](https://github.com/LiAutoAD/HierarchyUGP)

Recent advances in differentiable rendering have significantly improved dynamic street scene reconstruction. However, the complexity of large-scale scenarios and dynamic elements, such as vehicles and pedestrians, remains a substantial challenge. Existing methods often struggle to scale to large scenes or accurately model arbitrary dynamics. To address these limitations, we propose Hierarchy UGP, which constructs a hierarchical structure consisting of a root level, sub-scenes level, and primitive level, using Unified Gaussian Primitive (UGP) defined in 4D space as the representation. The root level serves as the entry point to the hierarchy. At the sub-scenes level, the scene is spatially divided into multiple sub-scenes, with various elements extracted. At the primitive level, each element is modeled with UGPs, and its global pose is controlled by a motion prior related to time. This hierarchical design greatly enhances the model's capacity, enabling it to model large-scale scenes. Additionally, our UGP allows for the reconstruction of both rigid and non-rigid dynamics. We conducted experiments on Dynamic City, our proprietary large-scale dynamic street scene dataset, as well as the public Waymo dataset. Experimental results demonstrate that our method achieves state-of-the-art performance. We plan to release the accompanying code and the Dynamic City dataset as open resources to further research within the community.


# Cite 

If you find this work useful in your research, please cite:

```bash
@InProceedings{Sun_2025_ICCV,
    author    = {Sun, Hongyang and Yang, Qinglin and Wang, Jiawei and Xu, Zhen and Liu, Chen and Wang, Yida and Zhan, Kun and Bao, Hujun and Zhou, Xiaowei and Peng, Sida},
    title     = {Hierarchy UGP: Hierarchy Unified Gaussian Primitive for Large-Scale Dynamic Scene Reconstruction},
    booktitle = {Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
    month     = {October},
    year      = {2025},
    pages     = {26252-26262}
}
```

