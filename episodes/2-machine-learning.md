---
title: "Machine Learning - Teaching Computers from Data"
teaching: 20 # teaching time in minutes
exercises: 25 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- How is machine learning different from traditional programming?
- What are supervised, unsupervised, and reinforcement learning?
- What does it mean to train and test a model?
- What is overfitting, and why does it matter?
- When is machine learning the right choice and when is it not?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what machine learning is and how it differs from traditional programming.
- Distinguish between supervised, unsupervised, and reinforcement learning.
- Describe the concept of training, testing, and overfitting in plain language.
- Explain the difference between interpretable and black box models, and why it matters.
- Recognise when a traditional statistical approach may be more appropriate than machine learning.

::::::::::::::::::::::::::::::::::::::::::::::::

## From Rules to Learning

In traditional programming, a human writes explicit rules for some data,the computer follows them and provides some output.

For example, a researcher studying whether a scientific paper is relevant to a systematic review on arthritis interventions might write rules such as:

- If the paper mentions "randomised controlled trial" and the "arthritis", include it.
- If the paper is published before 1990, exclude it.

The computer applies those rules to some data, in this case, paper abstracts, and the output is fully determined by the rules written in advance.

The logic flows like this:

**Rules + Data -> Output**

This works reasonably well when the criteria are clear and consistent. However, in reality, relevance is rarely so clean. Papers use different terminology, describe similar interventions in different ways, and sometimes the abstract alone is not enough to judge. Writing rules that handle all of this becomes increasingly difficult and fragile.

Machine learning takes a different approach. Instead of writing detailed rules, we provide:

- **Data** - a large collection of abstracts
- The desired **outputs** for a subset of the data - human judgements about whether papers are relevant

The system then learns the patterns that connect the two.

The logic becomes:

**Data + Output -> Rules**

In other words, the computer infers the rules for itself.


### Machine Learning Analogy

A useful analogy is teaching a child to recognise dogs. You would not provide a formal definition involving ear angles and tail length. Instead, you would show many examples of dogs and non-dogs. Over time, the child internalises patterns that allow them to identify new dogs correctly.

Machine learning systems operate in a similar way. They detect statistical patterns in examples and use those patterns to make predictions about new data.

![](fig/dogs_cropped.jpg){alt="Three dogs standing on a mounting block in some woodland"}


## Three Types of Machine Learning

Machine learning is not one single method. It includes several different learning paradigms.

| Type | What the model has | What it learns to do | Example |
|------|---------------------|----------------------|---------|
| Supervised Learning | Labelled examples (input + correct answer) | Map inputs to correct outputs | Email spam detection, disease classification |
| Unsupervised Learning | Unlabelled data only | Find hidden patterns or groups | Customer segmentation, topic modelling of papers |
| Reinforcement Learning | Reward signals from environment | Maximise a reward through trial and error | Game-playing AI, robot control |

### Supervised learning

In supervised learning, each example includes both the input and the correct output.

For instance, a dataset of medical images might include thousands of scans labelled "tumour" or "no tumour". The system learns to map image features to the correct diagnosis.

This is currently the most widely used type of machine learning in research and industry.

### Unsupervised learning

In unsupervised learning, the system is given data without explicit labels. Its task is to find structure within the data.

For example, given a large collection of research paper abstracts, an unsupervised model might group them into themes based on patterns of word usage. No one tells the system what the topics are in advance.

This approach is useful for exploration and discovery.

### Reinforcement learning

In reinforcement learning, an agent interacts with an environment and receives feedback in the form of rewards or penalties.

Over time, the system learns which actions maximise long-term reward. This approach has been used in game-playing systems and robotics.

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

::::::::::::::::::::::::::::::::::::: callout

## What Kind of Task Is It?

Machine learning can be applied to several different types of tasks: regression, classification, clustering and dimensionality reduction.  Supervised learning is usually applied to regression and classification tasks, whereas unsupervised learning is often applied to clustering or dimensionality reduction tasks (although there are exceptions to both of these statements).

**Regression** — predicting a continuous numerical value. For example, predicting a patient's length of hospital stay based on clinical variables, or estimating the yield of a crop from environmental measurements. The output is a number on a continuous scale.

**Classification** — predicting which category an input belongs to. For example, classifying an email as spam or not spam, identifying the species of a plant from an image, or flagging whether a research paper is relevant to a systematic review. The output is a label chosen from a defined set.

**Clustering** — grouping unlabelled data into meaningful clusters based on similarity, without being told in advance what the groups are. For example, grouping survey respondents by response patterns, or identifying subtypes of a disease from patient data.

**Dimensionality reduction** - compressing high-dimensional data into a simpler representation for visualisation or further analysis.  For example, in gene expression research, scientists might compress thousands of gene measurements per patient down to two or three variables that capture the most meaningful variation, making it possible to plot all patients on a single chart and spot groupings that may correspond to clinically relevant subtypes.

When choosing the right machine learning algorithm for the job, often deciding which task is required is the first step.  For a guide, have a look at the [scikit-learn algorithm cheat sheet](https://scikit-learn.org/stable/machine_learning_map.html)

::::::::::::::::::::::::::::::::::::::::::::::::



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


::::::::::::::::::::::::::::::::::::: challenge

## Image Classification with the Teachable Machine

A useful way to build understanding without the need to write code is to experiment with tools such as [Teachable Machine](https://teachablemachine.withgoogle.com/) which allow you to train a simple image or sound classifier using your own examples, without any coding required.

*"Teachable Machine is a web-based tool that makes creating machine learning models fast, easy, and accessible to everyone. You train a computer to recognize your images, sounds, and poses without writing any machine learning code."*

Find two different objects and have a go training an image classifying machine learning model.

Notice how the quality and quantity of training examples strongly influence the behaviour of the model.

For more information about the Teachable Machine, have a look through the FAQs on their website: [https://teachablemachine.withgoogle.com/faq](https://teachablemachine.withgoogle.com/faq) 
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

## When Not to Use Machine Learning

Machine learning is a powerful set of tools, but it is not always the right one. Depending on the research question, traditional statistics may be better suited.

The main factor that should help you decide whether your goal is explanation or prediction:

- **Explanation** involves understanding the relationship between variables, testing hypotheses, and drawing causal or inferential conclusions e.g. *Does this treatment reduce recovery time?*
- **Prediction** involves building a system that produces accurate outputs for new cases e.g. *Can we flag likely hospital readmissions before they happen?*

Traditional statistical methods including regression models, t-tests, and ANOVA have been developed with explanation as their primary goal. They come with well-understood assumptions and and inferential frameworks, such as p-values and confidence intervals, that are widely understood in research communities. When your goal is to understand what is going on and why, these tools are often more appropriate than a machine learning model.

Machine learning, by contrast, is optimised for predictive performance. It works well when the dataset is large, the relationship between inputs and outputs is complex, the goal is prediction rather than inference, and formal hypothesis testing is not required.

Many research workflows combine a statistical model to test a hypothesis, and then a machine learning model to build a practical prediction tool. The important thing is to choose machine learning or traditional statistics deliberately, based on your research question.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


## How Can I Train My Own Machine Learning Model?

For many research tasks, training a machine learning model from scratch can be useful and within the realm of possibility. Researchers do this regularly, not because off-the-shelf tools are unavailable, but because a custom model trained on domain-specific data can outperform a general-purpose one, and because owning the model gives you full control over how it is evaluated, documented, and reported.

### What skills this requires

Training a conventional machine learning model requires **programming skills**, typically in Python or R, and familiarity with standard machine learning libraries such as scikit-learn (Python) or randomForest/xgboost/tidymodels (R).

A basic understanding of **data preparation** is essential as most of the practical work in machine learning involves cleaning, transforming, and structuring data rather than tuning models. 

An understanding of **statistics** is also valuable. Understanding what your evaluation metrics actually mean, and being able to reason about whether your model has learned something meaningful or has simply exploited a pattern in the training data, requires a degree of statstical understanding.

If you are new to programming or data science, many researchers begin with the Carpentries lessons on [Plotting and Programming in Python ](https://swcarpentry.github.io/python-novice-gapminder/) or [R for Reproducible Scientific Analysis](https://swcarpentry.github.io/r-novice-gapminder/), followed by  [Introduction to Machine Learning with Python](https://carpentries-incubator.github.io/machine-learning-novice-sklearn/) or [Machine Learning for Tabular Data in R](https://southampton-rsg-training.github.io/machine-learning-in-r/).

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### Working with a Research Software Engineer

If the machine learning component is central to your research, working with a Research Software Engineer (RSE) could be a helpful. RSEs can help you choose appropriate methods, implement them correctly and efficiently, and ensure your code is reliable, robust and well-documented. 

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- Machine learning systems learn patterns from data rather than following rules.
- Training and test sets help us assess whether a model generalises to new data.
- Interpretable models make their reasoning transparent whereas black box models do not.
- Traditional statistical methods are often more appropriate than machine learning when the goal is explanation rather than prediction, particularly with small datasets.
- The quality and representativeness of training data strongly influence model performance and fairness.

::::::::::::::::::::::::::::::::::::::::::::::::

## References

- [scikit-learn algorithm cheat sheet](https://scikit-learn.org/stable/machine_learning_map.html)
- [Van De Schoot, R., De Bruin, J., Schram, R., Zahedi, P., De Boer, J., Weijdema, F., ... & Oberski, D. L. (2021). An open source machine learning framework for efficient and transparent systematic reviews. Nature machine intelligence, 3(2), 125-133.](https://www.nature.com/articles/s42256-020-00287-7)
- [Teachable Machine](https://teachablemachine.withgoogle.com/)
- [geeksforgeeks Introduction to Machine Learning](https://www.geeksforgeeks.org/machine-learning/introduction-machine-learning/)
- [Overfitting in Machine Learning](https://www.freecodecamp.org/news/what-is-overfitting-machine-learning/)

