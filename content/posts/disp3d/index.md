---
title: Learning Local Displacements for Point Cloud Completion
date: 2022-02-19T10:15:01+02:00
categories: [CVPR]
tags: [3D Completion, Semantic Completion, Point Cloud]
language: en
cover:
    image: "covers/disp3d.png"
    alt: 'disp3d'
    caption: "Learning Local Displacements for Point Cloud Completion"
slug: disp3d
---

> Re-direct to the full [**PAPER**](https://arxiv.org/pdf/2203.16600v1.pdf) and [**CODE**](https://github.com/wangyida/disp3d) 

{{< youtube -rSLpHYO78M >}}

# Abstract
<div style="display: flex; flex-wrap: wrap; gap: 20px; align-items: flex-start; margin-bottom: 30px;">
    <div style="flex: 1; width: 50%; min-width: 300px;">
        <img src="images/CVPR_teaser.png" style="width: 100%; height: auto; border-radius: 4px;">
    </div>
    <div style="flex: 1; width: 50%; min-width: 300px;">
        <h3 style="margin-top: 0;">Completing a car</h3>
        <p>From the input partial scan to our object completion, we visualize the amount of detail in our reconstruction.</p>
    </div>
</div>

We propose a novel approach aimed at object and semantic scene completion from a partial scan represented as a 3D point cloud.
Our architecture relies on three novel layers that are used successively within an encoder-decoder structure and specifically developed for the task at hand.
The first one carries out feature extraction by matching the point features to a set of pre-trained local descriptors.
Then, to avoid losing individual descriptors as part of standard operations such as max-pooling, we propose an alternative neighbor-pooling operation that relies on adopting the feature vectors with the highest activations. Finally, up-sampling in the decoder modifies our feature extraction in order to increase the output dimension.
While this model is already able to achieve competitive results with the state of the art, we further propose a way to increase the versatility of our approach to process point clouds. To this aim, we introduce a second model that assembles our layers within a transformer architecture.
We evaluate both architectures on object and indoor scene completion tasks, achieving state-of-the-art performance.

# Methodology
## Local displacement operator
<table style="width: 100%; border: none; border-collapse: collapse;">
  <tr style="border: none;">
    <td style="width: 50%; vertical-align: top; border: none; padding-right: 15px;">
      <img src="images/CVPR_graph_conv.png" style="width: 100%; height: auto;">
    </td>
    <td style="width: 50%; vertical-align: top; border: none; padding-left: 15px;">
      <strong>The operation</strong><br><br>
      (a) <em>k</em>-nearest neighbor in reference to an anchor <strong>f</strong>; (b) displacement vectors around the anchor <strong>f</strong> + δ<sub>i</sub> and the corresponding weight σ<sub>i</sub>; and, (c) closest features for all i.
    </td>
  </tr>
</table>

## Architectures
<table style="width: 100%; border: none; border-collapse: collapse;">
  <tr style="border: none;">
    <td style="width: 50%; text-align: center; vertical-align: top; border: none; padding: 5px;">
      <strong>The <em>direct</em> architecture</strong><br>
      <img src="images/CVPR_direct_architecture.png" style="width: 100%; height: auto;">
    </td>
    <td style="width: 50%; text-align: center; vertical-align: top; border: none; padding: 5px;">
      <strong>The <em>transformer</em> architecture</strong><br>
      <img src="images/CVPR_transformer_architecture.png" style="width: 100%; height: auto;">
    </td>
  </tr>
</table>

## Qualitatives
### Object completion
![objects](images/CVPR_shapenet.png#center)

### Semantic scene completion
![objects](images/CVPR_scannet.png#center)

# Cite

If you find this work useful in your research, please cite:

```bash
@inproceedings{wang2022displacement,
  title={Learning Local Displacements for Point Cloud Completion},
  author={Wang, Yida and Tan, David Joseph and Navab, Nassir and Tombari, Federico},
  booktitle={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
  year={2022}
}
```
