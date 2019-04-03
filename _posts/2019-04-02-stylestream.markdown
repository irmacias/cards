---
layout: post
title:  "Stylestream"
categories: jekyll update
img: stylestream.jpg
categories: two
---
HackMIT 2017 Project.

Link to code here: https://github.com/justyucode/2017_audio_transfer


## What it does
We constructed StyleStream using variational autoencoders  (VAEs), networks whose purpose is to have the ability seamlessly transfer styles between music tracks. To illustrate the idea, consider two song pieces, one whose genre is rock and the other whose genre is classical. Now take the feel and style of the rock song and project it onto the classical song and what is produced is the same classical song as a base but with a new, refreshing rock style that captures the and combines two entirely different pieces of music into one. Style stream does this, using music from several thousand rich samples.

## How we built it

Building and training a successful model requires a large and diverse dataset that requires heavy pre-processing. Our dataset consisted of WAV file spectrograms that had to be translated from MIDI to WAV and then had their respective spectrograms extracted and transformed. In order to be able to use these spectrograms we constructed an aggregate Fourier transformed dataset of over 7000 songs of various styles for future tasks on audio reconstruction. While doing so, there was some necessary quality loss that had to be incurred when transforming the music. This is important as the music that was outputted from the model after reconstruction had some loss of quality. It is important to note, however, that we were able to optimize this operation and retain most if the significant features that the WAV file contained.

We wish to construct a network that is able to transfer styles between various different types of songs. To construct this, we train a recurrent variational autoencoder similar to architecture of the DRAW paper to encode and decode songs of various  styles. To transfer styles between songs, we first train an autoencoder A1 on a specific style of music. We then transfer music from a different style by  transform S2 to S3 using A1 to encode and decode S2. In this way, the autoencoder is able to generate S3 in the style of S2.
