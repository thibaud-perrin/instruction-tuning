# Supervised Fine-Tuning

Supervised Fine-Tuning (SFT) is the process of adapting pre-trained language models to perform specific tasks or operate within specialized domains. While pre-trained models possess general language capabilities, SFT fine-tunes their behavior to meet specific requirements by training them on curated datasets with labeled examples.

---

## Understanding Supervised Fine-Tuning

At its core, SFT involves teaching a pre-trained model how to perform specific tasks through examples of desired input-output behavior. This builds upon the model's foundational knowledge, refining its performance to align with particular use cases.

---

## When to Use Supervised Fine-Tuning

SFT is particularly valuable in scenarios requiring precise control or domain-specific expertise. For example:
- **Customer Service Applications**: Align responses with company guidelines.
- **Specialized Domains**: Ensure accuracy in fields like medicine, law, or programming.

By tailoring the model to your specific requirements, SFT ensures better task alignment and improved outputs.

---

## The Fine-Tuning Process

The SFT workflow involves:
1. **Dataset Preparation**: Select or curate a dataset representative of the task, with high-quality labeled examples.  
2. **Fine-Tuning**: Train the model on this dataset using frameworks like Hugging Face's `transformers` or `trl`.
3. **Evaluation**: Monitor performance on a validation set to ensure desired behavior without overfitting.

Continuous evaluation ensures the model learns the intended behaviors effectively.

---

## Results

### Pre-Fine-Tuning Example
Before fine-tuning, the model's response to user input was repetitive and lacked coherence:

```txt
user
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a haiku about programming
Write a
```

### Fine-Tuning on `HuggingFaceTB/smoltalk`
After training on the `HuggingFaceTB/smoltalk` dataset, the model's responses improved, demonstrating a better understanding of user queries:

```txt
user
Write a haiku about programming
assistant
Hello! How can I help you today? I'm a language model and I'm looking for help with programming. What programming language are you comfortable with? I'd be happy to help you learn. What programming language are you comfortable with? Python, Java, or something else? I can help you learn it. What programming language are you comfortable with? Python, Java, or something else? I can help you learn it. What programming language are you comfortable with? Python,
```

Though the response is not perfect due to limited training, the model begins to address the prompt in a conversational manner.

### Fine-Tuning on `bigcode/the-stack-smol`
After fine-tuning on Python code from the `bigcode/the-stack-smol` dataset (5,000 examples), the model demonstrates task-specific comprehension:

```txt
user
# write a snake movement function in python
assistant
```Python
# write a snake movement function in python

import random
import time

def snake_move(snake_x, snake_y, snake_length):
    global speed
    global direction
    global direction_list
    global direction_list_list
    global snake_x, snake_y, snake_length
    global direction_list, direction_list_list
    global direction_list_list_list
    global snake_x, snake_
```

While the response isn't flawless, the model correctly interprets the task, providing a structured code snippet relevant to the prompt.

---

## The Role of SFT in Preference Alignment

SFT is foundational for aligning language models with human preferences. Techniques like Reinforcement Learning from Human Feedback (RLHF) and Direct Preference Optimization (DPO) rely on SFT to establish a baseline of task-specific behavior. By incorporating domain-specific data, SFT ensures that the model produces outputs aligned with human expectations.

---

## Using TRL for Supervised Fine-Tuning

The `trl` library simplifies the fine-tuning process, offering tools for supervised fine-tuning, reward modeling, and preference optimization. Built on top of Hugging Face Transformers, `trl` supports pre-trained models and various architectures, making it an essential toolkit for fine-tuning tasks.

---

⏭️ [Next: Chat Templates Tutorial](./notebooks/chat_template.ipynb)  
⏭️ [Supervised Fine-Tuning Tutorial](./notebooks/supervised_fine_tuning.ipynb)
