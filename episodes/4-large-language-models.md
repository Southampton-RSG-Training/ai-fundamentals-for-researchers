---
title: "Large Language Models"
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 



::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Explain what an LLM is and how it is trained.
- Describe the Transformer architecture at a conceptual level (attention mechanism).
- Distinguish between pre-training and fine-tuning.
- Identify key limitations of LLMs, including hallucination and context window constraints.

::::::::::::::::::::::::::::::::::::::::::::::::

## What is a Large Language Model?

- An LLM is a deep learning model trained on vast amounts of text to predict and generate language.
- "Large" refers to: the volume of training data (trillions of words) and the number of parameters (billions to trillions of weights).
- Key task learned during training: next token prediction — given a sequence of words, predict the most likely next word. From this simple objective, rich language abilities emerge.

## Transformer Architecture

- Introduced in 2017 (Google Brain); now the foundation of most state-of-the-art language models.
- Key innovation: the **attention mechanism** — the model learns which parts of the input text to "pay attention to" when processing each word.
- Analogy: when reading "The bank was steep and muddy, so she slipped," we automatically pay attention to *steep*, *muddy*, and *slipped* to understand that *bank* means a riverbank. Transformers learn to do something similar.
- Unlike older RNNs, Transformers can process all words in parallel, making them highly efficient on modern hardware.

## Training LLMs

- **Pre-training:** Train on a massive general text corpus (books, websites, academic papers, code) to build broad language knowledge. This is extremely expensive — can cost millions of dollars in compute.
- **Fine-tuning:** Take the pre-trained model and continue training on a smaller, task-specific dataset to tailor its behaviour (e.g. medical notes, legal documents, customer service).
- **RLHF (Reinforcement Learning from Human Feedback):** A technique used to align LLM outputs with human preferences — human raters score outputs, and the model is trained to produce higher-rated responses. This is how ChatGPT-style "helpfulness" is achieved.
- Analogy: pre-training is like a university education; fine-tuning is like a postgraduate specialisation.


## What LLMs Can and Cannot Do

- **Capabilities:** Fluent text generation, summarisation, translation, question answering, code generation, reasoning through problems step by step.
- **Hallucination:** LLMs confidently generate plausible-sounding but factually incorrect content. This is a fundamental property, not a bug to be patched. The model is optimised to produce coherent text, not verified truth.
- **Knowledge cutoff:** LLMs are trained on data up to a certain date — they do not have access to current events unless given tools to do so (e.g. web search plugins).
- **Context window:** LLMs can only "see" a limited amount of text at a time (their context window). Very long documents may be truncated.
- **Stochasticity:** Outputs are probabilistic — asking the same question twice may yield different answers.


:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## True or False

Are following statements are true or false — and why:

1. LLMs look up facts in a database when they answer questions. 
2. A fine-tuned LLM trained on medical literature will always give accurate medical advice.
3. Two researchers asking the same LLM the same question will always get the same answer.

:::::::::::::::::::::::: solution 

1. (False — they generate responses based on learned patterns, not database lookups.)
2. (False — hallucination can still occur; outputs must always be verified.)
3. (False — outputs are probabilistic.)

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Testing the Limitations of LLMs

Go to a conversational AI tool such as ChatGPT, Microsoft Copilot or Claude and ask the following questions:

1. Ask a factual question and verify the answer.
2. Ask the same question twice — compare outputs.
3. Ask a question that requires knowledge of a very recent event.
4. Ask it to summarise your research - to what extent is it correct?

:::::::::::::::::::::::: solution 


:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: callout



::::::::::::::::::::::::::::::::::::::::::::::::






::::::::::::::::::::::::::::::::::::: keypoints 



::::::::::::::::::::::::::::::::::::::::::::::::


