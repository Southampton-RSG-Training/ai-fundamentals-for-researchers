---
title: "Machine Learning - Teaching Computers from Data"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- How is machine learning different from traditional programming?
- What are supervised, unsupervised, and reinforcement learning?
- What does it mean to train and test a model?
- What is overfitting, and why does it matter?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what machine learning is and how it differs from traditional programming.
- Distinguish between supervised, unsupervised, and reinforcement learning.
- Describe the concept of training, testing, and overfitting in plain language.
- Give a domain-relevant example of a machine learning application.

::::::::::::::::::::::::::::::::::::::::::::::::

## From Rules to Learning

In traditional programming, a human writes explicit rules and the computer follows them.

For example:

- A programmer writes rules to calculate tax.
- The computer applies those rules to a set of numbers.
- The output is fully determined by the instructions written in advance.

The logic flows like this:

**Rules + Data -> Answers**

Machine learning takes a different approach. Instead of writing detailed rules, we provide:

- Data
- The desired outputs (in many cases)
- The system then learns patterns that connect the two.

The logic becomes:

**Data + Answers -> Rules**

In other words, the computer infers the rules for itself.

A useful analogy is teaching a child to recognise cats. You would not provide a formal definition involving ear angles and whisker length. Instead, you would show many examples of cats and non-cats. Over time, the child internalises patterns that allow them to identify new cats correctly.

Machine learning systems operate in a similar way. They detect statistical patterns in examples and use those patterns to make predictions about new data.

## Three Types of Machine Learning

Machine learning is not one single method. It includes several different learning paradigms.

| Type | What the model has | What it learns to do | Example |
|------|---------------------|----------------------|---------|
| Supervised Learning | Labelled examples (input + correct answer) | Map inputs to correct outputs | Email spam detection, disease classification |
| Unsupervised Learning | Unlabelled data only | Find hidden patterns or groups | Customer segmentation, topic modelling of papers |
| Reinforcement Learning | Reward signals from environment | Maximise a reward through trial and error | Game-playing AI, robot control |

### Supervised learning

In supervised learning, each example includes both the input and the correct output.

For instance, a dataset of medical images might include thousands of scans labelled “tumour” or “no tumour”. The system learns to map image features to the correct diagnosis.

This is currently the most widely used type of machine learning in research and industry.

### Unsupervised learning

In unsupervised learning, the system is given data without explicit labels. Its task is to find structure within the data.

For example, given a large collection of research abstracts, an unsupervised model might group them into themes based on patterns of word usage. No one tells the system what the topics are in advance.

This approach is useful for exploration and discovery.

### Reinforcement learning

In reinforcement learning, an agent interacts with an environment and receives feedback in the form of rewards or penalties.

Over time, the system learns which actions maximise long-term reward. This approach has been used in game-playing systems and robotics.

## How a Model Learns

Let's walk through a simplified example of supervised learning:

1. Start with a dataset of examples. For example, 10,000 labelled medical images.
2. Split the data into two parts:

- A training set
- A test set

The training set is used to teach the model. The test set is kept separate and used only for evaluation.

This split matters because we want to know whether the model performs well on new, unseen data. If we test it on the same data it has already seen, we learn very little about its real-world usefulness.

3. During training, the model adjusts its internal parameters. You can think of these as thousands or millions of adjustable dials. The system tweaks these settings to reduce the number of mistakes it makes on the training data.
4. After training, we evaluate the model on the test set. This tells us how well it generalises beyond the examples it was shown during learning.

### Overfitting

A key risk in machine learning is overfitting.

Overfitting occurs when a model learns the training data too well, including its noise and quirks. Instead of learning general patterns, it effectively memorises the examples.

An analogy is a student who memorises past exam papers word for word. They may perform extremely well on familiar questions, but struggle when the questions are phrased differently.

A well-trained model should capture underlying structure, not just memorise details.

### Measuring Performance

Several metrics are used to evaluate model quality.

- **Accuracy** measures the proportion of correct predictions overall.
- **Precision** measures how many predicted positive cases were actually positive.
- **Recall** measures how many actual positive cases were correctly identified.

Different research contexts prioritise different metrics. In medical screening, for example, recall may be especially important to avoid missing true cases.

::::::::::::::::::::::::::::::::::::: callout

## Demonstration: Teachable Machine

A useful way to build intuition is to experiment with tools such as [Teachable Machine](https://teachablemachine.withgoogle.com/). These tools allow you to train a simple image or sound classifier using your own examples, without writing code.

The experience reinforces the core idea: the quality and quantity of training examples strongly influence the behaviour of the model.

::::::::::::::::::::::::::::::::::::::::::::::::


## What Can Go Wrong?

Machine learning systems are only as good as the data they are trained on.

A common phrase is “garbage in, garbage out”. If the training data is incomplete, biased, or unrepresentative, the resulting model will reflect those limitations.

Research-relevant examples include:

- A text analysis model trained only on English-language literature will struggle with multilingual texts.
- A medical diagnostic model trained predominantly on one demographic group may perform poorly for others.

These issues are not purely technical, they're ethically and societally important because they influence who benefits from AI systems and who may be disadvantaged by them. We will examine these ethical and societal questions in greater depth in Episode 5.

::::::::::::::::::::::::::::::::::::: challenge 

## Machine Learning in Research Scenarios

Match each scenario to supervised, unsupervised, or reinforcement learning:

1. A tool that groups research papers into topics automatically, without anyone labelling the topics in advance.
2. A system trained on thousands of labelled X-rays to flag potential tumours.
3. A robot that learns to navigate a maze by receiving a reward signal each time it gets closer to the exit.

:::::::::::::::::::::::: solution 

1 = Unsupervised learning
2 = Supervised learning
3 = Reinforcement learning

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::




::::::::::::::::::::::::::::::::::::: keypoints 

- Machine learning systems learn patterns from data rather than following only hand-written rules.
- Supervised learning uses labelled examples, unsupervised learning finds structure without labels, and reinforcement learning learns through rewards.
- Training and test sets help us assess whether a model generalises to new data.
- Overfitting occurs when a model memorises training data instead of learning general patterns.
- The quality and representativeness of training data strongly influence model performance and fairness.

::::::::::::::::::::::::::::::::::::::::::::::::



