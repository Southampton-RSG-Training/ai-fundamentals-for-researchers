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

The name comes from a loose analogy with biology. In the human brain, neurons receive signals from other neurons. If the combined signal is strong enough, the neuron "fires" and passes a signal onwards.

![A diagram of a neuron. Egm4313.s12 at English Wikipedia, CC BY-SA 3.0, via Wikimedia Commons](fig/neuron.png){alt='Neuron and myelinated axon, with signal flow from inputs at dendrites to outputs at axon terminals.'}

An artificial neuron works in a simplified mathematical way:

- It receives numbers as inputs.
- Each input is multiplied by a weight, which represents its importance.
- These weighted values are added together.
- The result is passed through a function that determines the output.
- That output is then sent to the next layer.

Note that artificial neural networks are inspired by biology, but they are not realistic simulations of the brain. They are mathematical models designed to detect patterns in data.

A single artificial neuron is rarely useful on its own but can be really powerful when combined with many other artificial neurons. We can arrange many neurons together to form a layer and then stack multiple layers together to create a neural network.


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

The word **deep** simply refers to the number of hidden layers. A shallow model might have one hidden layer. A deep model may have dozens or even hundreds of layers.

![A simplified diagram of an artificial neural network. Glosser.ca, CC BY-SA 3.0, via Wikimedia Commons](fig/artificial_neural_network.svg){alt='Artificial neural network with layer coloring'}

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout
### Feature Learning

A key reason deep learning differs from earlier machine learning approaches lies in how models learn from the features within the data.

Earlier machine learning approaches depended heavily on feature engineering. Researchers had to decide in advance which aspects of the data might be useful and then write code to extract them.

In image classification, for example, a researcher might calculate edge counts, colour histograms, or texture measures. The model would not see the raw pixels but instead would only see these hand-crafted feature measures. If the chosen features were poor, the model’s performance would suffer. A great deal of expertise and experimentation often went into designing the feature measures for a model.

This is not the case for deep learning. Instead of feeding the model carefully designed features, we provide the raw data, such as pixel values. A neural network with multiple layers then learns its own feature measures during training. Early layers might detect simple patterns like edges, while later layers combine these into more complex structures.

In short, traditional methods rely on humans to decide what matters in the data. Deep learning models learn what matters directly from the data itself, given enough examples and computing power.
::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

## Training a Neural Network

Training a neural network follows a repeated cycle.

1. The network receives an input and produces a prediction.
2. The prediction is compared with the correct answer.
3. The difference between them is calculated as an error.
4. This error signal is sent backwards through the network.
5. The weights are adjusted slightly to reduce future errors.

Sending the error backwards through the network is known as **backpropagation**.  We'll mention this again in the next episode in the context of large language models.

This process is repeated across many examples, often millions, and over many passes through the dataset.

::::::::::::::::::::::::::::::::::::: challenge 

## Try Training a Neural Network

You can experiment with the process of training a neural network interactively using tools such as [Tensorflow Playground](https://playground.tensorflow.org). Adjust the parameters and watch how decision boundaries change.

::::::::::::::::::::::::::::::::::::::::::::::::

### Why So Much Data and Computing Power?

Modern neural networks often contain millions or even billions of adjustable parameters. Training them involves:

- Processing very large datasets.
- Performing repeated calculations across all parameters.
- Iterating many thousands of times.

This requires significant computational resources, often specialised hardware. Without large datasets and substantial computing power, deep models tend to perform poorly.


## Types of Deep Learning

There are many neural network architectures, each suited to particular tasks.  Just a few common examples are discussed below.  

### Convolutional Neural Networks (CNNs)

CNNs are particularly effective for image and video analysis. They use specialised layers that focus on local patterns, such as edges and textures. Image classification tools such as [Google Vision image classification tool](https://cloud.google.com/vision) are built on this type of architecture.

### Recurrent Neural Networks (RNNs)

RNNs were designed to handle sequential data, such as time-series measurements or text. They process information step by step, maintaining a form of internal memory. In many applications, they have now been replaced by more advanced architectures.

### Transformers

Transformers are the foundation of most modern natural language processing systems. They are especially effective at modelling relationships within sequences of text and form the basis of contemporary large language models, which we will examine in the next episode.
 

To read more about different neural network architectures have a look at the [Neural Network Zoo](https://www.asimovinstitute.org/neural-network-zoo/), a cheat sheet for neural network architectures.

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

## How can I Train My Own Deep Learning Model?

Training a deep learning model from scratch is significantly more demanding than training a conventional machine learning model, but it is not out of reach for motivated researchers, particularly with access to institutional computing infrastructure and Research Software Engineering support. More commonly, researchers work with **pre-trained models** and adapt them, rather than training from scratch.

### What skills this requires

Deep learning requires all of the skills needed for conventional machine learning (programming in Python, data preparation, evaluation) plus additional capabilities. You will need familiarity with a **deep learning framework** such as PyTorch or TensorFlow, both of which have extensive documentation and active research communities.

**Access to appropriate hardware** is a practical requirement. Training deep learning models on a standard laptop CPU is rarely feasible for research-scale tasks. Most researchers use GPUs, either through institutional high-performance computing (HPC) facilities or cloud platforms such as Google Colab, which provides free GPU access for smaller experiments.

**Experiment management** becomes important at this level of complexity. Tracking which model configuration produced which results, managing large datasets, and handling training runs that may take hours or days requires a great deal of organisation and tools such as Weights & Biases or MLflow.

Deep learning also demands a somewhat deeper understanding of model architecture and training dynamics than conventional ML. You need enough conceptual understanding to diagnose when training is going wrong, for example, when a model is failing to learn, overfitting, or producing unexpected outputs.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### Transfer learning lowers the barrier considerably

The requirement to train a deep learning model entirely from scratch is rarer than it might appear. For many research tasks, a pre-trained model from a repository such as [Hugging Face](https://huggingface.co) or [PyTorch Hub](https://pytorch.org/hub/) can be downloaded and fine-tuned in a matter of hours on a modest GPU. The skills required for fine-tuning are closer to those needed for conventional ML than to the full deep learning training pipeline.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- Artificial neural networks consist of layers of weighted computational units inspired by biological neurons.
- 'Deep' refers to having multiple hidden layers that learn increasingly abstract representations.
- Training involves making predictions, measuring error, and adjusting weights using backpropagation.
- Deep learning excels at complex pattern recognition tasks such as image, audio, and text analysis.
- Large models require extensive data and computing resources to train effectively.

::::::::::::::::::::::::::::::::::::::::::::::::

## References

- [Neural Network Zoo](https://www.asimovinstitute.org/neural-network-zoo/)
- [Choosing the right deep learning model a comprehensive guide](https://www.artiba.org/blog/choosing-the-right-deep-learning-model-a-comprehensive-guide)

