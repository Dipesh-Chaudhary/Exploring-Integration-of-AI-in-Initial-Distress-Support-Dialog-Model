# Exploring Integration of AI in Initial Distress Support Dialog Model


## Overview
This repository contains the code, data, and documentation for the final year project titled **"Exploring Integration of AI in Initial Distress Support Dialog Model."** This project focuses on leveraging **Large Language Models (LLMs)** to develop an AI-powered chatbot capable of empathetically responding to users experiencing emotional distress.

The project explores various AI architectures and fine-tuning techniques, including emotion and intent-aware instruct tuning, to improve the chatbot's ability to provide meaningful support. It aims to address the growing mental health challenges globally by offering accessible and empathetic preliminary support.

## Key Features
- Empathy-driven conversations using advanced LLMs (e.g., LLaMA 3.1 Instruct).
- Emotion and intent awareness for nuanced responses.
- Iterative development and evaluation of architectures like MEED2 and EPIMEED+.
- Ethical design ensuring safety and compliance with mental health guidelines.
## Methodology
The project involves the following stages:

**1) Existing Approaches and Problem Analysis**
Our research began with a comprehensive review of empathetic AI models for early distress support. Key steps included identifying over 50 papers from databases like Arxiv and Google Scholar, screening 15 for detailed analysis, and synthesizing insights on methodologies, datasets, architectures, and limitations.

**Key Insights**
- **Emotion recognition:** Essential for empathetic responses.
- **Fine-grained intents:** Improved nuanced conversations.
- **Balancing responses:** Emotional and cognitive elements must align.
- **Challenges in coherence:** Existing models often generate repetitive or inconsistent responses.
- **Dataset scarcity:** High-quality, domain-specific datasets are limited.
  
**Gaps Identified**
- **End-to-end integration:** Most approaches use separate modules for emotion recognition, intent classification, and response generation.
- **Limited LLM exploration:** Few studies leverage state-of-the-art models like GPT-3 or LLaMA for mental health contexts.
For more details, refer to the Literature Review Section of the [final report]()


**2) Model Development:**
**2.1) Initial Prototype Development**
- Model: Fine-tuned LLaMA 3 on the CounselChat dataset (3,000+ expert Q&A pairs).
- Results: The prototype lacked emotional understanding, generated generic responses, and struggled with multi-turn conversations.
**2.2) Advanced Model Exploration**
- MEED2[1]: Integrated emotion embeddings into encoder-decoder architecture, showing a 15% improvement in empathy scores.
- EPIMEED+[2]: Added cognitive reactions to the emotional responses, dynamically balancing empathy and coherence. However, full implementation was constrained by resource limitations.
**2.3) Custom Model Development**
- Modified LLaMA Architecture: Included emotion embeddings for nuanced understanding in LLaMA architecture but faced challenges like increased parameters and memory constraints,so had to drop this plan .
**2.4) Alternative Fine-Tuning Approach**
- Emotion and Intent-Aware Tuning: Leveraged a dataset with 32 emotions (e.g., "joyful," "anxious") and 9 intents (e.g., "encouraging," "consoling") .
- Added structured input prompts to explicitly guide the model's emotional understanding and intent prediction.
Still didnot get proper empathetic cognitive responses as we wanted.
**2.5) Final Implementation**
During the work a new free open source LLM [LLaMA 3.1](https://ai.meta.com/blog/meta-llama-3-1/) was introduced so decided to give it a try
- Model: Transitioned to LLaMA 3.1 Instruct, emphasizing instruction tuning for enhanced performance without extensive fine-tuning.
- Framework: Incorporated the EMPATHY framework:
Emotion recognition, Mirroring, Perspective-taking, Active listening, Tailored response, Helping, Yielding space.
- Process:
 Compiled detailed instructions with context for better response generation.
 Evaluated outputs for empathy, context adherence, and safety.
**2.6) Architectural Highlights
- Baseline: Fine-tuned LLaMA 3 with basic emotional context.
- MEED2: Added pre-trained emotion classifiers for embedding generation.
- EPIMEED+: Combined emotion and cognitive aspects via dual encoders.
- Tried to Finetune LLama inspired by MEED2 and EPIMEED (but had to drop the plan due to resources constraint)
- Final: Used LLaMA 3.1 Instruct for instruction-tuned responses .


## Future Work
 - Evaluate in proper evaluation etrics
 - Introduce multimodal inputs (e.g., voice, text).
 - Deploy a user-friendly interface using platforms like Streamlit or Hugging Face Spaces.

## Acknowledgments
We thank our supervisor, Er. Shailesh Pandey, and the Department of IT, Everest Engineering College, for their guidance and support. We also acknowledge the researchers and contributors of datasets like CounselChat and EmpatheticDialogues.

## References

[1] Rashkin, H., Smith, E. M., Li, M., & Boureau, Y.-L. (2019). Towards Empathetic Open-domain Conversation Models. *Proceedings of the 57th Annual Meeting of the Association for Computational Linguistics*, 5370–5381. [Link](https://arxiv.org/abs/1811.00207)

[2] Xie, Y., & Pu, P. (2021). Empathetic Dialog Generation with Fine-Grained Intents. *ArXiv*, abs/2105.06829. [Link](https://arxiv.org/abs/2105.06829)

[3] Welivita, A., & Pu, P. (2023). Empathetic Response Generation for Distress Support. *Proceedings of the 24th Annual Meeting of the Special Interest Group on Discourse and Dialogue (ACL)*, 632–644. [Link](https://aclanthology.org/2023.sigdial-1.59/)
