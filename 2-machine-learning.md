---
title: "Machine Learning - Teaching Computers from Data"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 



::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what machine learning is and how it differs from traditional programming.
- Distinguish between supervised, unsupervised, and reinforcement learning.
- Describe the concept of training, testing, and overfitting in plain language.
- Give a domain-relevant example of a machine learning application.

::::::::::::::::::::::::::::::::::::::::::::::::

## From Rules to Learning

- Traditional programming: humans write rules → computer applies them to data.
- Machine learning: humans provide data + desired outcomes → computer finds the rules.
- Analogy: teaching a child to identify cats by showing them many pictures rather than writing a dictionary definition.

## Three Types of Machine Learning

| Type | What the model has | What it learns to do | Example |
|------|---------------------|----------------------|---------|
| Supervised Learning | Labelled examples (input + correct answer) | Map inputs to correct outputs | Email spam detection, disease classification |
| Unsupervised Learning | Unlabelled data only | Find hidden patterns or groups | Customer segmentation, topic modelling of papers |
| Reinforcement Learning | Reward signals from environment | Maximise a reward through trial and error | Game-playing AI, robot control |

## How a Model Learns

Conceptual walkthrough of supervised learning:
1. Start with a dataset of examples (e.g. 10,000 labelled medical images).
2. Split into *training set* and *test set* - why the split matters
3. The model adjusts its internal settings (parameters) to reduce errors on training data.
4. Evaluate on the *test set* to see how well it generalises.

- Introduce *overfitting* with an intuitive analogy: memorising past exam papers versus truly understanding the material.
- Briefly introduce the idea of *accuracy*, *precision*, and *recall* as measures of model quality

- [Teachable Machine](https://teachablemachine.withgoogle.com/) demonstration

## What Can Go Wrong?

- Garbage in, garbage out: biased or incomplete training data leads to biased models.
- Brief examples relevant to research: text analysis trained only on English literature; medical models trained only on one demographic.
- This is a preview — ethical issues are explored in depth in Episode 5.
  
  

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Machine Learning in Research Scenarios

Match each scenario to supervised, unsupervised, or reinforcement learning:

1. A tool that groups research papers into topics automatically, without anyone labelling the topics in advance.
2. A system trained on thousands of labelled X-rays to flag potential tumours.
3. A robot that learns to navigate a maze by receiving a reward signal each time it gets closer to the exit.

:::::::::::::::::::::::: solution 

(Answers: 1 = Unsupervised, 2 = Supervised, 3 = Reinforcement)

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::: callout



::::::::::::::::::::::::::::::::::::::::::::::::






::::::::::::::::::::::::::::::::::::: keypoints 



::::::::::::::::::::::::::::::::::::::::::::::::



