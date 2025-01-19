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

1 **Literature Review:** Analysis of empathetic AI and existing models (MEED, EPIMEED+, etc.).

2 **Dataset Collection:** Leveraging datasets like CounselChat and EmpatheticDialogues for fine-tuning.

3 **Model Development:**
 - Baseline: Fine-tuned LLaMA 3 on CounselChat.
 - Advanced: Emotion and intent-aware instruct fine-tuning.
 - Final: Transition to LLaMA 3.1 Instruct with improved instructions.
 - 
4 **Evaluation(TO BE DONE YET):**
 - Empathy and response diversity metrics.
 - Safety compliance for crisis situations.

for, detailed steps , refer to the Final report documentation [Link]()


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
