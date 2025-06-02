Link to Jupyter Source File: 
https://colab.research.google.com/drive/1oSWkboyXhK3g1Xk8gdNXyjwVYEEOlMci?usp=sharing

**GPT-2 Fine-Tuning on Custom Text Dataset**

This project demonstrates how to fine-tune the GPT-2 language model on a custom plain text dataset using Hugging Face's `transformers` and `datasets` libraries. The resulting model can be used for text generation based on your specific domain or writing style.

**🔗 [Open in Google Colab](https://colab.research.google.com/drive/1oSWkboyXhK3g1Xk8gdNXyjwVYEEOlMci?usp=sharing)**

---

📦 **Requirements**

pip install transformers datasets


📋 **Overview**
The code performs the following steps:

**1. Tokenizer Setup**
Loads the GPT-2 tokenizer and sets the padding token to be the same as the end-of-sequence token (eos_token).

**2. Dataset Loading**
Loads a plain text file (/content/data.txt) using Hugging Face's datasets library.

**3. Tokenization**
Defines a tokenization function that:
Tokenizes the text using the GPT-2 tokenizer
Truncates or pads the sequence to a fixed length (128 tokens)
Returns PyTorch tensors
Applies the tokenization function and sets the labels for causal language modeling (input shifted by one).

**4. Model Loading**
Loads the pretrained GPT-2 model for causal language modeling.

**5. Training Setup**
Configures the training arguments including:
Output directory
Number of training epochs
Batch size
Save and logging steps
Learning rate and weight decay

**6. Training**
Initializes the Trainer and starts training on the tokenized dataset.

**7. Model Saving**
Saves the fine-tuned model and tokenizer locally in the ./gpt2-finetuned directory.

**8. Text Generation**
Loads the fine-tuned model and uses the pipeline API to generate text from a prompt (e.g., "Neurons are").
