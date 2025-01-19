# Chat Templates

Chat templates are a crucial tool for structuring interactions between users and language models. They ensure consistency and clarity by organizing conversations into roles and formats that models can understand. This allows for more accurate and contextually appropriate responses.

---

## Base Models vs Instruct Models

- **Base Models**: Trained on raw text data, they predict the next token in a sequence.  
- **Instruct Models**: Fine-tuned to follow instructions and engage in conversations.

To make a base model behave like an instruct model, prompts must follow a specific format, such as `ChatML`, which includes system messages, user inputs, and assistant responses. When using an instruct model, ensure the correct chat template aligns with its training.

---

## Chat Template Structure

Chat templates define how interactions are formatted. For example:

```sh
<|im_start|>user
Hi there!<|im_end|>
<|im_start|>assistant
Hello! How can I help you?<|im_end|>
```

In code, this structure translates to:

```python
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "Can you explain chat templates?"},
    {"role": "assistant", "content": "Chat templates structure conversations for consistency..."}
]
```

---

### Key Components

1. **System Messages**: Set the model's behavior.  
   Example:
   ```python
   {"role": "system", "content": "You are a polite and helpful assistant."}
   ```

2. **User and Assistant Messages**: Define the flow of conversations and maintain context across multiple turns.  
   Example:
   ```python
   [
       {"role": "user", "content": "What is calculus?"},
       {"role": "assistant", "content": "Calculus is a branch of mathematics..."}
   ]
   ```

---

## Using Chat Templates in Transformers

The `transformers` library simplifies working with chat templates. Messages can be structured programmatically:

```python
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("SmolLM2-135M-Instruct")

messages = [
    {"role": "system", "content": "You are a coding assistant."},
    {"role": "user", "content": "Write a Python function to sort a list."}
]

formatted_chat = tokenizer.apply_chat_template(messages, tokenize=False, add_generation_prompt=True)
```

---

## Customizing Templates

Templates can be tailored for specific roles or scenarios:

```python
template = """
<|system|>{system_message}
<|user|>{user_message}
<|assistant|>{assistant_message}
""".strip()
```

Multi-turn conversations are also supported, ensuring that context persists throughout the interaction.

⏭️ [Next: Supervised Fine-Tuning](./supervised_fine_tuning.md)
