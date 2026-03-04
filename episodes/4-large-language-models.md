---
title: "Large Language Models"
teaching: 25 # teaching time in minutes
exercises: 5 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is a large language model and how does it relate to deep learning?
- How are LLMs trained, and what does "large" actually mean?
- Why do LLMs sometimes produce confident but incorrect information?
- What are the key limitations I should understand before using an LLM in my research?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what an LLM is and where it sits within the broader AI landscape.
- Describe the Transformer architecture and the attention mechanism.
- Distinguish between pre-training and fine-tuning.
- Define hallucination, knowledge cutoff, and context window, and explain why they matter for research use.

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

Over the previous two episodes we have built up a picture of how machines can learn from data, and how deep neural networks can learn rich, layered representations of the world. In this episode we apply those ideas to language. We will explore **Large Language Models (LLMs)**, the technology behind tools such as ChatGPT, Claude, Gemini, and Copilot, to understand what they are, how they are built, and what their real limitations are.

By the end of this episode you will be in a much stronger position to use these tools critically and responsibly in your own research

## What is a Large Language Model?

A Large Language Model is a type of deep learning model trained on vast quantities of text, with the goal of learning how language works so that it can generate and respond to text in a coherent, useful way.

The word **"large"** refers to two things at once:

- **The training data:** modern LLMs are trained on trillions of words drawn from books, websites, academic papers, code repositories, and more.
- **The number of parameters:** parameters are the adjustable weights inside the network that are learned during training. Leading models have hundreds of billions, or even trillions, of these values.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### Putting "large" in perspective

One trillion is 1,000,000,000,000. To give a sense of scale: if you counted one parameter per second without stopping, counting to one trillion would take over 31,000 years.
The sheer number of parameters is what allows these models to store and manipulate rich, nuanced representations of language.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

Despite their apparent sophistication, LLMs are trained on a surprisingly simple objective: **given a sequence of words, predict what word is most likely to come next**.

Consider the sentence:

*The researcher submitted her manuscript to the ___*

A well-trained model should assign a high probability to words like *journal* or *publisher*, and a low probability to words like *submarine* or *Tuesday*. By doing this billions of times across an enormous training corpus, the model is forced to learn grammar, facts, writing conventions, and even something resembling reasoning because all of these are encoded in the statistical patterns of language.

This is sometimes called **self-supervised learning**: the training data provides its own labels (the next word is always known from the text itself), so no human annotation is required.


## Transformer Architecture

LLMs are built on an architecture called the **Transformer**, introduced in a landmark 2017 paper titled "Attention Is All You Need" (cited over 234,000 times as of Spring 2026). Before the Transformer, models processed text one word at a time, which was slow and made it hard to capture relationships between words that were far apart in a sentence. The Transformer solved both problems.

### The attention mechanism

The key innovation of the Transformer is the **attention mechanism**. Rather than processing words in isolation, attention allows the model to look at all the words in a passage simultaneously and learn which ones are most relevant to understanding each particular word.

Consider this sentence:

*The bank was steep and muddy, so she slipped climbing down it.*

When processing the word *bank*, a human reader immediately uses context clues such as *steep*, *muddy*, and *climbing*, to understand that this is a riverbank, not a financial institution. The attention mechanism allows a Transformer to do something similar: it learns to assign higher attention weights to the words most relevant for correctly interpreting each part of the text.


The attention mechanism combined with the availability of large-scale computing hardware, triggered a step up in what language models could do. Essentially all major LLMs today including ChatGPT, Claude, and Gemini are built on the Transformer architecture.

## How LLMs Are Trained: Pre-training and Fine-tuning

Building a capable LLM is typically a two-stage process.

### Stage 1: Pre-training

In the pre-training stage, the model is trained from scratch on an enormous, general-purpose body of text. The training objective is to predict the next word. The model adjusts its billions of parameters through backpropagation (the backward flow of error through a neural network, see [Episode 3](3-deep-learning.md)) until it becomes very good at predicting text across a huge range of topics and styles.

Pre-training is extremely  resource-intensive. Training a leading LLM can:

- Require thousands of specialised computer chips running in parallel for weeks or months.
- Consume millions of pounds' worth of electricity and hardware time.
- Produce a significant carbon footprint.  [One study](https://www.technologyreview.com/2019/06/06/239031/training-a-single-ai-model-can-emit-as-much-carbon-as-five-cars-in-their-lifetimes/#:~:text=A%20paper%20from%20the%20University%20of%20Massachusetts%2C,on%20teaching%20machines%20to%20handle%20human%20language.) found that training a single large transformer model can emit over 283,000 kg of carbon 

This cost means that pre-trained models are rarely trained from scratch by individual researchers or institutions. Instead, organisations release **pre-trained base models** that others can build on.

### Stage 2: Fine-tuning

Once a base model exists, it can be **fine-tuned**. This means it can be trained further on a smaller, more targeted dataset to adapt its behaviour for a specific purpose or domain. For example, a base model might be fine-tuned...

- on medical literature to improve its performance on clinical questions.
- on legal documents to better support contract analysis.
- using human feedback to make it more helpful, harmless, and honest in conversation.

That last approach, of using human ratings to guide the model toward more desirable outputs, is called **Reinforcement Learning from Human Feedback (RLHF)**. It is largely responsible for the conversational, 'helpful assistant' style of tools like ChatGPT. Human raters score model outputs, and the model is trained to produce outputs that score more highly.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

## Pre-training and Fine-tuning Analogy

Think of pre-training as an undergraduate education: the student reads broadly across many subjects and develops general knowledge and reasoning skills. Fine-tuning is then like a postgraduate specialisation: the student goes deep into a specific field, building on their broad foundation.

A model trained this way inherits both the strengths and the limitations of its pre-training. If the pre-training data contained biased, outdated, or incorrect material, those properties will be present in the base model and may persist even after fine-tuning.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

## What LLMs Can Do

LLMs have demonstrated some amazing capabilities across a wide range of language tasks, including:

- **Text generation and summarisation** — producing coherent text, summarising long documents, drafting emails.
- **Question answering** — responding to factual queries based on patterns in training data.
- **Translation** — converting text between languages.
- **Code generation** — writing, explaining, and debugging computer code.
- **Step-by-step reasoning** — working through multi-step problems when prompted appropriately.
- **Information extraction** — identifying entities, relationships, or themes in text.

For researchers, LLMs offer potential value in tasks such as summarising literature, drafting sections of text for revision, assisting with qualitative coding, generating data analysis computer code, and exploring ideas interactively.

## What LLMs Cannot Do: Key Limitations

Understanding what LLMs *cannot* reliably do is at least as important as knowing what they can do, especially for research applications where accuracy and reproducibility matter.

### Hallucination

Perhaps the most important limitation to understand is **hallucination**: LLMs often generate confident, fluent, plausible-sounding text that is factually incorrect.

This is not an occasional bug that will eventually be fixed, it is a fundamental property of how these models work. An LLM is optimised to produce coherent, contextually appropriate text but it is not optimised to produce truth. It has no direct access to a database of facts it can look up. Instead, it generates text by predicting what is most likely to come next, based on patterns learned during training.

In practice this means an LLM might:

- Invent citations to academic papers that do not exist, complete with plausible-sounding titles, authors, and journal names.
- State incorrect dates, statistics, or quotations with complete confidence.
- Describe the findings of a study inaccurately, even when the study is real.

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### Why is it called 'hallucination'?

The term is borrowed from psychology, where hallucination refers to perceiving something that is not actually there. When an LLM "hallucinates", it generates content that feels real and is presented confidently, but has no basis in fact. The model has no way to flag its own uncertainty in the way a cautious human expert might say "I'm not certain, but I believe...". That's why it's important to verify factual claims from LLMs using primary sources.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

### Knowledge Cutoff

LLMs are trained on data collected up to a specific point in time, this is known as their **knowledge cutoff** date. They have no awareness of events, publications, or developments that occurred after that date, unless they are connected to external tools such as a web search capability.

This matters particularly for research, where the most recent literature may be the most relevant. An LLM asked about the current state of a fast-moving field may give a confident account that is months or years out of date.


### Stochasticity: Different Answers Each Time

LLM outputs are **probabilistic** rather than deterministic. Even when given exactly the same input, an LLM will often produce a different output on subsequent runs. This has implications for reproducibility in research: if you use an LLM in your methodology, you cannot guarantee that re-running your analysis will produce identical results.


### Context Window

Every LLM has a **context window**, which is the maximum amount of text it can "see" and process at one time. You can think of it as the model's working memory for a single interaction. If you provide a document that exceeds the context window, the model may be forced to ignore parts of it, potentially affecting the quality of its output.

Context window sizes vary widely across models and have grown considerably in recent years, but they remain a practical constraint when working with very long documents.


### No Genuine Understanding

Finally, it is important to resist the temptation to interpret LLM fluency as understanding. An LLM produces text by sophisticated pattern matching and it does not have beliefs, intentions, or knowledge in the way a human expert does. A model that can write a convincing paragraph about quantum mechanics has not 'understood' quantum mechanics, it has just learned what such paragraphs tend to look like.



:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### Summary of key LLM limitations

| Limitation | What it means in practice |
|---|---|
| Hallucination | Outputs may be confidently wrong; always verify factual claims |
| Knowledge cutoff | The model is unaware of events after its training data ends |
| Stochasticity | The same question can produce different answers |
| Context window | Very long documents may be partially ignored |
| No verified understanding | Fluency does not equal accuracy or expertise |

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::::::: challenge

### Challenge: True or False?

For each statement below, decide whether it is true or false, and briefly explain your reasoning.

1. When an LLM answers a question, it searches the internet and retrieves the most relevant facts.
2. A fine-tuned LLM trained on medical literature will always give accurate medical information.
3. Two researchers using the same LLM with the same prompt will always receive identical outputs.
4. LLMs learn from their conversations with users, updating their knowledge in real time.

::::::::::::::::::::: solution

### Solution

1. **False.** A standard LLM generates responses based on patterns learned during training — it does not retrieve information from a live database or the internet. Some LLMs are connected to web search tools, but this is an added capability, not a core feature of how the model works.

2. **False.** Fine-tuning on domain-specific text can improve performance in a given area, but it does not eliminate hallucination. A model can still produce confident but incorrect medical information. Domain expertise does not guarantee accuracy.

3. **False.** LLM outputs are probabilistic. The same input can produce different outputs across different sessions, or even within the same session, because the model samples from a distribution of possible next words rather than selecting a single deterministic answer.

4. **False** (for most deployed LLMs). Once trained and deployed, an LLM's parameters are fixed — it does not learn from or retain information from individual conversations. Each session typically starts fresh from the same model state. (Some specialised systems are designed to update over time, but this is not the default.)

:::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: challenge 

## Testing the Limitations of LLMs

Go to a conversational AI tool such as ChatGPT, Microsoft Copilot or Claude and ask the following questions:

1. Ask the model to provide three references on a niche academic topic. Note any invented or inaccurate citations.
2. Ask the same question twice and compare outputs.
3. Ask about a very recent event, publication, or development in your field. Observe how the model responds — it may admit uncertainty, speculate, give outdated information, or turn to web search capabilities.
4. Ask the model to summarise a short paragraph you provide.

:::::::::::::::::::::::: solution 

1. Hallucination demo
2. Stochasticity demo
3. Knowledge cutoff demo
4. This illustrates a task where LLMs genuinely add value when the output is reviewed critically.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

## Summary

In this episode we have seen how the simple task of predicting the next word can lead to the powerful, general-purpose language tools that are reshaping how people interact with information today. 

In [Episode 5](5-ai-in-research.md), we will bring together everything from the course to explore how AI tools, including LLMs, are being used in research today, and how to evaluate them critically and ethically.

::::::::::::::::::::::::::::::::::::: keypoints 

- LLMs are deep learning models trained on massive text datasets to predict the next word, from which broad language capabilities emerge.
- The Transformer architecture, and its attention mechanism, is the foundation of all major modern LLMs.
- Pre-training builds general language knowledge; fine-tuning specialises a model for particular tasks or behaviours.
- LLMs hallucinate — they generate confident but factually incorrect content — because they are optimised for coherent text, not verified truth.
- LLMs have a knowledge cutoff date and are unaware of more recent events unless equipped with external search tools.
- Outputs are probabilistic: the same prompt can produce different responses, with implications for research reproducibility.

::::::::::::::::::::::::::::::::::::::::::::::::

## References

- [Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., ... & Polosukhin, I. (2017). Attention is all you need. Advances in neural information processing systems, 30.](https://proceedings.neurips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)


::::::::::::::::::::::::::::::::::::: callout
## Glossary

**Attention mechanism**
The core innovation of the Transformer architecture. Rather than processing words one at a time, the attention mechanism allows a model to consider all words in a passage simultaneously and learn which ones are most relevant to interpreting each particular word. It is what allows LLMs to handle long, complex text without losing track of meaning established earlier in a passage.

**Context window**
The maximum amount of text an LLM can process in a single interaction i.e. its working memory for a conversation or task. Text that exceeds the context window may be silently ignored, which can affect the quality of outputs when working with long documents. Context window sizes are typically measured in **tokens** rather than words.

**Fine-tuning**
The process of taking a pre-trained base model and training it further on a smaller, task-specific dataset to adapt its behaviour for a particular domain or purpose. Fine-tuning is far less resource-intensive than pre-training and is the most common way that general-purpose LLMs are adapted for specialised research or industry applications.

**Foundation model**
A large model trained on broad data at scale that can be adapted for a wide range of downstream tasks. LLMs such as GPT-4 and Claude are foundation models. The term emphasises that these models serve as a foundation on which more specialised systems are built, typically through fine-tuning or prompting.

**Grounding**
The process of connecting an LLM's outputs to verifiable external information, such as a specific document, database, or knowledge base. Grounding reduces the risk of hallucination by anchoring the model's responses to a defined source. Retrieval-Augmented Generation (RAG) is one common approach to grounding.

**Hallucination**
The generation of text that is fluent and confident-sounding but factually incorrect or entirely fabricated. Hallucination is a fundamental property of how LLMs work and cannot currently be eliminated entirely. Common examples include invented academic citations, incorrect statistics, and inaccurate descriptions of real events or studies.

**Inference**
The process of running a trained model to generate a response to a new input. Inference is what happens every time a user submits a prompt to an LLM. In contrast to training, which is a one-time or infrequent event, inference happens continuously at scale and ultimately accounts for the majority of an LLM's cumulative energy consumption.

**Knowledge cutoff**
The date up to which an LLM's training data was collected. The model has no direct awareness of events, publications, or developments that occurred after this date. Some LLMs are connected to web search tools that partially compensate for this limitation, but the base model's knowledge remains fixed at the cutoff.

**Large Language Model (LLM)**
A type of deep learning model built on the Transformer architecture and trained on very large quantities of text to predict the next word in a sequence. Through this training process, LLMs develop broad capabilities in language generation, question answering, summarisation, translation, and reasoning. Examples include GPT-4, Claude, Gemini, and LLaMA.

**Model card**
A standardised document published alongside an AI model that describes how it was trained, what data it was trained on, what it was evaluated on, and its known limitations and failure modes. Model cards are the primary resource for critically evaluating whether a model is appropriate for a given research use case.

**Multiagent system**
A system in which multiple AI models (or multiple instances of the same model) work together to complete a task, each taking on a defined role. For example, one agent might search for information, a second might summarise it, and a third might check the result for errors. Multiagent systems can tackle more complex, multi-step tasks than a single model working alone, but they can also compound errors if one agent's hallucinated output is passed unchecked to the next.

**Parameter**
An adjustable numerical weight inside a neural network that is learned during training. Parameters are the internal settings that encode everything the model has learned. LLMs are described as "large" partly because they contain hundreds of billions or even trillions of parameters.

**Pre-training**
The initial, large-scale training of an LLM from scratch on a broad general-purpose text corpus. Pre-training is the most computationally expensive stage of building an LLM and produces a **base model** with general language knowledge that can subsequently be fine-tuned for specific applications.

**Prompt**
The input text provided to an LLM to elicit a response. A prompt might be a question, an instruction, a partially completed passage, or a combination of background context and a specific request. The design and wording of a prompt can substantially affect the quality and nature of the model's output.

**Prompt engineering**
The practice of deliberately designing and refining prompts to elicit better, more reliable, or more appropriately structured outputs from an LLM. Effective prompt engineering techniques include providing clear instructions, supplying relevant context, specifying the desired format of the response, and using examples to demonstrate the expected output style. While it requires no knowledge of the model's internal workings, it can significantly improve the usefulness and consistency of LLM outputs in research workflows.

**Retrieval-Augmented Generation (RAG)**
An approach that combines an LLM with a separate retrieval system, typically a database or document store. When a query is submitted, relevant passages are first retrieved from the external source and then provided to the LLM as context alongside the original query. This allows the model to generate responses grounded in specific, up-to-date, or domain-specific documents, reducing hallucination and overcoming the knowledge cutoff limitation without the expense of fine-tuning the model itself.

**Reinforcement Learning from Human Feedback (RLHF)**
A training technique used to align LLM outputs with human preferences. Human raters score model-generated responses, and the model is trained to produce outputs that receive higher ratings. RLHF is responsible for the conversational, "helpful assistant" behaviour of deployed tools such as ChatGPT, and is distinct from both pre-training and fine-tuning in that it optimises for human approval rather than next-word prediction accuracy.

**Self-supervised learning**
A form of machine learning in which the training labels are derived from the data itself, without any human annotation. LLM pre-training is self-supervised: the correct next word is always present in the original text, so no labelling effort is required. This property makes it possible to train on the enormous volumes of text needed to build capable LLMs.

**System prompt**
A set of instructions provided to an LLM before a conversation begins, typically by the developer or organisation deploying the tool rather than the end user. System prompts define the model's persona, set behavioural constraints, and establish the context in which the model is operating. Users often cannot see the system prompt, but it shapes every response the model gives.

**Temperature**
A parameter that controls how predictable or varied an LLM's outputs are. A low temperature makes the model more deterministic, consistently choosing the most probable next word. A higher temperature introduces more randomness, producing more varied and sometimes more creative outputs but also increasing the risk of incoherence or hallucination. Temperature is one reason why the same prompt can produce different outputs on different runs.

**Token**
The basic unit of text that an LLM processes, which may be a word, part of a word, or a punctuation mark. Context window sizes and API costs are typically expressed in tokens rather than words. As a rough guide, 100 tokens is approximately 75 words in English.

**Transformer**
The neural network architecture that underpins all major modern LLMs, introduced in the 2017 paper "Attention Is All You Need". The defining feature of the Transformer is the attention mechanism, which allows it to process all parts of an input simultaneously and model relationships between distant words. Its ability to be trained efficiently on large datasets using parallel computing hardware made the current generation of LLMs possible.

::::::::::::::::::::::::::::::::::::::::::::::::
