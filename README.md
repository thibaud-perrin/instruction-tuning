
![DALL·E-2025-01-19-21 21](https://github.com/user-attachments/assets/a3654de2-8155-4fd2-981b-a84320169c60)

# Instruction Tuning

In this project we explore how work instruction tuning language models. Instruction tuning is the process of adapting pre-trained models to specific tasks by further training them on task-specific datasets. This technique enhances model performance on targeted tasks.

The repository is structured around two main topics: **Chat Templates** and **Supervised Fine-Tuning**.

---

## 1️⃣ Chat Templates

Chat templates are designed to structure interactions between users and AI models. They ensure consistent and contextually relevant responses by organizing prompts and messages with roles and system instructions. Learn more about chat templates in the [Chat Templates](./chat_templates.md) section.

---

## 2️⃣ Supervised Fine-Tuning

Supervised Fine-Tuning (SFT) focuses on adapting pre-trained language models to specific tasks by training them on labeled, task-specific datasets. This approach is essential for achieving higher accuracy and relevance in specialized use cases. Detailed information and guidance can be found in the [Supervised Fine-Tuning](./supervised_fine_tuning.md) section.

---

## Notebooks Overview

The repository includes interactive notebooks that demonstrate the key concepts:

### Chat Templates
Show how to apply chat templates with SmolLM2 and process datasets into the `chatml` format.
- **Notebook:** [Chat Template](./notebooks/chat_template.ipynb)
- **Key Datasets:**
  - Convert the `HuggingFaceTB/smoltalk` dataset into `chatml` format.
  - Convert the `openai/gsm8k` dataset into `chatml` format.

### Supervised Fine-Tuning
Show how to fine-tune SmolLM2 using the `SFTTrainer` from the `trl` library.
- **Notebook:** [SFT Fine-Tuning](./notebooks/supervised_fine_tuning.ipynb)
- **Key Datasets:**
  - Use the `HuggingFaceTB/smoltalk` dataset.
  - Fine-tune using the `bigcode/the-stack-smol` dataset with a subset focused on 50,000 data only.
