---
title: AI in Research
teaching: 10 # teaching time in minutes
exercises: 2 # exercise time in minutes
---

:::::::::::::::::::::::::::::::::::::: questions 



::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Identify practical applications of AI techniques relevant to their field.
- Critically assess AI tool outputs rather than accepting them uncritically.
- Describe key ethical concerns around bias, transparency, and reproducibility in AI.
- Know what questions to ask before adopting an AI tool in their research workflow.

::::::::::::::::::::::::::::::::::::::::::::::::

# How Researchers are using AI

- AI applications in research:
  - **Text and literature:** Automated literature review support, document summarisation, qualitative coding assistance.
  - **Images and signals:** Microscopy image analysis, satellite imagery classification, medical imaging, seismology.
  - **Tabular and structured data:** Predictive modelling, anomaly detection, pattern discovery.
  - **Audio and speech:** Automated transcription, speaker identification, bioacoustic analysis.
  - **Multimodal:** Combining text, image, and data for richer analysis.
- Emphasis: AI as a *tool to augment* researchers, not replace them. Researchers provide domain knowledge, critical judgement, and ethical oversight.


## Critical Evaluation of AI Tools

- Questions to ask before using an AI tool in research:
  - What data was this model trained on? Does it represent my population or domain?
  - Has it been independently validated? By whom and on what benchmarks?
  - What are the known failure modes or limitations?
  - Is the tool explainable — can I understand *why* it produced a given output?
  - Can I reproduce results and cite the model version?
- Introduce the concept of *explainability* vs *interpretability* — some models are black boxes; in high-stakes research, this matters.


## Ethical Considerations

- **Bias and fairness:** Models reflect the biases in their training data. A language model trained on historical text will encode historical inequalities. A clinical model trained on data from one population may underperform on others.
- **Transparency and reproducibility:** Can you describe your AI methods clearly enough for others to replicate your results? Are you using a versioned model?
- **Privacy and data governance:** Training data or input data may contain sensitive personal information. What are the data sharing implications?
- **Authorship and attribution:** Who is the "author" when AI assisted in writing or analysis? What do your institution's and your target journal's policies say?
- **Environmental cost:** Training large models has a significant carbon footprint — relevant for sustainability-conscious researchers.


:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor



::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge 

## Critical Evaluation of AI in Research

**Scenario**: You are reviewing a paper where the authors used an LLM to assist with qualitative coding of interview transcripts. What questions would you want the authors to have answered in their methods section?

:::::::::::::::::::::::: solution 

Possible discussion points: which model/version was used; how was the output validated; how was human oversight applied; what were the model's known limitations; are there any privacy implications for the participants?

:::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::::::::::::::



::::::::::::::::::::::::::::::::::::: callout



::::::::::::::::::::::::::::::::::::::::::::::::






::::::::::::::::::::::::::::::::::::: keypoints 



::::::::::::::::::::::::::::::::::::::::::::::::


