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

6. **Base Llama 2 Model vs. Chat Version:**
   - Specific prompt templates not necessary for base Llama 2 model, unlike the chat version.

(Note: LLMs = Large Language Models, SFT = Supervised Fine-Tuning, RLHF = Reinforcement Learning from Human Feedback, DPO = Direct Preference Optimization)

# Instructions to run the notebook
You can run the notebook in **Google Colab**, make sure to chane the runtime to GPU for training and testing or Use the link to access the notebook and run all: https://colab.research.google.com/drive/1Pv9w_EMjEAwk9HsJigtzMimgOSZ95eXS?usp=sharing


# Dataset Formatting to train Llama 2 model
As we need to follow the template of Llama 2 model for fine tuning, Lets create the data based on **Title** and **Description** of a news article.
1. **Importance of Prompt Templates:**
   - Prompt templates structure inputs: system prompt, user prompt, additional inputs, and model answer.
   - Different templates (e.g., Alpaca, Vicuna) have varying impacts.
   - Converting instruction dataset to Llama 2's template is important.
   - Llama 2's template example:
>```
> {"text": "input_text", "summary": "output_text"}
> {"text": "another_input_text", "summary": "another_output_text"}
> ...

In our case, a sample from our dataset:
>```
>### title: thousands of wild horses creating hazard for nevada drivers as collisions nearly double. ### 
>description: thousands of wild horses in the virginia range near lake tahoe are becoming increasingly hazardous to drivers — but residents have no legal means to control the population on their own.

# Results
After fine tuning the model, I have tested the model on the following prompt:
>```
>prompt = 'city!'

The text generated by the model:
>```
>city!
>everybody's talking about it!
>the city of santa cruz is a magical place located on the central coast of california. with stunning natural beauty, rich history, and vibrant culture, santa cruz is the perfect destination for travelers looking for an authentic california experience. from the >redwood forests to the sandy beaches, from the artistic community to the farmstands, santa cruz has it all. whether you're a local looking for the latest news and events or a traveler planning your trip, make sure to check out our comprehensive coverage of >everything that makes santa cruz special.

The output of the model talks about the city of santa cruz and the quality of the text generated is really extraodinary.

# Intuition and possibilities of Improvement
Llama 2 is pretrained on a massive amount of data, enabling it to capture complex patterns and relationships in language. This pretrained knowledge can be fine-tuned on a specific dataset for better performance in domain-specific tasks. It has a higher capacity to learn abstract concepts and generate coherent and contextually relevant text. This is beneficial for tasks that require nuanced language understanding and creative text generation.

With additional resources, I can enhance the Llama 2 fine-tuning process by focusing on three key aspects: model size, training data, and training duration. Firstly, consider utilizing a larger variant of Llama 2, if available, to benefit from increased model capacity and potentially capture more intricate patterns in the data. Secondly, augment the training dataset with diverse and representative examples, ensuring a broader coverage of the target domain. Collecting a more extensive and varied dataset can help the model generalize better. Lastly, extend the training duration by increasing the number of epochs or utilizing distributed training across multiple GPUs to allow the model to converge to a more refined state. Keep an eye on performance metrics during training to identify the optimal configuration. Additionally, exploring advanced techniques like mixed-precision training or experimenting with different hyperparameter settings can contribute to further improvements.
