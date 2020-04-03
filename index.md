---
title: Impact of Intensity Normalization of MS Lesion Sementation in MRI
author:
  - name: John Muschelli
    email: jmusche1@jhu.edu
    affiliation: JHSPH
address:
  - code: JHSPH
    address: Johns Hopkins Bloomberg School of Public Health, Department of Biostatistics, 615 N Wolfe St, Baltimore, MD, 21205
abstract: |
  MS lesion stuff MRI
journal: "International Conference on Information Processing and Management of Uncertainty in Knowledge-Based Systems"
date: "2020-04-03"
bibliography: refs.bib
output: 
  bookdown::pdf_book:
    base_format: rticles::elsevier_article
    keep_tex: true
    number_sections: yes
    keep_md: true
  html_document: 
    toc: true
---



# Introduction

Multiple sclerosis (MRI) is a neuro-inflammatory disease which causes pathology in the brain, namely lesions.  These lesions are potential biomarkers of clinical symptomology and disease progression.  One way to ascertain the extent of these lesions is to use clinical magnetic resonance imaging (MRI).  A number of methods have been developed for lesion segmenation in MRI scans.  These methods aim to remove the need for manual segmentation from human readers, which is costly, time-consuming, and has issues with intra- and inter-reader variability.  

A number of increasing methods are using deep learning, namely convolutional neural networks (CNNs), to segment the lesion from the image CITE.  As many of these methods have shown a high degree of accuracy, we believe this area will deliver fruitful methods for segmentation.  Many of these methods focus on changes or adaptation to the architecture of the network to increase the accuracy of the method.  Many of these methods are trained and tested on one scanning protocol from one site and one scanner. As more data is aggregated from multiple scanners and sites, especially with efforts such as the MSPATHS, we believe multi-site harmonization techniques will be required to make these methods generalizable.  As MRI are measured in arbitrary units, we believe this makes the problem "harder" for networks to learn, even within single-site studies.

Multiple MRI sequences are commonly measured in MS protocols, namely T1-weighted (T1), T2-weighted (T2), T2-weighted fluid-attenuated inversion recovery (FLAIR), and proton density (PD) sequences.  As these sequences can also have quite different intensity ranges, performance may increase when performing intensity normalization on each sequence to make the measures more comparable.  


A number of intensity normalization techniques are available.  We can break these methods into subject-level and population-level normalization techniques.  Subject-level normalization uses information only from the individual subject.  In most cases, these 
Many of these use statistics or moments of the image to center and/or scale the image.  For example, one of the most common techniques is min/max normalization, where all intensities of the image have the minimum subtracted and then divided by the difference in the max and min values, to map the intensities to a [0, 1] range.  These methods can be done 

Population-level normalization techniques.

Both subject- and population-level normalization can perform normalization within-sequence, across-sequence, or use joint measures to inform within-sequence normalization.  For example, the WhiteStripe method estimates a normal-appearing white matter (NAWM) mask from a T1 or T2 sequence, estimates the mean and standard deviation of the intensities within this mask, then centers the image by the mean and scales it by the standard deviation.  When both T1 and T2 sequences have been collected, WhiteStripe can also center and scale based on the intersection mask estimated by each sequence.  Thus, within-sequence and joint-normalization are possible.  Alternatively, histogram matching could be performed (may not be a good idea) on the T1 and T2 sequences to try to get their intensities similar. 

We propose to study the effects of different intensity normalization techniques on a number of performance metrics of lesion segmentation, within one neural network.  We chose the FLEXCONN neural network because 1) the method performed well (did it?) in previous work, 2) the data FLEXCONN was trained on is (publicly?) available, and 3) the authors have provided software to fit and train their model. 

## Acknowledgments
This work has been been supported by the XXX and XXX grants from the National Institute of Neurological Disorders and Stroke at the National Institutes of Health (NINDS/NIH). 




References {#references .unnumbered}
==========
