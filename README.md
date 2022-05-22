# 3D Object Stylization and Placement

### Introduction

- Our project is to synthesize a harmonious stylized 3D scene from a stylized 3D scene and a new 3D object. The project consists of three parts: object stylization, object placement and harmony analysis.
- Team Members:
  - Chunru Lin
  - Cong Zhou
  - Haotian Zheng

### Problem Description

- Harmonious 3D scenes generation is challenging but of great importance for real-world scenes modeling, which is a major topic in computer graphics. It is also the fundation of 3D scene understanding and further human-machine interaction. In 2D vision, object placement and image harmonization gains lots of attention and attracts many reseachers with its novelty and challenges. However, it hasn't been highly noticed in computer graphics. In this project, we focus on the harmonization topic and try to provide a general method to synthesize harmonious stylized 3D scene with a stylized scene and a new object.

### Goals & Deliverables
- Our plan is to generate stylized and harmonic scenes with a given set of realistic models and get fun pictures of them.
    - **Model Stylization.** First, we will tranform a series of imported, realistic models (meshes) into a more non-realistic ones using techniques like cubic stylization, which turns an object into a cute, cartoon-style one.
    - **Harmony Analysis.** Stylizing models are not enough to make a harmonic scene; with the help of clustering, we may evaluate whether the style of two models resembles each other and furthermore choose a portion of models to be included.
    - **Model Placement.** Fit our selected models into the scene and make pictures. A naive implementation is to put objects one by one wherever vacant, in other words, to avoid collision. More advanced placement can be inspired by 2D techniques in CV. 
    - Among the three goals mentioned above, **Stylization and harmony Analysis** are what we plan to deliver, and **advanced model placement** is what we hope to deliver.
- We will base our project on OpenGL or WebGL (easy to shift from on another anyway).
- Since our result is a cartoon image, the performance of our project is determined by the sense of beauty. 

### Schedule

- Week 1: read relevant papers
- Week 2~3: stylization (cubic as a starting example)
- Week 4~5: harmony evaluation and naive placement
- Week 6: render images, (if hev extra time) advanced object placement research, write paper, present videos, prepare presentation

### Resources

- Liu H T D, Jacobson A. Cubic stylization[J]. arXiv preprint arXiv:1910.02926, 2019.
- Liu T, Hertzmann A, Li W, et al. Style compatibility for 3D furniture models[J]. ACM Transactions on Graphics (TOG), 2015, 34(4): 1-9.
- Fisher M, Ritchie D, Savva M, et al. Example-based synthesis of 3D object arrangements[J]. ACM Transactions on Graphics (TOG), 2012, 31(6): 1-11.
- Ohlei A, Bundt L, Bouck-Standen D, et al. Optimization of 3D object placement in augmented reality settings in museum contexts[C]//International Conference on Augmented Reality, Virtual Reality and Computer Graphics. Springer, Cham, 2019: 208-220.
- Krichenbauer M, Yamamoto G, Taketom T, et al. Augmented reality versus virtual reality for 3d object manipulation[J]. IEEE transactions on visualization and computer graphics, 2017, 24(2): 1038-1048.
- https://www.youtube.com/watch?v=oBKrdRI_NGI
- To be added more...


# Milestone
## Model Stylization
First, we will tranform a series of imported, realistic models (meshes) into a more non-realistic ones using techniques like cubic stylization, which turns an object into a cute, cartoon-style one.
<img src="https://github.com/XHRlyb/CG-Project/blob/main/test.png?raw=true" style="width:50%">
<img src="https://github.com/XHRlyb/CG-Project/blob/main/test_before.png?raw=true" style="width:40%">
<img src="https://github.com/XHRlyb/CG-Project/blob/main/test_after.png?raw=true" style="width:40%">

## Harmony Analysis.
Our work in this stage mainly focuses on how two models resemble each other. In 2D, curvature features may be taken into consideration when synthesizing 2D shapes styles(Li et al.). For 3D, there exist algorithms traversing around a mesh gaining features and even a 3D model search engine is developed on it (Funkhouser et al.). However, what is spoiling is that these algorithms mainly focus on mapping, not making partitions.
Liu et al. introduced "part-aware geometric feature vectors" in Style Compatibility for 3D Furniture Models, characterizing the shapes of different parts of an object, and mapping different objects' geometric features to a shared feature space may shed some light. But whether feature vectors can be compared between completely irrelevant objects is still under investigation.

## Model Placement.
Fit our selected models into the scene and make pictures. A naive implementation is to put objects one by one wherever vacant, in other words, to avoid collision. More advanced placement can be inspired by 2D techniques in CV. 

For the 2D object placement task,  "InstaBoost: Boosting instance segmentation via probability map guided copy-pasting" applies appearance consistency heatmap to guide the placement with surrounding visual context; "Synthesizing training data for object detection in indoor scenes" combines supporting surface detection and semantic segmentation with pretrained deep learning model; other supervised methods predict bboxs first leveraging background and foreground features.


It is worth mentioning that some extra work and research is done towards mixing virtual scene and the real environment, putting virtual stylized models into reality with AR technology.Our first target is to learn how to recognize a scene in reality, like detecting a plane, and putting something on it. To do this, we try to make use of Google ARCore (https://developers.google.cn/ar/develop) running on most Android devices and Harmony OS ARCore (https://gitee.com/hms-core/hms-AREngine-demo) running on Harmony OS devices. Both framework supports AR model placement. Since stylization rely on compute resources, the light-weight mobile app as client is favourable to demonstrate placement results.
<img src="https://github.com/XHRlyb/CG-Project/blob/main/com.google.ar.png?raw=true" style="width:20%">

However, the second target, matching the stylized mesh with the environment is extremely troublesome. Categorizing the scene from a certain picture captured by the AR app is difficult in CV and needs compute resources support. What's more, even if we can tell the category of environment style, it differs form our idea of **Harmony Analysis**, where we mainly tell how two 3D objects **resemble** each other and divide them into clusters. 
Therefore, the environment is likely not to be considered during placement, and we are still struggling to put meshes dynamicly in the AR app.
