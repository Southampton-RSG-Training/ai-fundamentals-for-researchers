---
title: "AI in Research"
teaching: 20
exercises: 5
---

:::::::::::::::::::::::::::::::::::::: questions

- How are AI techniques being used across research disciplines today?
- What questions should I ask before adopting an AI tool in my research workflow?
- What ethical responsibilities do I have as a researcher using AI?
- How do I handle transparency and reproducibility when AI has been part of my methodology?

::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Identify AI applications relevant to your own research discipline.
- Apply a set of critical evaluation questions to any AI tool before adopting it.
- Describe the key ethical concerns raised by the use of AI in research, including bias, transparency, privacy, and attribution.
- Explain why reproducibility is a particular challenge when AI is part of a research workflow.

::::::::::::::::::::::::::::::::::::::::::::::::


## Introduction

Throughout this course we have built up a conceptual map of the AI landscape: from the broad field of machine learning, through the layered representations of deep learning, to the language capabilities of large language models. In this final episode we ask the question that matters most for you as a researcher: "What can I do with AI in my research?"

The goal of this episode is not to tell you whether to use AI in your research, but to give you the knowledge to make that decision well including how to recognise opportunities, ask the right critical questions, and engage seriously with the ethical responsibilities that come with AI tools.


## How Researchers Are Using AI Today

AI techniques are being applied across virtually every research domain. The examples below are illustrative rather than exhaustive.  The aim of this episode is to help you begin connecting the technical ideas from earlier episodes to work that may be relevant to your own field.

### Working with Text

Text is one of the most abundant forms of data in research, and AI tools for working with text are among the most mature. Researchers are using LLMs and related tools to:

- Assist with literature reviews by summarising large volumes of papers.
- Support qualitative coding of interview transcripts, field notes, or open-ended survey responses.
- Draft and revise written outputs such as grant applications, reports, and manuscripts.
- Extract structured information such as dates, entities, or relationships from unstructured documents such as historical records or clinical notes.
- Analyse sentiment or tone across large amounts of text, such as social media data or policy documents.

### Analysing Images and Signals

Convolutional neural networks (introduced in [Episode 3](3-deep-learning.md)) have transformed the analysis of visual data and complex signals. Applications include:

- Classifying cell types or identifying anomalies in microscopy images.
- Detecting objects or changes in satellite or aerial imagery for environmental, geographic, or agricultural research.
- Supporting diagnostic imaging in clinical settings by identifying tumours, fractures, or lesions.
- Recognising patterns in audio signals such as birdsong, seismic activity, or cardiac rhythms.

### Working with Tabular and Structured Data

Supervised machine learning methods are highly effective for analysing structured datasets of the kind that appear throughout quantitative research.  For example:

- Predicting outcomes in clinical trials or epidemiological studies.
- Detecting anomalies or fraud in financial datasets.
- Classifying observations in ecology.
- Building recommendation systems for research infrastructure, such as suggesting reviewers for journal submissions.

### Code and Data Analysis Assistance

LLMs have rapidly become practical tools for researchers who work with data by writing code. AI coding assistants can write, explain, and debug code in languages such as Python and R, making computational methods more accessible to researchers who do not have a formal programming background. This can be incredibly useful but you should be cautious about using AI-written code in your research if you don't understand it. Due to the limitations in LLMs, AI generated code isn't always correct! 

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: callout

### AI as a Collaborator

A theme running through all of these applications is that AI tools work best when used as a tool to complement the expertise of a human researcher, rather than replacing the researcher. An LLM that assists with qualitative coding still requires a researcher who understands the domain, the methodology, and the data. A computer vision model that flags anomalies in microscopy images still requires a scientist who can interpret what those anomalies mean.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::



## Ethical Considerations

Using AI in research is an ethical as well as a methodological question. The following are among the most important issues for researchers to engage with.

### Bias and Fairness

AI models do not arrive in the world as neutral tools. They are trained on data generated by human societies, and those societies contain historical and structural inequalities. A model trained on historical medical records will reflect historical disparities in who received care and who was documented. A model trained on published academic literature will reflect who has historically had access to publish.

The consequences can be serious. Models used for clinical risk prediction have been shown to perform worse on patients from groups underrepresented in the training data. Automated tools used in hiring or admissions have reproduced patterns of discrimination from historical decisions.

As a researcher, bias matters in two distinct ways:

- **Bias in tools you use:** if an AI tool is part of your analysis, its biases may propagate into your findings.
- **Bias in research you produce:** if you build or fine-tune AI models as part of your research, you have a responsibility to evaluate and document their limitations across the populations they may affect.

### Transparency and Reproducibility

Research integrity depends on being transparent about your methods. When AI is part of your workflow, transparency requires:

- Stating clearly which AI tools were used, for what purpose, and at what stage of the research.
- Citing specific model versions wherever possible, so that readers can assess potential limitations and replicate your approach.
- Describing how you validated or checked AI-generated outputs.
- Acknowledging limitations that arise specifically from using AI, such as the probabilistic nature of LLM outputs or the knowledge cutoff of the model used.

### Privacy and Data Governance

Many AI tools, particularly cloud-based LLMs, process data on external servers. If you input sensitive data such as patient records, interview transcripts, or confidential documents, into a commercial AI tool, you may be:

- Breaching participant confidentiality.
- Violating data protection legislation such as the UK GDPR.
- Contravening your institution's data governance policies or your ethical approval conditions.

Before inputting any data into an AI tool, check your institution's and research group's guidance on what categories of data may be processed in this way, and review the tool provider's privacy and data retention policies.


### Attribution and Authorship

LLMs have raised genuinely novel questions about authorship and attribution that the research community is still working through. Key issues include:

- **Authorship of AI-generated text:** most major publishers and funders now have explicit policies stating that AI tools cannot be listed as authors, because authorship carries accountability that an AI model cannot hold. However, policies on *disclosing* the use of AI in drafting or editing text vary and are evolving rapidly.
- **Attribution of AI-generated analysis:** if an LLM assists with qualitative coding or data interpretation, how should that contribution be disclosed in the methods section?
- **Copyright in training data:** LLMs are trained on text that may include copyrighted material. The legal and ethical status of this is an active area of debate.  By including AI-generated text or code in your research, you may inadvertantly be infringing copyright.

You should check the current policies of your target journal or funder, and your institution's own guidance, before submitting work in which AI has played a role.


::::::::::::::::::::::::::::::::::::::::: challenge

### Challenge: The Critical Reviewer

You are reviewing a manuscript submitted to your field's leading journal. In the methods section, the authors write:

> *"Qualitative thematic analysis of interview transcripts was supported by an AI language model, which was used to generate initial codes. These codes were then reviewed and refined by the research team. The AI tool assisted with the analysis of all 47 transcripts."*

Discuss the following questions:

1. What information is missing from this methods description that you would need as a reviewer?
2. What risks or limitations should the authors have acknowledged?
3. What would a more complete and transparent methods statement look like?

::::::::::::::::::::: solution

### Points to consider

**Information that is missing:**

- Which AI tool was used, and which version? (Without this, the approach cannot be evaluated or replicated.)
- What prompts or instructions were given to the model?
- How were AI-generated codes accepted, modified, or rejected?
- Was the tool validated on similar data or in similar research contexts?
- How was participant data handled? Was it anonymised before being input? Was the tool's data retention policy checked against ethical approval conditions?

**Risks and limitations the authors should have acknowledged:**

- LLMs can produce plausible-sounding codes that do not accurately reflect the content of the transcript.
- The model may perform inconsistently across different transcripts, introducing variability that is difficult to detect.
- The model's outputs may reflect biases in its training data rather than patterns in the research data.
- If the same analysis were run again, the model might produce different initial codes.

**A more complete methods statement might include:**

- The name and version of the AI tool used.
- A description of how the tool was prompted and integrated into the coding workflow.
- A statement of how participant data was handled in compliance with ethical approval and data protection requirements.
- A description of the human review process e.g. how many researchers reviewed codes, whether inter-rater reliability was assessed, how disagreements were resolved.
- An explicit acknowledgement of the limitations of AI-assisted coding and how these were mitigated.

:::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

### Environmental Cost of AI

The environmental cost of AI is larger and more complex than most users appreciate. The most recent estimates suggest that in 2025, AI systems generated up to 79.7 million tonnes of carbon, which is comparable to the annual emissions of a major city, and consumed up to 764 billion litres of water, which is comparable to global bottled water consumption  ([de Vries-Gao, 2025](https://doi.org/10.1016/j.patter.2025.101430)). 

These costs accumulate across the full lifecycle of an AI model.  This includes the water and carbon used to manufacture the specialist chips required to run the AI; the intensive one-off cost of training the model; and the ongoing costs of inference (the cost every time a query is run). 

A [2019 study](https://www.technologyreview.com/2019/06/06/239031/training-a-single-ai-model-can-emit-as-much-carbon-as-five-cars-in-their-lifetimes/#:~:text=A%20paper%20from%20the%20University%20of%20Massachusetts%2C,on%20teaching%20machines%20to%20handle%20human%20language.) found that training a single large transformer model can emit over 283,000 kg (626,000 pounds) of carbon, which is roughly equivalent to five times the lifetime emissions of an average American car. 

Although many people believe that initial training has the largest environmental cost, recent studies have found that inference can actually account for up to 90% of a model's lifetime energy use. Water consumption follows a similar pattern, with estimates suggesting a standard ChatGPT conversation of 20–50 exchanges requires roughly 500 millilitres of freshwater for cooling the servers in data centres ([Li et al., 2023](https://dl.acm.org/doi/10.1145/3724499)).

Not all AI is equally environmentally expensive. General-purpose LLMs are orders of magnitude more energy-intensive per inference than smaller, task-specific models performing the same job.  This means that the convenience of using a single general-purpose LLM interface can carry a substantial and largely invisible environmental cost when multiplied across many uses. A fine-tuned model used for classification or information extraction may produce comparable results at a fraction of the per-query energy cost ([Luccioni et al., 2024](https://doi.org/10.1145/3630106.3658542))

The biggest obstacle to accurate environmental accounting for AI is the problem of transparency.  The companies operating the largest AI systems publish very little useful data.  Furthermore, the published per-query emissions figures from AI providers typically reflect optimised, market-based conditions, rather than an accurate estimate of carbon and water usage ([de Vries-Gao, 2025](https://doi.org/10.1016/j.patter.2025.101430)). 


## Looking Ahead: Developing Your AI Literacy

This course has given you a map of the AI landscape and the vocabulary to navigate it. 

A few practical suggestions for developing your AI literacy beyond this course:

- **Follow your institution's guidance.** Most universities and research funders are actively developing AI use policies. These are the most directly relevant to your work, and they will continue to evolve.
- **Engage with your research community.** Methodological norms for AI use in research are being worked out discipline by discipline. Engaging with debates in your own field's journals and conferences is more valuable than generic AI news.
- **Start small and validate.** If you are considering integrating an AI tool into your workflow, start with a small, low-stakes task and validate the outputs carefully before scaling up.
- **Be transparent.** When in doubt about how much to disclose about your use of AI, err on the side of transparency. The research community is better served by over-disclosure than by the opposite.


::::::::::::::::::::::::::::::::::::: keypoints

- AI techniques are being applied across research disciplines, from text analysis and image classification to code generation and structured data modelling.
- Before adopting any AI tool, ask: what was it trained on? Has it been validated? Can results be reproduced? Can outputs be explained? What are the failure modes?
- AI models reflect the biases in their training data.
- Transparency in methods is essential: report which tools were used, at what version, for what purpose, and how outputs were validated.
- Privacy and data governance must be considered before inputting any sensitive or personal data into an AI tool.
- Authorship, attribution, and environmental cost are emerging ethical considerations that researchers should engage with actively.
- Developing AI literacy is an ongoing practice: follow institutional guidance, read model documentation, and engage with methodological debates in your own field.

::::::::::::::::::::::::::::::::::::::::::::::::

## References

- [de Vries-Gao, A. (2025). The carbon and water footprints of data centers and what this could mean for artificial intelligence. Patterns, 6, 101430.](https://doi.org/10.1016/j.patter.2025.101430)
- [Li, P., Yang, J., Islam, M. A., & Ren, S. (2023). Making AI less "thirsty": Uncovering and addressing the secret water footprint of AI models. Communications of the ACM.](https://dl.acm.org/doi/10.1145/3724499)
- [Luccioni, A. S., Jernite, Y., & Strubell, E. (2024). Power hungry processing: Watts driving the cost of AI deployment. Proceedings of the 2024 ACM Conference on Fairness, Accountability, and Transparency, 85–99](https://doi.org/10.1145/3630106.3658542)
