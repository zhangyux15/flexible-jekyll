---
layout: post
title: 4D Association Graph for Realtime Multi-person Motion Capture UsingMultiple Video Cameras
date: 2020-02-26 20:03:20 +0800
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: 4dassoc_teaser.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: []
---

## Abstract
This paper contributes a novel realtime multi-person motion capture algorithm using multiview video inputs. Due to the heavy occlusions in each view, joint optimization on the multiview images and multiple temporal frames is indispensable, which brings up the essential challenge of realtime efficiency. To this end, for the first time, we unify per-view parsing, cross-view matching, and temporal tracking into a single optimization framework, i.e., a 4D association graph that each dimension (image space, viewpoint and time) can be treated equally and simultaneously. To solve the 4D association graph efficiently, we further contribute the idea of 4D limb bundle parsing based on heuristic searching, followed with limb bundle assembling by proposing a bundle Kruskal's algorithm. Our method enables a real-time online motion capture system running at 30fps using 5 cameras on a 5-person scene. Benefiting from the unified parsing, matching and tracking constraints, our method is robust to noisy detection, and achieves high-quality online pose reconstruction quality. The proposed method outperforms the state-of-the-art method quantitatively without using high-level appearance information. We also contribute a multiview video dataset synchronized with a marker-based motion capture system for scientific evaluation.

## Method Overview
(a) We input body part positions and connection confidence of different views at time $t$, together with 3D person of last time. We use 3 views for example. (b) The 4D association graph. For clarity, we only highlight the association of the torso limb with three types of edges (**parsing** edges, **matching** edges and **tracking** edges) with different colors. (c) From the initial graph (b), our association method outputs the assembling results. (d) We optimize the assembled multiview 2D skeletons (c) to form 3D skeletons of current frame $t$.
![overview]({{site.baseurl}}/assets/img/4dassoc_overview.jpg)

## Results
![teaser]({{site.baseurl}}/assets/img/4dassoc_teaser.jpg)
Our method enables multi-person motion capture system working at 30fps for 5 persons using 5 RGB cameras, while achieving high quality skeleton reconstruction results.

![result]({{site.baseurl}}/assets/img/4dassoc_result.jpg)
Results of our system. From top to bottom: input images, reprojection of 3D human, and 3D visualization respectively. (a) Our live captured data with fast motion (left), severe occlusion (middle) and crowded scene (right). 5 views used. (b) Our dataset with textureless clothing and rich motion. 6 views used. (c) Panoptic studio dataset with natural social interaction. 7 views used.
