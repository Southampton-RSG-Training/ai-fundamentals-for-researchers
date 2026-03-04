---
title: "Machine Learning - Teaching Computers from Data"
teaching: 20 # teaching time in minutes
exercises: 5 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- How is machine learning different from traditional programming?
- What are supervised, unsupervised, and reinforcement learning?
- What does it mean to train and test a model?
- What is overfitting, and why does it matter?
- When is machine learning the right choice — and when is it not?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what machine learning is and how it differs from traditional programming.
- Distinguish between supervised, unsupervised, and reinforcement learning.
- Identify the main types of ML task: regression, classification, and clustering.
- Describe the concept of training, testing, and overfitting in plain language.
- Explain the difference between interpretable and black box models, and why it matters.
- Recognise when a traditional statistical approach may be more appropriate than machine learning.

::::::::::::::::::::::::::::::::::::::::::::::::

## From Rules to Learning

In traditional programming, a human writes explicit rules and the computer follows them.

For example:

- A programmer writes **rules** to calculate tax.
- The computer applies those rules to some **data**.
- The output is fully determined by the rules written in advance.

The logic flows like this:

**Rules + Data -> Output**

Machine learning takes a different approach. Instead of writing detailed rules, we provide:

- **Data**
- The desired **outputs** 
- The system then learns rules or patterns that connect the two.

The logic becomes:

**Data + Output -> Rules**

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

## What Kind of Task Is It?

Machine learning can be applied to several different types of tasks: regression, classification, clustering and dimensionality reduction.  Supervised learning is usually applied to regression and classification tasks, whereas unsupervised learning is often applied to clustering or dimensionality reduction tasks (although there are exceptions to both of these statements).

**Regression** — predicting a continuous numerical value. For example, predicting a patient's length of hospital stay based on clinical variables, or estimating the yield of a crop from environmental measurements. The output is a number on a continuous scale.

**Classification** — predicting which category an input belongs to. For example, classifying an email as spam or not spam, identifying the species of a plant from an image, or flagging whether a research paper is relevant to a systematic review. The output is a label chosen from a defined set.

**Clustering** — grouping unlabelled data into meaningful clusters based on similarity, without being told in advance what the groups are. For example, grouping survey respondents by response patterns, or identifying subtypes of a disease from patient data.

**Dimensionality reduction** - compressing high-dimensional data into a simpler representation for visualisation or further analysis.  For example, in gene expression research, scientists might compress thousands of gene measurements per patient down to two or three variables that capture the most meaningful variation, making it possible to plot all patients on a single chart and spot groupings that may correspond to clinically relevant subtypes.


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

A useful way to build understanding without the need to write code is to experiment with tools such as [Teachable Machine](https://teachablemachine.withgoogle.com/). These tools allow you to train a simple image or sound classifier using your own examples, without any coding required.

Notice how the quality and quantity of training examples strongly influence the behaviour of the model.

::::::::::::::::::::::::::::::::::::::::::::::::

## Interpretable Models vs Black Box Models

Before choosing a machine learning approach, one of the most important questions to ask is:

> *"Do I need to understand why the model makes a particular prediction, or is the prediction itself sufficient?"*

This is the distinction between **interpretable** and **black box** models.

An **interpretable model** produces outputs that can be traced back to a clear, human-readable explanation. A linear regression, for instance, gives you a coefficient for each input variable and you can see directly how much each factor contributed to the prediction. A decision tree reaches its conclusion through a series of simple yes/no rules that can be printed out and inspected. When accountability, transparency, or regulatory compliance matter, interpretability may be essential.

A **black box model**, such as a deep neural network with many layers, may produce highly accurate predictions, but the internal reasoning process is not directly accessible. You can observe the inputs and outputs, but the path between them involves thousands or millions of interacting numerical parameters that do not correspond to human-understandable concepts. 

Consider an interpretable model when:

- You need to explain or justify individual predictions
- Your field has regulatory or ethical requirements for transparency
- Discovering which variables matter is part of the research question
- Stakeholders (e.g. patients, policymakers, or funders) need to understand the rationale

A black box model may be acceptable when:

- Predictive accuracy is the primary goal
- Outputs will be validated independently before acting on them
- Large volumes of complex data (images, audio) make interpretability impractical


## When Not to Use Machine Learning

Machine learning is a powerful set of tools, but it is not always the right one. Depending on the research question, traditional statistics may be better suited.

The main factor that should help you decide whether your goal is explanation or prediction:

- **Explanation** involves understanding the relationship between variables, testing hypotheses, and drawing causal or inferential conclusions e.g. *Does this treatment reduce recovery time?*
- **Prediction** involves building a system that produces accurate outputs for new cases e.g. *Can we flag likely hospital readmissions before they happen?*

Traditional statistical methods including regression models, t-tests, and ANOVA have been developed with explanation as their primary goal. They come with well-understood assumptions and and inferential frameworks, such as p-values and confidence intervals, that are widely understood in research communities. When your goal is to understand what is going on and why, these tools are often more appropriate than a machine learning model.

Machine learning, by contrast, is optimised for predictive performance. It works well when the dataset is large, the relationship between inputs and outputs is complex, the goal is prediction rather than inference, and formal hypothesis testing is not required.

Many research workflows combine a statistical model to test a hypothesis, and then a machine learning model to build a practical prediction tool. The important thing is to choose machine learning or traditional statistics deliberately, based on your research question.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

## Signs that a traditional statistical approach may be more appropriate

- Your primary goal is to test a specific hypothesis.
- Your dataset is small (many ML methods need substantial amounts of data to generalise reliably).
- You need to quantify uncertainty formally, with confidence intervals or p-values.
- Assumptions are well-understood and can be checked (e.g. normality, independence).
- Interpretability is essential and a simpler statistical model performs adequately.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


## What Can Go Wrong?

Machine learning systems are only as good as the data they are trained on.

A common phrase is "garbage in, garbage out". If the training data is incomplete, biased, or unrepresentative, the resulting model will reflect those limitations.

Research-relevant examples include:

- A text analysis model trained only on English-language literature will struggle with multilingual texts.
- A medical diagnostic model trained predominantly on one demographic group may perform poorly for others.

These issues are not purely technical, they're ethically and societally important because they influence who benefits from AI systems and who may be disadvantaged by them. We will examine these ethical and societal questions in greater depth in [Episode 5](05-ai-in-research.md).


::::::::::::::::::::::::::::::::::::: challenge

## Choosing the Right Approach

For each research scenario below, decide whether you would lean towards a traditional statistical method, a machine learning model, or a combination of both — and briefly explain why.

1. A clinical researcher wants to know whether a new drug significantly reduces blood pressure compared to a placebo, using data from a randomised controlled trial of 120 participants.
2. A team wants to build a tool that automatically flags grant applications likely to score in the top 10%, trained on 50,000 previously scored applications.
3. An ecologist wants to understand which environmental variables most strongly predict the presence of a rare species, and needs to report effect sizes to inform conservation policy.

:::::::::::::::::::::::: solution

1. **Traditional statistics.** The goal is hypothesis testing and effect estimation in a small, well-controlled dataset. A t-test or regression model is appropriate, interpretable, and produces the confidence intervals and p-values the clinical audience expects.

2. **Machine learning.** The goal is prediction, the dataset is large, and accuracy on unseen applications is the primary criterion. Interpretability may still matter (to avoid bias in funding decisions), so the choice of model and evaluation for fairness would both warrant careful thought.

3. **Traditional statistics, possibly combined with ML.** The goal is explanation and communication of effect sizes to a policy audience. A regression-based approach is likely more appropriate. If the dataset is large and the relationships complex, a machine learning model might improve predictive accuracy, but the interpretability requirement points toward simpler, explainable methods.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- Machine learning systems learn patterns from data rather than following only hand-written rules.
- Supervised learning uses labelled examples, unsupervised learning finds structure without labels, and reinforcement learning learns through rewards.
- The main task types are regression (predicting a continuous value), classification (predicting a category), and clustering (grouping unlabelled data).
- Training and test sets help us assess whether a model generalises to new data.
- Overfitting occurs when a model memorises training data instead of learning general patterns.
- Interpretable models make their reasoning transparent; black box models do not — the right choice depends on whether explanation or prediction is the primary goal.
- Traditional statistical methods are often more appropriate than machine learning when the goal is hypothesis testing, effect estimation, or causal inference, particularly with small datasets.
- The quality and representativeness of training data strongly influence model performance and fairness.

::::::::::::::::::::::::::::::::::::::::::::::::
