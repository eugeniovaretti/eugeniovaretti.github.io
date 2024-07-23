---
title:  "Managing atrial fibrillation taking advantage of pseudo-electrogram measurements"
search: false
categories:
  - Python
  - Scientific Computing
---
## Introduction
Atrial fibrillation (AF) is a high-incidence cardiac arrhythmia characterized by episodes of atria's irregular electrical activity that may compromise atrial contraction. Despite clinical and academic research efforts, the mechanism behind atrial fibrillation is still subject to debate. Many theories have been proposed to explain AF mechanisms, such as the wave theory (Moe, 1962), focal activity (Jaïs et al., 1997), and driver domains (Haissaguerre et al., 2014).

In recent years, technological development has led to new clinical tools that open new frontiers in the study of AF. Specifically, the latest generation of mapping catheters allows, thanks to their multiple splines, to acquire a set of high-definition endocavitary signals that measure the local activity of the atrial tissue.

This project aims at developing innovative scientific computing tools to infer the mechanism of atrial fibrillation from pseudo-electrogram measurements. The research unfolds in three significant checkpoints, each addressing distinct aspects of this complex phenomenon.

### Checkpoint 1: Classification of Atrial Fibrillation Mechanism

The first checkpoint focuses on the development of an algorithm to discern and categorize atrial fibrillation mechanisms based on 20 endocavitary signals describing localized cardiac tissue activity. Two primary mechanisms are under scrutiny: focal activity and reentrant activity. Focal activity is typified by signal propagation radiating from a central point, while reentrant activity involves the continuous circulation of electrical impulses within a closed loop. Identification of the activation points through ECG signal morphology is pivotal to understanding the nature of these irregular heartbeats.
  
![identification]({{ site.url }}{{ site.baseurl }}/files/posts_img/hearth_img1.png){: .align-center}  

This checkpoint is further dissected into subproblems, encompassing signal annotation, the classification of annotated beats into the QS/RS groups, and the overarching classification of activities as focal, reentry, or a combination of both.

### Checkpoint 2: Estimation of Unknown Parameters

![inverse estimation]({{ site.url }}{{ site.baseurl }}/files/posts_img/hearth_img2_bis.png){: .align-right width="300" heigth="375"}
The second checkpoint is dedicated to inferring the unknown parameters characterizing the applied current within the monodomain model. Depending on the specific mechanism (focal or reentrant), these parameters may include the position of the focal activity center or the timing and length of the impulse generating reentrant activity.  
![inverse estimation]({{ site.url }}{{ site.baseurl }}/files/posts_img/hearth_img2.png){: .align-left width="300" heigth="350"}
Novel signals are generated from the 20 sensors by utilizing a numerical approximation based on the monodomain model coupled with the Mitchell-Schaeffer model. The optimization objective combines L2 norm relative error and a customized norm addressing activation timing errors to yield these critical parameters.

### Checkpoint 3: Reconstruction of Transmembrane Potential

The final segment of the project centers on the spatial reconstruction of the transmembrane potential on an 11x11 grid. The action potential, characterized by five distinct phases, governs cardiac cell function. This reconstruction is achieved through the application of the monodomain model coupled with the Mitchell-Schaeffer model. These models enable the simulation of electrical impulse propagation within cardiac tissue. The mathematical formulation encompasses partial differential equations and ionic models, which collectively facilitate a comprehensive understanding of action potential dynamics.  
  
![potential reconstruction](/files/posts_img/hearth_img3.png){: .align-center}  

The project incorporates techniques such as Principal Component Analysis (PCA) of multivariate data, Classification on PCA scores through Support Vector Machine (SVM), Regression through Generalized Linear Mixed models, Compressed sensing.  Further information on the project's aims and methodology can be found in the [dedicated report](/files/posts_pdf/hearth_pdf.pdf).





