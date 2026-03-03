---
title: "What is Artificial Intelligence?"
teaching: 25 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is AI?
- What are some categories of AI?
- Which factors have contributed to the AI boom over the last few years?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Give a working definition of Artificial Intelligence.
- Explain the difference between narrow AI and general AI.
- Describe how AI, machine learning, deep learning, and LLMs relate to each other using a nested diagram.


::::::::::::::::::::::::::::::::::::::::::::::::

## Defining AI

Artificial Intelligence, or AI, is a broad term. A useful working definition is:

**AI refers to computer systems that perform tasks which would typically require human intelligence.**

These tasks might include recognising images, understanding language, making recommendations, detecting patterns in data, or playing strategic games.

It is worth noting that AI is not a single technique or tool. It is an umbrella term covering a wide range of approaches developed over several decades.

### A Brief History in Three Phases

**Rule-based systems (1950s–1980s)**
Early AI systems relied on explicit rules written by humans. For example, a medical expert system might contain hundreds of “if–then” statements created by specialists, designed to lead to a diagnosis. These systems could perform well in narrow domains but were inflexible and difficult to scale.

**Statistical approaches (1980s–2000s)**
Researchers began using probability and statistics to handle uncertainty and variability in real-world data. Instead of hard-coded rules, systems estimated likelihoods and made predictions based on data.

**Modern machine learning (2000s–present)**
With increased data and computing power, systems began to "learn"" patterns directly from large datasets. Rather than being told exactly what to do, they infer patterns from examples.

Throughout all these phases, the goal has remained broadly the same: to build systems that can carry out tasks we associate with intelligent behaviour.


### Narrow AI vs General AI

A crucial distinction is between narrow AI and general AI.

**Narrow AI** (also called weak AI) refers to systems designed to perform a specific task. Examples include image classification, language translation, and recommendation systems. All AI systems in practical use today fall into this category. They can perform their assigned task very effectively, but they cannot transfer that ability broadly to unrelated domains.

**General AI** (also called strong AI or Artificial General Intelligence) refers to a hypothetical system with human-level reasoning ability across a wide range of tasks. Such a system would be able to learn, reason, and adapt flexibly in unfamiliar situations. 

General AI is the overarching goal of many AI companies but, at present, general AI does not exist. When discussing real-world research and applications, we are dealing with narrow AI.


## The AI Family Tree

AI can be visualised as a set of nested fields. Each inner layer represents a more specific set of techniques within the broader area.

```
┌─────────────────────────────────────────┐
│  Artificial Intelligence                │
│  ┌───────────────────────────────────┐  │
│  │  Machine Learning                 │  │
│  │  ┌─────────────────────────────┐  │  │
│  │  │  Deep Learning              │  │  │
│  │  │  ┌───────────────────────┐  │  │  │
│  │  │  │  LLMs (e.g. GPT, etc) │  │  │  │
│  │  │  └───────────────────────┘  │  │  │
│  │  └─────────────────────────────┘  │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘
```
We can interpret this diagram from the outside in:

- **Artificial Intelligence** is the broadest category. It includes any computational method aimed at performing tasks associated with intelligence.
- **Machine Learning** is a subset of AI focused on systems that learn patterns from data rather than relying purely on hand-written rules.
- **Deep Learning** is a subset of machine learning that uses multi-layered neural networks to model complex patterns.
- **Large Language Models (LLMs)** are a specific application of deep learning, trained on vast amounts of text data to generate and understand language.

As the course progresses, we will move gradually from the outer layer towards the inner layers, building conceptual understanding at each step.


## Why AI Now?

AI research has existed for decades, so why has it become so prominent recently?

Three enabling factors have converged:

1. **Data availability**: The growth of the internet, digital services, sensors, and large-scale data collection has created vast datasets for training models.

2. **Computing power**: Graphics Processing Units (GPUs), originally developed for rendering images in gaming, turned out to be highly effective for the kinds of parallel computations used in deep learning.

3. **Algorithmic advances**: New training methods and model architectures have significantly improved performance, particularly in areas such as image recognition and natural language processing. For example the transformer architecture that underpins most large language models (transformer is the 'T' in ChatGPT)

The current wave of AI is therefore not the result of a single breakthrough, but the interaction between data, hardware, and improved methods.



::::::::::::::::::::::::::::::::::::: challenge 

## Noticing AI

Can you think of an AI system you have encountered recently? What task was it performing?

Write down one example and briefly describe what input it received and what output it produced.

:::::::::::::::::::::::: solution 

Examples might include:

- A spam filter classifying incoming emails as “spam” or “not spam”.
- A recommendation system suggesting articles, products, or videos based on previous behaviour.
- Autocomplete predicting the next word or line of code while you type.
- A medical imaging tool highlighting areas of a scan that may require clinical attention.

In each case, the system is performing a specific task based on patterns learned from data.

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::




::::::::::::::::::::::::::::::::::::: keypoints 

- Artificial Intelligence is a broad field concerned with systems that perform tasks associated with human intelligence.
- All AI systems currently in use are narrow, task-specific systems.
- Machine learning is a subset of AI that learns from data.
- Deep learning is a subset of machine learning based on multi-layered neural networks.
- Large language models are a specific type of deep learning model focused on language.
- The recent growth of AI has been driven by data availability, increased computing power, and algorithmic advances.

::::::::::::::::::::::::::::::::::::::::::::::::


