---
title: "Deep Learning and Neural Networks"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is an artificial neural network?
- What does “deep” mean in deep learning?
- How do neural networks learn from errors?
- Why does deep learning require substantial data and computing resources?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Describe what an artificial neural network is using an analogy.
- Explain what "deep" means in deep learning.
- Identify types of tasks that deep learning excels at.
- Understand why deep learning requires a lot of data and computing power.

::::::::::::::::::::::::::::::::::::::::::::::::

## What is a Neural Network?

Deep learning is built on a concept called the artificial neural network.

The name comes from a loose analogy with biology. In the human brain, neurons receive signals from other neurons. If the combined signal is strong enough, the neuron “fires” and passes a signal onwards.

An artificial neuron works in a simplified mathematical way:

- It receives numbers as inputs.
- Each input is multiplied by a weight, which represents its importance.
- These weighted values are added together.
- The result is passed through a function that determines the output.
- That output is then sent to the next layer.

It is important to be clear that artificial neural networks are inspired by biology, but they are not realistic simulations of the brain. They are mathematical models designed to detect patterns in data.

A single artificial neuron is rarely useful on its own. When we arrange many neurons together, we form a layer. When we stack multiple layers together, we create a neural network.


## Layers, Depth and Feature Learning

A neural network is typically organised into three types of layers:

- An input layer, which receives the raw data.
- One or more hidden layers, where most of the computation happens.
- An output layer, which produces the final prediction.

As data passes through the network, each layer transforms it into a slightly more abstract representation.

For example, in image recognition:

- An early layer might detect simple edges and lines.
- A later layer might detect shapes or textures.
- A deeper layer might detect complex structures such as faces.

In text processing:

- Early layers might detect characters or short word patterns.
- Middle layers might represent words or phrases.
- Later layers might capture aspects of meaning or context.

This hierarchical pattern detection is one of the main strengths of deep learning.

The word **'deep'** simply refers to the number of hidden layers. A shallow model might have one hidden layer. A deep model may have dozens or even hundreds.

### Feature Learning

A key reason deep learning marked such a significant shift from earlier machine learning approaches lies in how models learn from the features within the data.

Earlier machine learning approaches depended heavily on feature engineering. Researchers had to decide in advance which aspects of the data might be useful and then write code to extract them.

In image classification, for example, a researcher might calculate edge counts, colour histograms, or texture measures. The model would not see the raw pixels. It would only see these hand-crafted data measures. If the chosen features were poor, the model’s performance would suffer. A great deal of expertise and experimentation often went into designing them.

Deep learning changes this. Instead of feeding the model carefully designed features, we provide the raw data, such as pixel values. A neural network with multiple layers then learns its own internal representations during training. Early layers might detect simple patterns like edges, while later layers combine these into more complex structures.

In short, traditional methods rely on humans to decide what matters in the data. Deep learning models learn what matters directly from the data itself, given enough examples and computing power.

## Training a Neural Network

Training a neural network follows a repeated cycle.

1. The network receives an input and produces a prediction.
2. The prediction is compared with the correct answer.
3. The difference between them is calculated as an error.
4. This error signal is sent backwards through the network.
5. The weights are adjusted slightly to reduce future errors.

This backward flow of error is known as **backpropagation**.

As an analogy for training a deep learning model, imagine standing on a foggy hillside and trying to reach the lowest point (the correct answer). You cannot see the whole landscape, but you can feel the slope under your feet. You take small steps downhill. Repeating this process eventually brings you closer to the lowest point.

In neural networks, the 'height' represents error. The model repeatedly takes small steps in the direction that reduces error.

This process is repeated across many examples, often millions, and over many passes through the dataset.

::::::::::::::::::::::::::::::::::::: challenge 

## Try Training a Neural Network

You can experiment with the process of training a neural network interactively using tools such as [Tensorflow Playground](https://playground.tensorflow.org) . Adjusting parameters and watching how decision boundaries change can help make these abstract ideas more concrete.

::::::::::::::::::::::::::::::::::::::::::::::::

### Why So Much Data and Computing Power?

Modern neural networks often contain millions or even billions of adjustable parameters. Training them involves:

- Processing very large datasets.
- Performing repeated calculations across all parameters.
- Iterating many thousands of times.

This requires significant computational resources, often specialised hardware. Without large datasets and substantial computing power, deep models tend to perform poorly.


## Types of Deep Learning

There are several major neural network architectures, each suited to particular tasks.

### Convolutional Neural Networks (CNNs)

CNNs are particularly effective for image and video analysis. They use specialised layers that focus on local patterns, such as edges and textures. Image classification tools such as [Google Vision image classification tool](https://cloud.google.com/vision) are built on this type of architecture.

### Recurrent Neural Networks (RNNs)

RNNs were designed to handle sequential data, such as time-series measurements or text. They process information step by step, maintaining a form of internal memory. In many applications, they have now been replaced by more advanced architectures.

### Transformers

Transformers are the foundation of most modern natural language processing systems. They are especially effective at modelling relationships within sequences of text and form the basis of contemporary large language models, which we will examine in the next episode.
 
:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Discussion

Deep learning has transformed image recognition and, in some contexts, now matches or exceeds human performance. Can you identify a research application in your field where this capability is useful or already in use?

:::::::::::::::::::::::: solution 

Examples may include:

- Analysing satellite imagery to detect environmental change.
- Identifying cell structures in microscopy images.
- Digitising and classifying historical documents.
- Transcribing and analysing handwritten documents

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- Artificial neural networks consist of layers of weighted computational units inspired by biological neurons.
- 'Deep' refers to having multiple hidden layers that learn increasingly abstract representations.
- Training involves making predictions, measuring error, and adjusting weights using backpropagation.
- Deep learning excels at complex pattern recognition tasks such as image, audio, and text analysis.
- Large models require extensive data and computing resources to train effectively.

::::::::::::::::::::::::::::::::::::::::::::::::



