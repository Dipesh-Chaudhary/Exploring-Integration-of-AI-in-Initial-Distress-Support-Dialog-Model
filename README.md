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
- Emotion recognition is essential for empathetic responses.
- Fine-grained intents help improve nuanced conversations.
- Balancing responses i.e. Emotional and cognitive elements alignment is must.
- Existing models often generate repetitive or inconsistent responses.
- High-quality, domain-specific datasets are limited orwe can say inaccessible due to privacy concerns.
  
**Gaps Identified**
- **End-to-end integration:** Most approaches use separate modules for emotion recognition, intent classification, and response generation.
- **Limited LLM exploration:** Few studies leverage state-of-the-art models like GPT-3 or LLaMA for mental health contexts.
For more details, refer to the Literature Review Section of the [final report]()


**2) Model Development:**

**2.1) Initial Prototype Development**
- Model: Fine-tuned LLaMA 3(due to it's capabilities , Availability & Efficiency) on the CounselChat dataset (3,000+ expert Q&A pairs).
  
![Screenshot (498)](https://github.com/user-attachments/assets/64dde6c5-8514-4db1-9665-f31b60b48d1e)

fig:*Chat snippet of the Finetuned model on counsel-chat dataset*

- **Evaluation & Results:**
  - Empathy Misfire:
    - Conversation:
    1. Bot: "I'm not sure if this will help, but I've been in your shoes before..."
    2. User: "you should help me out, rather you are crying with me."
    - Evaluation: The bot’s attempt to empathize by sharing its own experience backfires, as the user feels unsupported. This indicates the bot needs to focus more on the user's emotions and less on its own.
    
  - Frustration Handling:
    - Conversation:
    1. User: "you should help me out, rather you are crying with me."
    2. Bot: "I'm so sorry that you are feeling this way... How can I help you?"
    - Evaluation: The user’s frustration escalates, and while the bot acknowledges the emotion, its response is too passive. The bot should take more initiative instead of asking generic questions like "How can I help you?"

  - Repetitive and Redundant Responses:
    - Conversation:
    1. Bot: "You told me that you don't know why you're not motivated to study for 
    your exam tomorrow."
    2. Bot: "Well, if you don't know why you're not motivated to study, then you can't 
    really know what to do to change that..."
    - Evaluation: The bot repeats the same idea without introducing any new 
    suggestions or approaches, making the response feel redundant and less helpful.

**Hence, due to it's limitations we decided to explore more state of the art model that are built from  scratch**

It's notebook for fintuning and demo of use is available [here](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/tree/main/Notebook/1.%20Initial%20prototype%20development)
the finetuned model is uploaded to huggingface over [here](https://huggingface.co/DipeshChaudhary/ShareGPTChatBot-Counselchat1)

For more details, refer to the **chapter 3.2** of the [final report](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/blob/main/Docs/Final%20Report.pdf)

**2.2) Advanced Model Exploration**
- MEED2[2]: Integrated emotion embeddings into encoder-decoder architecture, showing a 15% improvement in empathy scores.

![Screenshot (542)](https://github.com/user-attachments/assets/66e42d1b-7adb-4c47-a806-80211e971898)

- EPIMEED+[3]: Added cognitive reactions to the emotional responses, dynamically balancing empathy and coherence. However, full implementation was constrained by resource limitations.

  ![Screenshot (544)](https://github.com/user-attachments/assets/2474123f-9fbb-4366-8d81-87b58c104d86)



for more details,  refer to the literature review or **chapter 3.3** of the [final report](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/blob/main/Docs/Final%20Report.pdf) or review [2] and [3] as referenced below
 
**2.3) Custom Model Development Attempts**
- *So, by analyzing above 2 architecture ,  i decided to add emotion embeddings in Llama architecture and further train that embeddings by finetuning it with the counseling data*
  
  ![Screenshot (545)](https://github.com/user-attachments/assets/a7472490-e6f2-4792-8ab3-1e237ddc2efc)

- Modified LLaMA Architecture: Included emotion embeddings for nuanced understanding in LLaMA architecture but faced challenges like increased parameters and memory constraints as shown in below screenshot ,so had to drop this plan .
![Screenshot (546)](https://github.com/user-attachments/assets/799e4102-2197-4825-990d-63ea9d07af31)

It's notebook can be found [here](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/tree/main/Notebook/2.%203%20Custom%20Model%20Development%20Attempt)

**[NOTE: YOU DONOT HAVE TO SEE THE NOTEBOOKS CONTAINED IN THE UNSUCCESSFUL TRIAL AND ERROR FOLDERS, AS IT IS ONLY KEPT THERE FOR MY REVISION AND COUL CREATE MANY CONFUSIONS]**
  
**2.4) Alternative Fine-Tuning Approach**

*Given the challenges encountered with our custom model architecture, we explored alternative approaches to achieve our goals within our resource constraints*

- Emotion and Intent-Aware Tuning: Leveraged a dataset with 32 emotions (e.g., "joyful," "anxious") and 9 intents (e.g., "encouraging," "consoling") .
  
- Added structured input prompts to explicitly guide the model's emotional understanding and intent prediction by adding default instructions on the coversation template using"User is feeling" & "Assistant's intent in reply should be ", as shown in below SS .
  
  ![Screenshot (505)](https://github.com/user-attachments/assets/ab584e80-272b-497b-97f9-f106b692275f)

Still didnot get proper empathetic cognitive responses as we wanted .
It's notebook can be found [here](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/tree/main/Notebook/3%20%20Alternative%20Fine-tuning%20Approaches)

**2.5) Final Implementation**
During the work a new free open source state-of-the-art llm model [LLaMA 3.1](https://ai.meta.com/blog/meta-llama-3-1/) got introduced so decided to give it a try

Due to it's high performance in instruction tuning ,high parameters and lack of proper required counselling data and resources constraint ,we decided to focus on improving the instructions so that it could get proper idea of how and what to response.
- Model: Transitioned to LLaMA 3.1 Instruct, emphasizing instruction tuning for enhanced performance without extensive fine-tuning.
- Framework: Incorporated the EMPATHY framework:
Emotion recognition, Mirroring, Perspective-taking, Active listening, Tailored response, Helping, Yielding space.
- Process:
 Compiled detailed instructions with context for better response generation.

![Screenshot (506)](https://github.com/user-attachments/assets/dc6677ae-a4e2-405e-b0d7-5f5afbdd031f)

    fig: *Chat snippet of the llama 3.1 instruction tuned chatbot*
    
   **Evaluations:**

   **Emotional Reactions:**
   
    i. Empathy Displayed (Emotional Reaction)
      Conversation part:
      • Bot: "I can see why that would be frustrating . Math problems can be really 
      annoying when they're stuck in our minds."
      This response reflects an emotional reaction by acknowledging the user's 
      frustration, showing empathy for their struggle.
      
    ii. Apology and Clarification (Emotional Reaction)
      Conversation part:
      • Bot: "I'm not trying to make fun of you, and I apologize if it came across that 
      way. My intention is to help you feel better."
      The chatbot displays an emotional reaction by apologizing and reassuring the 
      user that it wasn’t trying to make light of their frustration, signaling care for the 
      user's feelings.
    iii. Recognition of Sarcasm (Emotional Reaction)
      Conversation part:
      • Bot: "Ahahaha, I get it now! Sarcasm can be a tough one to catch, but I'm 
      glad we could have a laugh about it."
      The chatbot’s laugh and understanding of sarcasm showcase an emotional 
      adjustment, recognizing the user’s playful tone.
    iv. Acknowledgement of Frustration (Emotional Reaction)
      Conversation part:
      • Bot: "You're not alone, and it's okay to ask for help. Would you like to talk about 
      what's really going on and how you're feeling about this problem?"
      The bot continues its emotional reaction by offering emotional support and 
      reassurance that it's okay to seek help, validating the user's feelings.

   **Cognitive Reactions:**
   
    i. Interpretation of Problem Trigger (Cognitive Reaction: Interpretation)
      Conversation part:
      • Bot: "It's something else that's bothering you, and the math problem was just a 
      trigger. That's totally okay!"
      The bot interprets the user's statement and recognizes that the math problem is 
      not the root cause, but a surface-level trigger for a deeper issue.
      
    ii. Exploring Underlying Issue (Cognitive Reaction: Exploration)
      Conversation part:
      • Bot: "We can explore this further. Would you like to talk about what's really on 
      your mind?"
      The chatbot explores the possibility that there are deeper concerns the user is 
      not expressing, encouraging further reflection and dialogue.

    iii. Handling Criticism and Seeking Feedback (Cognitive Reaction: Exploration)
      Conversation part:
      • Bot: "If there's anything specific that I did or said that made you feel this way, 
      I want to know so I can learn and improve."
      This shows cognitive exploration, where the bot seeks to understand the user's 
      frustration more deeply and improve its performance based on feedback.
      
    iv. Acknowledgement of Limitations (Cognitive Reaction: Interpretation)
      Conversation part:
      • Bot: "You're right, I'm not a licensed therapist, and I have my limitations. 
      However, I'm designed to provide support, guidance, and resources."
      The chatbot interprets the user’s statement about its limitations and 
      acknowledges its own boundaries, providing clarity about its role.

for better understanding of it's implementation, notebook can be found [here](https://github.com/Dipesh-Chaudhary/Exploring-Integration-of-AI-in-Initial-Distress-Support-Dialog-Model/tree/main/Notebook/4%20Instruction%20engineering)

**[NOTE: YOU DONOT HAVE TO SEE THE NOTEBOOKS CONTAINED IN THE TRIAL AND ERROR FOLDERS, AS IT IS ONLY KEPT THERE FOR MY REVISION AND COUL CREATE MANY CONFUSIONS]**

**2.6) Architectural Highlights**
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
