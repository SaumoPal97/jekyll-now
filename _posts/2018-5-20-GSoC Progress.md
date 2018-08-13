---
layout: post
title: GSoC'18 Progress 
---

This will contain the timeline of my proposed work and my progress through it to ensure that I am on track.

## Community Bonding Period
* Familiarising myself with the following papers 
  - [Using Semantic Similarity in Crawling-based Web Application Testing](http://castman.net/static/file/paper/icst17.pdf)
  - [Automation of Android Applications Testing Using Machine Learning Activities Classification](https://arxiv.org/pdf/1709.00928.pdf)
  - [Inductive Representation Learning on Large Graphs](https://arxiv.org/pdf/1706.02216.pdf)
  - [ERICA: Interaction Mining Mobile Apps](http://ranjithakumar.net/resources/deka-uist2016-erica.pdf)
  - [Webzeitgeist: Design Mining the Web](http://vis.stanford.edu/files/2013-Webzeitgeist-CHI.pdf)
  - [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
  - [Attention based Bidirectional Long Short-Term Memory networks](http://www.aclweb.org/anthology/P16-2034)

## Phase 1
This phase will be dedicated for implementation of the first paper with some help from second paper.
* Week 1
  - Analysing the [Rico](http://rico.interactionmining.org/) dataset to find the features to include in the analysis[DONE]
  - Working upon building the corpus from the json files in the above dataset (size above 20GB)[DONE]
* Week 2
  - Implementing the bag-of-words, tf-idf and LSI trasformation using the above corpus to obtain the set of vectors[DONE]
* Week 3
  - Writing a script for labelling input topics using a pre-defined dictionary inspired from second paper[DONE]
  - Implementing the cosine similarity of vectors obtained[DONE] 
* Week 4
  - Integrating with Rule based method
  - Analysing the accuracy and performance on a hold-out dataset[DONE]
  
## Phase 2
This phase will be dedicated for implementation of the third paper with some help from fourth paper and use of Convolutional Neural Networks. 
* Week 1
  - Working on UI labelling strategies by utilizing ideas from fourth paper along with manual inspection[DONE]
  - Writing script for labelling the UI activities from the Rico dataset used above[DONE]
* Week 2
  - Implementing CNN to train on the above dataset and test on a hold out dataset for classifying the UI activities[DONE]
  - Comparing performances across various pre-trained CNN models like Inception[DONE]
* Week 3
  - Comparing the method from Phase 1 with this method and with word level bidirectional RNN described in the last two links[DONE]
* Week 4
  - Working on integrating the embeddings obtained from the fully connected penultimate layer of the CNN as a starting point for graph embeddings as described in the fourth paper (requires a little more research)
  
## Phase 3
This phase will be dedicated for implementation of the last two papers for use of Recurrent Neural Networks.
* Week 1
  - Working on implementation of word level bidirectional RNN[DONE]
  - Preparation of the training and testing datasets from the UI activity xml files[DONE]
* Week 2
  - Working on implementation of attention based bidirectional LSTM[DONE]
  - Training the above networks on Google Colaboratory[DONE]
* Week 3
  - Preparation of the final documentation and exploration of future work and scope of the GSoC project[DONE]
* Week 4
  - Preparation of the final product submission blog and final commits[DONE]

