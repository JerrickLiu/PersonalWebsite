---
layout: post
title: Military vehicle classification and GradCAM
subtitle: Explainable A.I.
gh-repo: JerrickLiu/PyTorch-GradCam
gh-badge: [star, fork, follow]
thumbnail-img: /assets/img/cam.jpg
---

Through using supervised learning, I was able to train CNNs to classify 18
different classes of military vehicles.
I also used GradCAM, an explainable AI
technique used to visualize where the
CNN is looking at in an image. Below, I ran the GradCAM code on an image
of myself! Pretty cool!

![GradCAM](/assets/img/cam.jpg){: .mx-auto.d-block :}

### A bit more about this project

In the summer of 2019, I undertook a supervised learning research project for the 
Air Force to improve image classification of military vehicles in drones using t
he machine learning library PyTorch. Some of the work is classified, 
including the dataset so the Github repo does not contain the full code 
base I worked with nor the datset. However, the code for GradCAM that 
I helped improve is all there. GradCAM is very useful explainable A.I. 
technique used to highlight the features of a iamge a neural network 
is looking at when performing image classification. I ran the code on a 
picture of myself to show a little demonstration (keep in mind there hasn't 
been any training done on classifying my face) and as you can it see it 
seems to be looking at the edges of my collar. 

I used this code to load in trained models to see where the neural networks 
were looking at and it proves to be very helpful when trying to improve image 
classification. The results I obtained from the summer, I presented 
to a group of senior Air Force staff and fellow researchers. 
I'm quite proud of the code and findings I produced and this project cemented my love for machine learning.