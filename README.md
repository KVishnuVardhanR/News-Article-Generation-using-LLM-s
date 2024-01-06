# News-Article-Generation-using-LLM-s
Llama 2 LLM for news article generation based on data obtained by media stack API.  

# Background on fine-tuning LLMs

![](https://archive.is/0iIXL/5f30742c57ad532b4cda9f1b48790dbcc7d00a85.webp)

**Summary:**

1. **LLM Pretraining:**
   - Large Language Models (LLMs) are pretrained on extensive text corpora.
   - Llama 2 was pretrained on a dataset of 2 trillion tokens, compared to BERT's training on BookCorpus and Wikipedia.
   - Pretraining is resource-intensive and time-consuming.

2. **Auto-Regressive Prediction:**
   - Llama 2, an auto-regressive model, predicts the next token in a sequence.
   - Auto-regressive models lack usefulness in providing instructions, leading to the need for instruction tuning.

3. **Fine-Tuning Techniques:**
   - Instruction tuning uses two main fine-tuning techniques:
     a. Supervised Fine-Tuning (SFT): Trained on instruction-response datasets, minimizing differences between generated and actual responses.
     b. Reinforcement Learning from Human Feedback (RLHF): Trained to maximize rewards based on human evaluations.

4. **RLHF vs. SFT:**
   - RLHF captures complex human preferences but requires careful reward system design and consistent human feedback.
   - Direct Preference Optimization (DPO) might be a future alternative to RLHF.
   - SFT can be highly effective when the model hasn't encountered specific data during pretraining.

5. **Effective SFT Example:**
   - LIMA paper showed improved performance of LLaMA v1 model over GPT-3 by fine-tuning on a small high-quality dataset.
   - Data quality and model size (e.g., 65b parameters) are crucial for successful fine-tuning.

6. **Importance of Prompt Templates:**
   - Prompt templates structure inputs: system prompt, user prompt, additional inputs, and model answer.
   - Llama 2's template example: <s>[INST] <<SYS>> System prompt <</SYS>> User prompt [/INST] Model answer </s>
   - Different templates (e.g., Alpaca, Vicuna) have varying impacts.

7. **Reformatting for Llama 2:**
   - Converting instruction dataset to Llama 2's template is important.
   - The tutorial author already reformatted a dataset for this purpose.

8. **Base Llama 2 Model vs. Chat Version:**
   - Specific prompt templates not necessary for base Llama 2 model, unlike the chat version.

(Note: LLMs = Large Language Models, SFT = Supervised Fine-Tuning, RLHF = Reinforcement Learning from Human Feedback, DPO = Direct Preference Optimization)
