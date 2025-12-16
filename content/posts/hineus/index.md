---
title: High-fidelity Neural Surface Mitigating Low-texture and Reflective Ambiguity (HiNeuS)
date: 2025-06-27T10:15:01+02:00
categories: [conference]
tags: [Deep Learning, Computer Vision, ICCV, NeuS, Volume Rendering]
language: en
cover:
    image: "covers/hineus.png"
    alt: 'caption for image'
    caption: "HiNeuS: High-fidelity Neural Surface Mitigating Low-texture and Reflective Ambiguity"
slug: hineus
---
> Re-direct to the full [**PAPER**](https://arxiv.org/pdf/2506.23854) and [**CODE**](https://github.com/LiAutoAD)

Neural surface reconstruction faces persistent challenges in reconciling geometric fidelity with photometric consistency under complex scene conditions. We present HiNeuS, a unified framework that holistically addresses three core limitations in existing approaches: multi-view radiance inconsistency, missing keypoints in textureless regions, and structural degradation from over-enforced Eikonal constraints during joint optimization. To resolve these issues through a unified pipeline, we introduce: 1) Differential visibility verification through SDF-guided ray tracing, resolving reflection ambiguities via continuous occlusion modeling; 2) Planar-conformal regularization via ray-aligned geometry patches that enforce local surface coherence while preserving sharp edges through adaptive appearance weighting; and 3) Physically-grounded Eikonal relaxation that dynamically modulates geometric constraints based on local radiance gradients, enabling detail preservation without sacrificing global regularity. Unlike prior methods that handle these aspects through sequential optimizations or isolated modules, our approach achieves cohesive integration where appearance-geometry constraints evolve synergistically throughout training. Comprehensive evaluations across synthetic and real-world datasets demonstrate state-of-the-art performance, including a 21.4% reduction in Chamfer distance over reflection-aware baselines and 2.32 dB PSNR improvement against neural rendering counterparts. Qualitative analyses reveal superior capability in recovering specular instruments, urban layouts with centimeter-scale infrastructure, and low-textured surfaces without local patch collapse. The method’s generalizability is further validated through successful application to inverse rendering tasks, including material decomposition and view-consistent relighting.

# Methodology
We manage to handle occlusion-aware reflection. The SDF-based visibility verification avoids artifacts in neural and mesh-based approaches through continuous surface evaluation. Surface collapse is avoided even with cross-view reflection ambiguity.

Meshing the toaster with multi-view stereo reconstruction.
![toaster](images/toaster.gif)

## Self-Reflection Compensation 
Self-reflection handling comparison with RefNeuS.
![indirect_reflection](images/indirect_reflection.gif)

## Local Geometry-Constrained Regularization
Local geometry constraints enforce planarity through ray-aligned neighborhood sampling in textureless regions.

Investigating the planarity on top of a toy example on drum.
![toyexample](images/smooth_toyexample.png)

## Adaptive Eikonal
Purple/green regions indicate strong/weak regularization respectively.
![eikonal_relaxation](images/eikonal_relaxation.png)
High-fidelity details of the ship sculpture are revealed
![ship](images/ship.gif)

# Qualitatives
## UrbanScene3D
Our trained model renders the static layout in (b), disregarding the specular and dynamic visual cues such as moving vehicles in (a), so that our learned neural surfaces in (e) reveal more consistent roads without collapsing compared to Neuralangelo
![urban3d](images/static_rendering.png)

## Glossy Objects
Our method’s reflection-aware formulation demonstrates significant advantages on the GlossySynthetic benchmark.
![glossysynthetic](images/glossysynthetic.gif)

## 3DRealCar
Supplementing geometric layout for in-the-wild vehicle assets
![3drealcar](images/autoset.gif)

# Cite 

If you find this work useful in your research, please cite:

```bash
@inproceedings{wang2025hineus,
  title={HiNeuS: High-fidelity Neural Surface Mitigating Low-texture and Reflective Ambiguity},
  author={Wang, Yida and Zhang, Xueyang and Zhan, Kun and Jia, Peng and Lang, Xianpeng},
  booktitle={Proceedings of the IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2025},
}
```

