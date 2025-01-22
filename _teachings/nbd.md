---
layout: page
title: National Biomechanics Day
description: introduction to computer vision
img: assets/img/epoch3.png
importance: 1
category: work
related_publications: false
---

Every year, SRALab hosts local high school students and provides bite sized summaries of the different biomechanics research projects going on in the organization. I've previously helped some students from CBM present on myoelectric control for prosthetic devices, but this year decided to show the students something more related to my work.


Way back at WashU, [my friend Taylor](https://github.com/kwsp) and I created a [fun tool](https://gangsta.business/) to put sunglasses on any picture. I thought that since this type of computer vision permeates the world around us now (Face ID, Snapchat filters, and Face tracking), it would be cool to introduce students to how these models are trained, highlight their utility for our biomechanics research, and finally some limitations for people with disabilities. 

As an important part of training machine learning models is the data, I created a tool for students to annotate the location of a person's eyes on images (some of their teachers). In this way they could really understand what is needed to create these models. 

I stored all their annotations in a database and in real time trained a CNN to take an image and output the coordinates of the eyes. Through the training process, they were able to see how the model started out performing quite poorly at the task, but after feedback (from gradient descent) improved.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/epoch1.png" title="Initial Model Output" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/epoch2.png" title="Getting Better" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/epoch3.jpg" title="Model finds eyes" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The target eye annotation coordinates is shown in blue. Initially (left), the model is quite poor at identifying the eyes in the image. After a couple iterations of training (middle) it starts to realize that the eyes are generally in the center of the image. After 1000 iterations, it can find the eyes in the held out test image.
</div>

You can find my presentation [here](https://docs.google.com/presentation/d/14WLDOzutsY6R0Azm_1mp9VM_jFHMh0Pr/edit?usp=sharing&ouid=104758335792068799422&rtpof=true&sd=true). Here is the [repository](https://github.com/peifferjd/NBD-24/tree/main) for the data annotation tool using [Streamlit](https://streamlit.io/), the database to store the annotations using [Datajoint](https://www.datajoint.com/), and blazing fast CNN training using [Jax](https://jax.readthedocs.io/en/latest/) and [Equinox](https://docs.kidger.site/equinox/).
