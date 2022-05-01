# 3D Object Stylization and Placement Proposal

### Introduction

- Our project is to synthesize a hormonious stylized 3D scene from a stylized 3D scene and a new 3D object. The project consists of three parts: object stylization, object placement and harmony analysis.
- Team Members:
  - Chunru Lin
  - Cong Zhou
  - Haotian Zheng

### Problem Description

- Harmonious 3D scenes generation is challenging but of great importance for real-world scenes modeling, which is a major topic in computer graphics. It is also the fundation of 3D scene understanding and further human-machine interaction. In 2D vision, object placement and image harmonization gains lots of attention and attracts many reseachers with its novelty and challenges. However, it hasn't been highly noticed in computer graphics. In this project, we focus on the harmonization topic and try to provide a general method to synthesize harmonious stylized 3D scene with a stylized scene and a new object.

### Goals & Deliverables
- Our plan is to generate stylized and harmonic cartoon-like scenes with a given set of realistic models and get fun pictures of them.
    - **Model Stylization.** First, we will tranform a series of imported, realistic models (meshes) into a more cartoon-styled ones using techniques like cubic stylization.
    - **Harmony Evaluation.** Stylizing models are not enough to make a harmonic scene; with the help of clustering, we may evaluate whether the style of two models resembles each other and furthermore choose a portion of models to be included.
    - **Model Placement.** Fit our selected models into the scene and make pictures. A naive implementation is to put objects one by one wherever vacant, in other words, to avoid collision. More advanced placement can be inspired by 2D techniques in CV. 
    - Among the three goals mentioned above, **Stylization and harmony evaluation** are what we plan to deliver, and **advanced model placement** is what we hope to deliver.
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

