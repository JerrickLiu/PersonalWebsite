---
layout: project
title: CycleGAN and other computer vision stuff with aerial images. 
thumbnail-img: /assets/img/horse2zebra_1.png
order: 3
---

Throught the school year of my freshman year, I worked with a mentor of mine at the Air Force Research Laboratory conducting research in electro-optical ([EO](https://en.wikipedia.org/wiki/Electro-optical_sensor)) and synthetic-aperture radar ([SAR](https://en.wikipedia.org/wiki/Synthetic-aperture_radar)) images. Our goals were to perform image registration between these two domains of images. In short, we wanted to align these two different types of images in order to put them collectively into a nice dataset for future use through feature extraction and [homographies](https://en.wikipedia.org/wiki/Homography_(computer_vision))

If you haven't seen SAR images before, they are incredibly noisy at certain resolutions and it's awfully challenging to align images when you can't even tell what the image is of. 

Here are some examples of EO and SAR images. If you were worried about confidentiality, no worries! These images are [Distribution A](https://www.exportsolutionsinc.com/resources/blog/dod-distribution-statements/) and thus for public release.

![](/assets/img/EO.png)
![](/assets/img/SAR.png)

A proposed way of solving this problem is [CycleGAN](https://junyanz.github.io/CycleGAN/), which essentially allows us to convert images from one domain to another. In our caes, we want to convert SAR images to EO images, register the generated image, and then do the homography based on the feature points extracted on the generated image. It's really cool and we've made some progress! Down below are some results from SAR images to EO images after training CylceGAN on 15 epochs.

![](/assets/img/cg_result.png)

On top of that, I'm also in charge of a [classification competition](https://competitions.codalab.org/competitions/28123) based on our aligned EO and SAR data. We've gotten around 300 participants from all over the world including China, Switzerland, Romania, Japan, the United States, and more to submit models to classify EO and SAR chips of vehicles. It's been incredibly fascinating see all the various methods used to this classification, including [feature fusion](https://www.sciencedirect.com/science/article/pii/S003132030500083X), [knowledge distillation](https://arxiv.org/abs/1912.13179), and [semi-supervised learning methods like Noisy Student](https://arxiv.org/abs/1911.04252). I've been writing a paper detailing the results of the competitions as well as the intricate methods used by all of these teams. You can see the paper [here]({{site.url}}/files/publications/ntire.pdf)