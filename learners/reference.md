---
title: 'Reference'
---

## Glossary


**Attention mechanism**:
The core innovation of the Transformer architecture. Rather than processing words one at a time, the attention mechanism allows a model to consider all words in a passage simultaneously and learn which ones are most relevant to interpreting each particular word. It is what allows LLMs to handle long, complex text without losing track of meaning established earlier in a passage.

**Context window**:
The maximum amount of text an LLM can process in a single interaction i.e. its working memory for a conversation or task. Text that exceeds the context window may be silently ignored, which can affect the quality of outputs when working with long documents. Context window sizes are typically measured in **tokens** rather than words.

**Fine-tuning**:
The process of taking a pre-trained base model and training it further on a smaller, task-specific dataset to adapt its behaviour for a particular domain or purpose. Fine-tuning is far less resource-intensive than pre-training and is the most common way that general-purpose LLMs are adapted for specialised research or industry applications.

**Foundation model**:
A large model trained on broad data at scale that can be adapted for a wide range of downstream tasks. LLMs such as GPT-4 and Claude are foundation models. The term emphasises that these models serve as a foundation on which more specialised systems are built, typically through fine-tuning or prompting.

**Grounding**:
The process of connecting an LLM's outputs to verifiable external information, such as a specific document, database, or knowledge base. Grounding reduces the risk of hallucination by anchoring the model's responses to a defined source. Retrieval-Augmented Generation (RAG) is one common approach to grounding.

**Hallucination**:
The generation of text that is fluent and confident-sounding but factually incorrect or entirely fabricated. Hallucination is a fundamental property of how LLMs work and cannot currently be eliminated entirely. Common examples include invented academic citations, incorrect statistics, and inaccurate descriptions of real events or studies.

**Inference**:
The process of running a trained model to generate a response to a new input. Inference is what happens every time a user submits a prompt to an LLM. In contrast to training, which is a one-time or infrequent event, inference happens continuously at scale and ultimately accounts for the majority of an LLM's cumulative energy consumption.

**Knowledge cutoff**:
The date up to which an LLM's training data was collected. The model has no direct awareness of events, publications, or developments that occurred after this date. Some LLMs are connected to web search tools that partially compensate for this limitation, but the base model's knowledge remains fixed at the cutoff.

**Large Language Model (LLM)**:
A type of deep learning model built on the Transformer architecture and trained on very large quantities of text to predict the next word in a sequence. Through this training process, LLMs develop broad capabilities in language generation, question answering, summarisation, translation, and reasoning. Examples include GPT-4, Claude, Gemini, and LLaMA.

**Model card**:
A standardised document published alongside an AI model that describes how it was trained, what data it was trained on, what it was evaluated on, and its known limitations and failure modes. Model cards are the primary resource for critically evaluating whether a model is appropriate for a given research use case.

**Multiagent system**:
A system in which multiple AI models (or multiple instances of the same model) work together to complete a task, each taking on a defined role. For example, one agent might search for information, a second might summarise it, and a third might check the result for errors. Multiagent systems can tackle more complex, multi-step tasks than a single model working alone, but they can also compound errors if one agent's hallucinated output is passed unchecked to the next.

**Parameter**:
An adjustable numerical weight inside a neural network that is learned during training. Parameters are the internal settings that encode everything the model has learned. LLMs are described as "large" partly because they contain hundreds of billions or even trillions of parameters.

**Pre-training**:
The initial, large-scale training of an LLM from scratch on a broad general-purpose text corpus. Pre-training is the most computationally expensive stage of building an LLM and produces a **base model** with general language knowledge that can subsequently be fine-tuned for specific applications.

**Prompt**:
The input text provided to an LLM to elicit a response. A prompt might be a question, an instruction, a partially completed passage, or a combination of background context and a specific request. The design and wording of a prompt can substantially affect the quality and nature of the model's output.

**Prompt engineering**:
The practice of deliberately designing and refining prompts to elicit better, more reliable, or more appropriately structured outputs from an LLM. Effective prompt engineering techniques include providing clear instructions, supplying relevant context, specifying the desired format of the response, and using examples to demonstrate the expected output style. While it requires no knowledge of the model's internal workings, it can significantly improve the usefulness and consistency of LLM outputs in research workflows.

**Retrieval-Augmented Generation (RAG)**:
An approach that combines an LLM with a separate retrieval system, typically a database or document store. When a query is submitted, relevant passages are first retrieved from the external source and then provided to the LLM as context alongside the original query. This allows the model to generate responses grounded in specific, up-to-date, or domain-specific documents, reducing hallucination and overcoming the knowledge cutoff limitation without the expense of fine-tuning the model itself.

**Reinforcement Learning from Human Feedback (RLHF)**:
A training technique used to align LLM outputs with human preferences. Human raters score model-generated responses, and the model is trained to produce outputs that receive higher ratings. RLHF is responsible for the conversational, "helpful assistant" behaviour of deployed tools such as ChatGPT, and is distinct from both pre-training and fine-tuning in that it optimises for human approval rather than next-word prediction accuracy.

**Self-supervised learning**:
A form of machine learning in which the training labels are derived from the data itself, without any human annotation. LLM pre-training is self-supervised: the correct next word is always present in the original text, so no labelling effort is required. This property makes it possible to train on the enormous volumes of text needed to build capable LLMs.

**System prompt**:
A set of instructions provided to an LLM before a conversation begins, typically by the developer or organisation deploying the tool rather than the end user. System prompts define the model's persona, set behavioural constraints, and establish the context in which the model is operating. Users often cannot see the system prompt, but it shapes every response the model gives.

**Temperature**:
A parameter that controls how predictable or varied an LLM's outputs are. A low temperature makes the model more deterministic, consistently choosing the most probable next word. A higher temperature introduces more randomness, producing more varied and sometimes more creative outputs but also increasing the risk of incoherence or hallucination. Temperature is one reason why the same prompt can produce different outputs on different runs.

**Token**:
The basic unit of text that an LLM processes, which may be a word, part of a word, or a punctuation mark. Context window sizes and API costs are typically expressed in tokens rather than words. As a rough guide, 100 tokens is approximately 75 words in English.

**Transformer**:
The neural network architecture that underpins all major modern LLMs, introduced in the 2017 paper "Attention Is All You Need". The defining feature of the Transformer is the attention mechanism, which allows it to process all parts of an input simultaneously and model relationships between distant words. Its ability to be trained efficiently on large datasets using parallel computing hardware made the current generation of LLMs possible.



