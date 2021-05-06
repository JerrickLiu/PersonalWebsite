---
layout: page
title: My work experience
subtitle: A glimpse into what I've worked on at my jobs
---

## What I'm working on right now

### Computer Vision 

Right now, I'm working with a mentor of mine at the Air Force Research Laboratory conducting research in electro-optical ([EO](https://en.wikipedia.org/wiki/Electro-optical_sensor)) and synthetic-aperture radar ([SAR](https://en.wikipedia.org/wiki/Synthetic-aperture_radar)) images. Our goals right now are to perform image registration between these two domains of images. In short, we want to align these two different types of images in order to put them collectively into a nice dataset for future use through feature extraction and [homographies](https://en.wikipedia.org/wiki/Homography_(computer_vision))

If you haven't seen SAR images before, they are incredibly noisy at certain resolutions and it's awfully challenging to align images when you can't even tell what the image is of. A proposed way of solving this problem is CycleGAN, which essentially allows us to convert images from one domain to another. In our caes, we want to convert SAR images to EO images, register the generated image, and then do the homography based on the feature points extracted on the generated image. It's really cool and we've made some progress!


### RL / NLP

I'm also working on another research project centered around natural language processing and reinforcement learning. I'll be getting to work with transformers (specifically Bidirectional Encoder Represenations BERT) to hopefully train up a chatbot that can provide us a lot of important information depending on what we ask it. We're hopefully going to reinforce the learning of the chatbot as well to provide more satsifactory answers. 

## Summer of 2020

See [this post where I talk about my RL minecraft project](_projects/MineRL.md)

## Summer of 2019

See [this post where I talk about my explainable A.I. project](_projects/GradCAM.md)


