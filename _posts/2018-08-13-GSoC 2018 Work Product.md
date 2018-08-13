---
layout: post
title: GSoC'18 Work Product
---
My project for GSoC 2018 is [DroidBot with AI](https://summerofcode.withgoogle.com/projects/#5858149874008064) which was an exploratory research work to see how machine learning an artificial intelligence can help in automated dynamic analysis of Android applications. The explored methods are illustrated in this blog post which also serves as the final evaluation for GSoC 2018. The research is still open-ended with the need of more mature outcomes so that it can finally be integrated with [Droidbot](https://github.com/honeynet/droidbot). 

# Project overview

The major task to be tackled in this project is to increase the code coverage of Android applications using AI.Currently droidbot performs back box testing using the GUI elements. So I have focussed only on black box testing methods without assuming access to any previous data/information regarding the code structure. Currently the work done is based on:
* **Classical natural language processing**
* **Convolutional Neural Networks**
* **Recurrent Neural Networks**

# What we planned

During the community bonding period, my GSoC mentor Yuanchun Li discussed with me about the proposal for my project. The ultimate goal was to create embeddings for each UI view in each UI page which can be used for three major tasks:
* **UI view classification**
* **UI page classification**
* **Dependency analysis between UI views**

The path along which we decided to go along was to start with classical NLP concepts like Bag-of-words and TF-IDF which could give a reliable baseline following which we decided to implement deep learning methods like CNN for UI page screenshot classification and RNN for UI view XML classification.

# What I have done

1. **Classical NLP concepts**
  - Used for both UI page and UI view classification
  - Consisted of four major parts - Feature Extraction, Vector Transformation, Labelling and Inference
  - Feature extraction was done by extracting all the DOM elements from the XML files and representing the words in them as feature vectors
  - Vector Transformation was done by the classic NLP algorithms Bag-of-words followed by TF-IDF which enabled the feature vectors to be represented in the term document format Once this was done, reduction of dimensionality was done using LSI transformation which helped convert the term document format into document concepts
  - Labeling of the vectors created was done using a fixed size dictionary which was predefined by manually studying the vectors
  - Inference was done using the cosine similarity between the dimensionality reduced vectors created in the second step. The closest ones in the cosine similarity metric are considered similar so by comparing the vectors in the training and testing set, inferecing was done
  - The performance of UI view classification is 82% whereas that for UI page classification is x%
  
2. **Convolutional Neural Networks**
  - Used for UI page classification
  - Consisted of three major parts - Labelling, Training and Inference
  - Labelling was done using fetching the activity_name from the XML files followed by applying the Affinity Propagation algorithm using Levenshein distance metric. This was done to cluster the activity names based on similarities so that some major clusters could be named under the same class. After this, three major classes were identified for now ( can increase with increase in the dataset size). These classes are the login, onboarding and settings classes
  - Training was done on the VGG16 CNN network on the Google Colaboratory setup with NVIDIA Tesla K80 GPU
  - Finally inference was done on the holdout dataset which gave accuracies of close to 60%
  
3. **Recurrent Neural Netwoks**
  - Used for UI page classification
  - Consisted of three major parts - Labelling, Training and Inference, of which Labelling is in the same way as done previously
  - Training was done on a word based bidirectional RNN network and an attention based LSTM on the Google Colaboratory setup with NVIDIA Tesla K80 GPU
   - Finally inference was done on the holdout dataset which gave accuracies of close to y%

# What I haven't done and future scope

1. Unable to work on implementing the Graph Convolutional Network which would have ideally given the UI page embeddings 
2. Unable to work on UI views embeddings beyond classical NLP methods
3. Unable to integrate any method with the Droidbot setup

The major reasons for not being able to get the above ideas working is that the Graph Convolutional Network(GCN) would require big graphs and lots of data which I was unable to manage with my current setup. The data collection can be easily done using Droidbot itself. Some of the ideas and workarounds that I have in mind to make the algorithms implementable or make the existing ones mature are:
* **Use of text based methods rather than image based methods** - Since the layouts of Android applications are mostly rectangular based, and texts are used to convey information to users, image based methods are likely to perform poorer than text based methods. As already seen, untuned classical NLP methods work better than highly tuned CNN, it is unlikely CNNs can perform better for such datasets. 
* **Use of data augmentation in CNN** - If at all CNNs are to be used, use of keras' data augmentation function can help enlarging the dataset, however use of the rotation feature is to be avoided at all costs
* **Use of predefined embeddings for GCN** - Since the graphs created from the UI pages and views are bound to be too small for most GCN algorithms, it is better to used pre-trained embeddings for UI pages and views from the RNN or CNN algorithms as a starting point for including neighbourhood features in the UI view or page embeddings via GCN.
* **Use of classical NLP models for integration with Droidbot** - Currently with lower data volumes, it is suggested to use classical NLP models instead of deep learning models for automated dynamic analysis of Android applications.

# Final words

I would like to thank my mentor Yuanchun Li at The Honeynet Project for being highly supportive and co-operative with me during the coding period because of which I enjoyed and learnt a lot.


