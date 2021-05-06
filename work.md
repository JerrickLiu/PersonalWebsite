---
layout: page
title: My work experience
subtitle: A glimpse into what I've worked on at my jobs
show-avatar: false
---

### What I'm working on right now

Right now, I'm working with a mentor of mine at the Air Force Research Laboratory conducting research in electro-optical ([EO](https://en.wikipedia.org/wiki/Electro-optical_sensor)) and synthetic-aperture radar ([SAR](https://en.wikipedia.org/wiki/Synthetic-aperture_radar)) images. Our goals right now are to perform image registration between these two domains of images. In short, we want to align these two different types of images in order to put them collectively into a nice dataset for future use through feature extraction and [homographies](https://en.wikipedia.org/wiki/Homography_(computer_vision))

If you haven't seen SAR images before, they are incredibly noisy at certain resolutions and it's awfully challenging to align images when you can't even tell what the image is of. A proposed way of solving this problem is CycleGAN, which essentially allows us to convert images from one domain to another. In our caes, we want to convert SAR images to EO images, register the generated image, and then do the homography based on the feature points extracted on the generated image. It's really cool and we've made some progress!

### Summer of 2020

In the summer of 2020, I explored hierarchical reinforcement learning where I was researching whether agents can make long term decisions in the world of Minecraft. Minecraft may not be a hard game to us humans but to machine learning models there is a lot of planning to be done. Our end goal was to obtain a diamond, something not as trivial as it seems. 

I originally just used PPO (proximal policy optimization), a state-of-the art RL algoithm, but found that the agent wasn’t learning much. The rewards were very sparse since you only got rewards from mining or crafting (which takes sequential hitting actions). What we found was that MineRL environment also contains 60 million frames of human gameplay. Screaming imitation learning.
Used simple behavior cloning to train our agent: your actions should follow what these humans are doing. Penalized for not taking the “expert” action. Supervised. Then continued training with PPO
Found that agents learned much quickly. Able to chop trees and obtain wood. 
Sadly we ran out of time in the internship because COVID cut the research to only 6 weeks. Couldn’t train more and do more rollouts. 
Interesting parallels: MineRL could maybe support multi agent environments and I connected it to your paper on multi-agent tasks. Although not necessarily each task needs the other agent, coordination could definitely help to “solve” the environment (obtaining a diamond). Agents using your TBONE network, your 

### Summer of 2019


