---
layout: page
title: Projects
permalink: /projects/
---

In this page there are examples of machine learning projects and
predictive models that I worked with during my career in different
companies.

# Speaker recognition


Automatic speaker recognition project aims to recognize individual
people (verification task) in a data base from their voices. I worked
on the machine learning and also on the preprocessing voice separation
algorithms. The figures bellow illustrates the input audio where there
are two channels. One channel is called remote channel and it has the
voice of the local operator and the voice of the speaker that we are
interested. The other channel called local channel has only voice of
the operator.  I developed an algorithm to extract the operators voice
of the remote channel and remove silence on this channel. The
algorithm utilizes the autocorrelation properties of random signal in
order to perform this task.

<img src="{{ site.baseurl }}/images/voice_signal_1.png" alt="Input signal" width="300" height="300">

<audio controls controlsList="nodownload">
<source src="{{ site.baseurl }}/images/lm128_dec_rep3.wav" type="audio/wav">
Raw data input with silence and two speaker
</audio>

The figure bellows shows the expected output.

<img src="{{ site.baseurl }}/images/voice_signal_output.png" alt="Pre-processed signal with the voice of the desired speaker and without silence" width="300" height="150">

<audio controls controlsList="nodownload">
<source src="{{ site.baseurl }}/images/lm128_dec_rep1_preprocessed.wav" type="audio/wav">
Pre-processed output
</audio>

The **MFCC** (Mel frequency cepstrum coefficients) features was
extract from the preprocessed audio. A *Bayesian classifier* was built
with these features and a **GMM** (Gaussian Mixture Models). One of
the major challenges of this project are the fact that different
microphones, noise, channel transmission and environment change the
speech signature of the speaker and therefore make harder to verify
the identity of the speaker.



# Crop Recognition and Crop date determination

Crop Recognition and Automatic Determination of the Planting Date
project (developed in **IDL**) which analyzes satellite images in
order to determine planting dates and the crops planted in producing
regions.

# Wrinkle Analysis

I developed an image processing algorithm (**C, OpenCv**)to extract
facial wrinkles. A score was attributed to the wrinkles and these data
were correlated with medical data in order to determine skin age.

It was a marketing project that was being developed for a cosmetic
company to recommend products to their clients based on their skin
age.

# Magnetic noise attenuation system

Magnetic noise attenuation system: In this project, I designed a
compensation coil in order to reduce magnetic noise in magnetic
resonance scanner room. Also, I worked on the implementation of the
attenuation algorithm (C) deployed in **DSPIC**.

# RAoP

**This is a work in progress**

In this project data from online community Random Act of Pizza
([RAoP](https://www.reddit.com/r/Random_Acts_Of_Pizza/)) forum was
analyzed. The data is a collection of post where reddit's users are
requesting free pizza. Sentimental analyses were performed in the data
and the findings were used to build a model to predict if the post
written by the user will be successful. The link for the analysis can
be found
[here](https://github.com/leandroohf/raop/blob/master/README.md) and a
better explanation with more detail can be found in the links below.

# Kaggle Liberty

First Kaggle competition. The task is to predict a transformed count
of hazards or pre-existing damages using a dataset with anonymized
data.  I wrote a report explaining my journey (steps)
[here](https://github.com/leandroohf/Public_Liberty_Mutual_Group_Property_Inspection_Prediction)
    
# Virtual Eye (VEye)

Project developed during my MSc. I developed a computational framework
in C++ capable to reproduce the optical properties and physiological
phenomena of the human visual system. To accomplish that, I worked by
manipulating 3d meshes using algorithms such as "door-in door-out",
developed realistic ray traces algorithms and schematics models of the
human eye was built and in addition in-vivo data obtained from corneal
topography machine was introduced in these models allowing the
framework to determine optical properties of real cornea's topologies
such as dipotry power, high order aberrations using Zernike’s
polynomials and Point spread function (PSF) using Fourier
transform. The obtained results agree with related work in literature
and simulations with in-vivo data are according with the results
produced by a commercial wave-front device.

You can find my thesis
[here.](http://www.teses.usp.br/teses/disponiveis/55/55134/tde-09052008-161636/en.php)

The images below illustrate VEye's simulation where ray trace
algorithm is used to form a retinal image of the object in the scene
(Lena's image) in a schematic eye model.

<img src="{{ site.baseurl }}/images/proj_cone_a.png" alt="Virtual eye: ray trace" width="300" height="300">

<img src="{{ site.baseurl }}/images/proj_cone_b.png" alt="Virtual eye: ray trace lateral view" width="250" height="250">

The next picture is the image formed in the retina of the schematic
eye model where the in-vivo cornea has **ceratocone** and health
cornea.

<img src="{{ site.baseurl }}/images/lena_normal.png" alt="Lena normal" width="200" height="200">

<img src="{{ site.baseurl }}/images/lena_ceratocone.png" alt="Lena normal" width="200" height="200">
