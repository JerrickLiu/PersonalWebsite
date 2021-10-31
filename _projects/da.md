---
layout: project
title: Unsupervised domain adaptation on EO and SAR images
thumbnail-img: /assets/img/da.png
order: 1
---

During the summer of 2021, I worked on a project centerd around unsupervised domain adaptation (UDA). Illustrated below, domain adaptation is the simple idea of training a classifier on one domain, called the source domain, and adapting that classifier to classify the same classes in another domain, called the target domain.

![ex]((/assets/img/da_ex.png)

In the unsupervised area, the other domain you are trying to classify images on do not have labels. Thus, it's crucial that the classifer you've trained on the source domain is general and has not overfitted on the source images.

With the AFRL, we wanted to see if we could implement UDA methods on two domain. The source domain were images in the electro-optical (EO) spectrum while the target domain were images in the synethic-aperture radar spectrum (SAR). See [this post]({{site.url}}/unicorn.md) for more information on those images (and another research project centered around them!). Here's an illustration of EO and SAR images and what we're trying to do.

![](/assets/img/da.png)

We looked at two popular UDA methods, [Source Hypothesis Transfer](https://arxiv.org/abs/2002.08546) and [Constrastive Adapation Network](https://arxiv.org/abs/1901.00976). Again, due to the sheer noise in SAR images, it was hard to learn a general representation of EO images that could be adapted to SAR. However, we achieved **relatively** good results, increasing the baselines accuarcy of upwards of 20%! So it was quite good.  

