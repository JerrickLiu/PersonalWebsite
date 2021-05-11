---
layout: page
title: My work experience
subtitle: A glimpse into what I've worked on at my jobs
---

## What I'm working on right now

### Computer Vision 

Right now, I'm working with a mentor of mine at the Air Force Research Laboratory conducting research in electro-optical ([EO](https://en.wikipedia.org/wiki/Electro-optical_sensor)) and synthetic-aperture radar ([SAR](https://en.wikipedia.org/wiki/Synthetic-aperture_radar)) images. Our goals right now are to perform image registration between these two domains of images. In short, we want to align these two different types of images in order to put them collectively into a nice dataset for future use through feature extraction and [homographies](https://en.wikipedia.org/wiki/Homography_(computer_vision))

If you haven't seen SAR images before, they are incredibly noisy at certain resolutions and it's awfully challenging to align images when you can't even tell what the image is of. A proposed way of solving this problem is [CycleGAN](https://junyanz.github.io/CycleGAN/), which essentially allows us to convert images from one domain to another. In our caes, we want to convert SAR images to EO images, register the generated image, and then do the homography based on the feature points extracted on the generated image. It's really cool and we've made some progress!

On top of that, I'm also in charge of a classification competition based on our aligned EO and SAR data. We've gotten around 300 participants from all over the world including China, Switzerland, Romania, Japan, the United States, and more to submit models to classify EO and SAR chips of vehicles. It's been incredibly fascinating see all the various methods used to this classification, including [feature fusion](https://www.sciencedirect.com/science/article/pii/S003132030500083X), [knowledge distillation](https://arxiv.org/abs/1912.13179), and [semi-supervised learning methods like Noisy Student](https://arxiv.org/abs/1911.04252). I've been writing a paper detailing the results of the competitions as well as the intricate methods used by all of these teams. 


### Reinforcement Learning / Natural Language Processing

I'm also working on another research project centered around natural language processing and reinforcement learning. I'll be getting to work with transformers (specifically [Bidirectional Encoder Represenations (BERT)](http://jalammar.github.io/illustrated-bert/)) to hopefully train up a chatbot that can provide us a lot of important information depending on what we ask it. We're hopefully going to reinforce the learning of the chatbot as well using [Ray and RLlib](https://arxiv.org/abs/1911.04252) to provide more satsifactory answers.

### Code moderator for [Software Design Studio (CS 126)](https://courses.grainger.illinois.edu/CS126/sp2021/)

I'm also a code moderator for one of the classes here at UIUC called Software Design Studio where we try to emphasize good coding practices, smart design choices, and proper documentation for code. As a code moderator, I'm responsible for 5 talented and driven students where I view their code and offer constructive criticism to help them write better code. It's been a rewarding experience seeing the student's code quality improve so much over the semester. 

## Summer of 2020

See [this post where I talk about my RL minecraft project](_projects/MineRL.md)

## Summer of 2019

See [this post where I talk about my explainable A.I. project](_projects/GradCAM.md)


