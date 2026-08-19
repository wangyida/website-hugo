---
title: Arbitrary-Resolution and Fine-Grained Depth Estimation with Neural Implicit Fields (InfiniDepth)
date: 2026-04-09T10:15:01+02:00
categories: [CVPR]
tags: [Depth Estimation, Neural Rendering]
language: en
cover:
    image: "covers/infinidepth.png"
    alt: 'infinidepth'
    caption: "InfiniDepth: Arbitrary-Resolution and Fine-Grained Depth Estimation with Neural Implicit Fields"
slug: infinidepth
---
> Re-direct to the full [**PAPER**](https://zju3dv.github.io/InfiniDepth/) and [**CODE**](https://github.com/RitianYu/InfiniDepth)

<video controls loop muted playsinline style="width: 100%; height: auto; border-radius: 4px;">
    <source src="images/demo.mov" type="video/mp4">
</video>

# Abstract

Existing depth estimation methods are fundamentally limited to predicting depth on discrete image grids. Such representations restrict their scalability to arbitrary output resolutions and hinder the geometric detail recovery. This paper introduces **InfiniDepth**, which represents depth as neural implicit fields. Through a simple yet effective local implicit decoder, we can query depth at continuous 2D coordinates, enabling arbitrary-resolution and fine-grained depth estimation. To better assess our method's capabilities, we curate a high-quality 4K synthetic benchmark from five different games, spanning diverse scenes with rich geometric and appearance details. Experiments demonstrate that InfiniDepth achieves SOTA performance on both synthetic and real-world benchmarks across relative and metric depth estimation tasks, particularly excelling in fine-detail regions. It also benefits the task of novel view synthesis under large viewpoint shifts, producing high-quality results with fewer holes and artifacts.

# Methodology
## Pipeline
![pipeline](images/pipeline.jpg)

**Pipeline of InfiniDepth:**
- **Feature Query:** given an input image and a continuous query 2D coordinate, we extract feature tokens from multiple layers of the ViT encoder, and query local features for the coordinate at each scale through bilinear interpolation.
- **Depth Decoding:** given the multi-scale local features queried at the continuous coordinate, we hierarchically fuse features from high spatial resolution to low spatial resolution, and decode the fused feature to the depth value through a MLP head.

# Qualitative Visualization
The following are sample scene examples from InfiniDepth. The [**project page**](https://zju3dv.github.io/InfiniDepth/) provides fully interactive versions where you can zoom into 8K depth maps, rotate 3D point clouds, and explore Gaussian Splatting scenes in real time.

## Depth Map
Fine-grained depth maps predicted by InfiniDepth at high resolution. Each pair shows the RGB input (left) and the predicted depth map (right).
<table style="width: 100%; border: none; border-collapse: collapse;">
  <tr style="border: none;">
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/interactive_depth_rgb1.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/depth_result1.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
  </tr>
  <tr style="border: none;">
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/interactive_depth_diode.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/depth_result_diode.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
  </tr>
  <tr style="border: none;">
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/interactive_depth_rgb3.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/depth_result3.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
  </tr>
  <tr style="border: none;">
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/interactive_depth_rgb4.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 50%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/depth_result4.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
  </tr>
</table>

> For an interactive depth map viewer with zoom and pan, visit the [**InfiniDepth project page**](https://zju3dv.github.io/InfiniDepth/).

## Point Cloud
Point clouds reconstructed from predicted depth maps on diverse scenes. Below are sample scene examples and the rendered point cloud visualizations.
<table style="width: 100%; border: none; border-collapse: collapse;">
  <tr style="border: none;">
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/pointcloud_diode.png" style="width: 100%; height: auto; border-radius: 4px;">
      <p style="text-align: center; font-size: 0.9em;">DIODE</p>
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/pointcloud_eth1.png" style="width: 100%; height: auto; border-radius: 4px;">
      <p style="text-align: center; font-size: 0.9em;">ETH3D</p>
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/pointcloud_eth2.png" style="width: 100%; height: auto; border-radius: 4px;">
      <p style="text-align: center; font-size: 0.9em;">ETH3D</p>
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/pointcloud_nyu.png" style="width: 100%; height: auto; border-radius: 4px;">
      <p style="text-align: center; font-size: 0.9em;">NYU</p>
    </td>
  </tr>
</table>

![vis_pcd1](images/vis_pcd1.jpg)
![vis_pcd3](images/vis_pcd3.jpg)
![vis_pcd4](images/vis_pcd4.jpg)

> For an interactive 3D point cloud viewer with rotation, zoom, and pan, visit the [**InfiniDepth project page**](https://zju3dv.github.io/InfiniDepth/).

## Interactive Gaussian Splatting
3D Gaussian Splatting results from single-view depth prediction by InfiniDepth. Below are sample scene examples (input views).
<table style="width: 100%; border: none; border-collapse: collapse;">
  <tr style="border: none;">
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/gs_scene1.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/gs_scene2.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/gs_scene3.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
    <td style="width: 25%; vertical-align: top; border: none; padding: 5px;">
      <img src="images/gs_scene4.png" style="width: 100%; height: auto; border-radius: 4px;">
    </td>
  </tr>
</table>

> For an interactive Gaussian Splatting viewer where you can freely navigate the 3D scenes, visit the [**InfiniDepth project page**](https://zju3dv.github.io/InfiniDepth/).

# Qualitative Comparison
## Depth Map Comparison
Predicted depth maps from different methods on the same input. Blue and pink boxes highlight regions with fine-grained geometric details.
![depth_comparison](images/depth_comparison.jpg)

## Point Cloud Comparison
Predicted point clouds from different methods on the same input. Orange boxes highlight regions with fine-grained geometric details.
![pcd_comparison](images/pcd_comparison.jpg)

## Novel View Synthesis
Single-View NVS results under large viewpoint changes, e.g. Bird's-eye (BEV) views.
![nvs_comparison](images/nvs_comparison.jpg)

<video controls loop muted playsinline style="width: 100%; height: auto; border-radius: 4px;">
    <source src="images/nvs_scene1.mp4" type="video/mp4">
</video>

# Cite

If you find this work useful in your research, please cite:

```bash
@article{yu2026infinidepth,
    title={InfiniDepth: Arbitrary-Resolution and Fine-Grained Depth Estimation with Neural Implicit Fields},
    author={Hao Yu, Haotong Lin, Jiawei Wang, Jiaxin Li, Yida Wang, Xueyang Zhang, Yue Wang, Xiaowei Zhou, Ruizhen Hu and Sida Peng},
    booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
    year={2026}
}
```
