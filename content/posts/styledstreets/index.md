---
title: Multi-style Street Simulator with Spatial and Temporal Consistency (StyledStreets)
date: 2025-06-01T10:15:01+02:00
categories: [conference]
tags: [Deep Learning, Computer Vision, Gaussian Splatting, Diffusion]
language: en
cover:
    image: "covers/styledstreets.png"
    alt: 'styledstreets'
    caption: "*StyledStreets* migrates a pre-trained Gaussian Splatting model (a) into other styles (b-h), while the geometries and dynamics are kept consistent as the original scene, preserving the 3D simulation capability (h-i)."
slug: styledstreets
---
> Re-direct to the full [**PAPER**](https://arxiv.org/abs/2503.21104)

Urban scene reconstruction demands modeling static infrastructure and dynamic elements while maintaining consistency across diverse environmental conditions. We present StyledStreets, a multi-style street synthesis framework that achieves instruction-driven scene editing with ensured spatial-temporal coherence. Building on 3D Gaussian Splatting, we enhance street scene modeling through novel pose-aware optimization and multi-view training, enabling photorealistic environmental style transfer across seasonal variations, weather conditions, and multi-camera configurations. Our approach introduces three key innovations: (1) a hybrid geometry-appearance embedding architecture that disentangles persistent scene structure from transient stylistic attributes; (2) an uncertainty-aware rendering pipeline mitigating supervision noise from diffusion-based priors; and (3) a unified parametric model enforcing geometric consistency through regularized gradient updates.

# Methodology
## Mitigating Diffusion Ambiguity
![dino](images/dino_optimized.png)


# Qualitatives
## Depth
![depth](images/styled-gs-depth.gif)

## Novel Trajectories
![nvs](images/styled-gs-novelview.gif)

## Multi-cameras
![cameras](images/styledSG-3views.gif)

# Cite 

If you find this work useful in your research, please cite:

```bash
@misc{chen2025styledstreetsmultistylestreetsimulator,
      title={StyledStreets: Multi-style Street Simulator with Spatial and Temporal Consistency},
      author={Yuyin Chen and Yida Wang and Xueyang Zhang and Kun Zhan and Peng Jia and Yifei Zhan and Xianpeng Lang},
      year={2025},
      eprint={2503.21104},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2503.21104},
}
```

