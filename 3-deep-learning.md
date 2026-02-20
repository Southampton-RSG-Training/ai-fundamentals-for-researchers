---
title: "Deep Learning and Neural Networks"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 



::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Describe what an artificial neural network is using an analogy.
- Explain what "deep" means in deep learning.
- Identify types of tasks that deep learning excels at.
- Understand why deep learning requires a lot of data and computing power.

::::::::::::::::::::::::::::::::::::::::::::::::

## What is a Neural Network?
- Biological analogy: neurons fire when stimulated; artificial neurons activate when their inputs are strong enough.
- An artificial neuron takes in numbers, applies a weight to each, adds them up, and passes the result forward.
- Neural networks are *inspired* by biology but are not simulations of the brain.
- Single neuron → layer of neurons → multiple layers = a neural network.

## Layers, Depth and Feature Learning
- A network processes data through layers: *input layer → hidden layers → output layer*.
- Each layer learns to detect increasingly abstract patterns:
  - Image recognition example: layer 1 detects edges → layer 2 detects shapes → layer 3 detects faces.
  - Text example: layer 1 detects characters → layer 2 detects words → layer 3 detects meaning.
- "Deep" simply means many hidden layers (typically dozens to hundreds in modern models).
- Contrast with older "shallow" machine learning: deep learning can learn its own features; older methods required humans to design features manually.

## Training a Neural Network

- Conceptual walkthrough:
  - The network makes a prediction.
  - The error is calculated (how wrong was it?).
  - The error signal flows *backwards* through the network, adjusting weights to reduce the error.
  - Repeat millions of times across the training data.
- Try out adjusting the parameters in a neural network in [tensorflow playground](https://playground.tensorflow.org) 
- Introduce *gradient descent* as a metaphor: imagine rolling a ball downhill to find the lowest point (minimum error).
- Why this needs compute: millions of parameters, millions of examples, many thousands of repetitions.


## Types of Deep Learning
  - **Convolutional Neural Networks (CNNs):** excellent at image and video analysis. Example of [Google Vision image classification tool](https://cloud.google.com/vision)
  - **Recurrent Neural Networks (RNNs):** designed for sequential data like time-series; now largely superseded by Transformers.
  - **Transformers:** the architecture behind most modern NLP tools and LLMs (to be explored in Episode 4).

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Discussion

Deep learning has transformed image recognition — now matching or exceeding human accuracy in some tasks. Can you think of a research application in your field where this might be useful or is already used?
:::::::::::::::::::::::: solution 

(Possible prompts: satellite imagery analysis, microscopy, document digitisation, audio transcription.)
:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::: callout



::::::::::::::::::::::::::::::::::::::::::::::::






::::::::::::::::::::::::::::::::::::: keypoints 



::::::::::::::::::::::::::::::::::::::::::::::::



