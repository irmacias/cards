---
layout: post
title:  "Sentiboard"
date:   2019-04-02 10:51:47 +0530
categories: jekyll update
img: sentiboard.jpg
categories: [one, two]
---
https://devpost.com/software/sentiboard
Imbuing personality into product is a feature recently sought out by several leading companies in the consumer product industry. In the gaming industry, Corsair is a key leader with its customizable gaming peripherals, allowing users to easily personalize their own gear using custom LED lighting. The ability to demonstrate one’s own personal profile becomes much more profound, while also enhancing the user’s experience. With Sentiboard, we take this desire even further by linking the user’s profile not only with their custom preset, but also with their current emotional state, thereby allowing a more dynamic setting and creative venture.


## What it does

SentiBoard uses chat logs and facial recognition data to carefully analyze the user’s mood. It then changes the color of the keyboard LEDs to display how the user is feeling as he/she is using it. Warm colors like red, orange, and yellow represent heightened sense of feeling such as anger, annoyance, and disgust while cool colors like green, blue, and purple represent mood associated with relaxation and happiness.


## How we built it

SentiBoard consists of three integrated components:

1) Natural language processing - used to analyze mood from the user’s chat logs. SentiBoard uses the Natural Language Toolkit (NLTK), a Python library, which provides useful tools to classify text. In this project, NLTK was used to determine either a positive or negative connotation of one’s text.

2) Expression recognition - used to determine the user’s mood through a live webcam. Image recognition is done with OpenCV for Python. A Haar-based cascade is used to extract faces from backgrounds, while Fisherfaces are used to classify the different emotions. Training images were primarily taken from the [CK+](http://www.consortium.ri.cmu.edu/ckagree/) and [JAFFE](http://www.kasrl.org/jaffe.html) databases. Several pictures of the team’s members, as well as stock photos from Google were used. Faces were classified as either being “Happy”, “Sad”, “Angry”, or “Neutral”.

3) Keyboard RGB control - used to display different color lighting based-on the user’s mood found with the two parts mentioned above. Specifically, Corsair’s CUE SDK with a Python wrap was used to program a Corsair K70 LUX RGB. Transition of the colors were based on both the connotations of text and facial expressions.


## Challenges we ran into

On the front-end side of our project, the main problem we had was working around the provided SDK to create appropriate features for our design. An example of this would be with regards to retrieving the color value of individual keys, which we ended up working around through an algorithm designed specifically to transition between given states, without the need for necessary retrieval of values. While this may have been limiting to our overall freedom of implementation, it certainly tested our skills as problem-solvers. With respect to the back-end design of our project, the main issue we ran into dealt with the integration of all the components we created which includes both using and transforming appropriate data to control the lighting properties of our board. Also on the front-end side, it should be noted that none of the team members had any decent experience in front-end design.

On the back-end side of the project, errors were primarily met with an inconsistent classification of text using the NLTK. Further work here will focus on combining different corpuses, as well as examining common sentence structures in chat rooms. Emotion recognition worked at a better rate, but could be improved with a much larger dataset (not feasible in a hackathon) or by examining and classifying facial expressions based on points using algorithms like support vector machines.


## Accomplishments that we're proud of

We are most proud of achieving our goal of the project: creating a keyboard with lighting that reacts to the user’s expressions. Integration was full, and the colors did indeed follow the expressions. It should also be noted that the majority of the group did not have much real-life coding experiences, and working on this project allowed for experience in not just coding, but also in learning APIs and team programming skills.


## What we learned

– Corsair CUE SDK

– NLTK

– Fisherfaces and readily available databases

– GUI/Front-end interfacing using Tkinter with Python

– Code integration/sharing (i.e. GitHub)

– Debugging errors in software


## What's next for SentiBoard

On the technical side, improvements need to be made for increasing the accuracy of (especially) the text connotation classification, as well as the facial expression recognition. Future applications and extensions of the project may include:

– Using backlighting, as well as display color contrast and audio equalization, to subconsciously soothe frustrated users

– Color changing for pre-existing lighting layouts


## References

_CK+ Facial Expression Detection:_

– van Gent, P. (2016). Emotion Recognition With Python, OpenCV and a Face Dataset. A tech blog about fun things with Python and embedded electronics. Retrieved from:
http://www.paulvangent.com/2016/04/01/emotion-recognition-with-python-opencv-and-a-face-dataset/

– Kanade, T., Cohn, J. F., & Tian, Y. (2000). Comprehensive database for facial expression analysis. Proceedings of the Fourth IEEE International Conference on Automatic Face and Gesture Recognition (FG'00), Grenoble, France, 46-53.

– Lucey, P., Cohn, J. F., Kanade, T., Saragih, J., Ambadar, Z., & Matthews, I. (2010). The Extended Cohn-Kanade Dataset (CK+): A complete expression dataset for action unit and emotion-specified expression. Proceedings of the Third International Workshop on CVPR for Human Communicative Behavior Analysis (CVPR4HB 2010), San Francisco, USA, 94-101.

_JAFFE Facial Expression Detection:_

– Michael J. Lyons, Shigeru Akemastu, Miyuki Kamachi, Jiro Gyoba.
Coding Facial Expressions with Gabor Wavelets, 3rd IEEE International Conference on Automatic Face and Gesture Recognition, pp. 200-205 (1998).
