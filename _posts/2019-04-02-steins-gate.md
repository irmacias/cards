---
layout: post
title: Classifying the Voices of Steins;Gate Using Convolutional Neural Networks
img: stein.jpg
---
Final Project for MIT's Machine Learning Course: 6.867

The purpose of the project was to identify voice actors while they are speaking at certain times during an anime. We chose Steins;Gate to test our implementation.
Please refer to the PDF below for a full description of the final project. Code is available upon request (had to be kept private)!

##Introduction

For our final project we developed a convolutional neural network (CNN) capable of classifyingrandom  voice  samples  of  the  various  characters  of  the  anime  (Japanese  animation)  Steins;Gateaccording to the voice actors/actresses that produced them.  Throughout this paper we discuss ourmethods of data processing/collection, the architecture of our CNN implementation, the final resultsof our model, and potential improvements.

##Tools used
The  entire  project  was  written  in  Python, primarily  utilizing  the  deep-learning  frame-work, PyTorch to construct and train our neural networks.  Data collection and labelling was done using both Audacity (audio analysis  software)  and Praat  (speech  analysis software), both of which allowed us to produce precise annotations for the raw Steins;Gate audio.  Finally, much of the data handling operations were handled by the h5py library.

<iframe src="https://drive.google.com/file/d/1PdtE6u_0eZ_-9miAZ6UhMYq25juiH4VJ/preview" width="800" height="480"></iframe>
