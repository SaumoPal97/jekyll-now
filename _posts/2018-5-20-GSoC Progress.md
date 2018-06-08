---
layout: post
title: GSoC'18 Progress 
---

This will contain the timeline of my proposed work and my progress through it to ensure that I am on track.

## Community Bonding Period
* Familiarising myself with the following papers 
  - [Using Semantic Similarity in Crawling-based Web Application Testing](http://castman.net/static/file/paper/icst17.pdf)
  - [Automation of Android Applications Testing Using Machine Learning Activities Classification (https://arxiv.org/pdf/1709.00928.pdf)
  - [Inductive Representation Learning on Large Graphs](https://arxiv.org/pdf/1706.02216.pdf)
  - [Webzeitgeist: Design Mining the Web](http://vis.stanford.edu/files/2013-Webzeitgeist-CHI.pdf)

## Phase 1
This phase will be dedicated for implementation of the first paper with some help from second paper.
* Week 1
  - Analysing the [Rico](http://rico.interactionmining.org/) dataset to find the features to include in the analysis[DONE]
  - Working upon building the corpus from the json files in the above dataset (size above 20GB)[DONE]
* Week 2
  - Implementing the bag-of-words, tf-idf and LSI trasformation using the above corpus to obtain the set of vectors[DONE]
* Week 3
  - Writing a script for labelling input topics using a pre-defined dictionary inspired from second paper
  - Implementing the cosine similarity of vectors obtained 
* Week 4
  - Integrating with Rule based method
  - Analysing the accuracy and performance on a hold-out dataset
  - Integrating with the [DroidBot](https://github.com/honeynet/droidbot) 
  
## Phase 2
This phase will be dedicated for implementation of the third paper.
