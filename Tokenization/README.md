Link to Jupyter Source File: https://colab.research.google.com/drive/1CP9iJewC8YjSOo05TWfR4JdSRLfeWLpT?usp=sharing


# 📚 Custom Tokenizer & Text Encoding for LLMs

This project demonstrates how to build a **simple tokenizer** from scratch and explores **tokenization techniques** used in modern **Large Language Models (LLMs)** such as GPT. The tokenizer is tested on *The Verdict*, a short story, and includes preprocessing, vocabulary creation, token ID mapping, and byte pair encoding.

---

## 📌 Project Overview

### Objectives:

* Build a basic rule-based tokenizer (with and without special tokens)
* Encode and decode text using custom vocabulary
* Handle out-of-vocabulary (OOV) words using `<|unk|>` token
* Implement **Byte Pair Encoding (BPE)** using the `tiktoken` library
* Prepare input-target sequences for model training

---

## 🧾 Dataset

* **Text Source**: `the-verdict.txt`
  A short story used as the raw corpus for tokenizer testing and encoding.

---

## 🧠 Key Concepts

### ✔️ Tokenization

* Splits raw text into manageable pieces called *tokens* (words, punctuation, etc.)
* Handles punctuation and whitespace using `re.split`

### ✔️ Vocabulary Mapping

* Creates a mapping of unique tokens → integer IDs
* Stores both forward (`token → ID`) and reverse (`ID → token`) dictionaries

### ✔️ Special Tokens

* `<|endoftext|>`: End of a document
* `<|unk|>`: Unknown token (not in vocabulary)

### ✔️ Byte Pair Encoding (BPE)

* Encodes text into subword units using GPT-2’s tokenizer via `tiktoken` library
* Efficiently handles out-of-vocabulary terms and rare words

---

## 📦 Requirements

Install the required Python library:

```bash
pip install tiktoken
```

---

## 🚀 How to Use

1. **Basic Tokenizer (SimpleTokenizerV1)**
   Tokenizes input based on whitespace and punctuation, and maps each token to an ID.

2. **Improved Tokenizer (SimpleTokenizerV2)**
   Handles unknown tokens using `<|unk|>` and adds `<|endoftext|>` between text blocks.

3. **Encoding with GPT-2 BPE**
   Use `tiktoken` to tokenize and decode text with subword precision.

4. **Preparing Input-Target Pairs**
   Tokenized text is processed using a sliding window to create sequences for language modeling tasks.

---

## 🧪 Example

```python
text = "Hello, do you like tea? <|endoftext|> In the sunlit terraces"
ids = tokenizer.encode(text)
decoded = tokenizer.decode(ids)
```

**Sample Output:**

```
Token IDs: [15496, 11, 764, 345, 389, 561, 30, 50256, 287, 262, 19369, 23461]
Decoded Text: Hello, do you like tea? In the sunlit terraces
```

---

## 🔍 Notes

* **GPT Tokenizer Quirk**: The GPT tokenizer (`tiktoken`) doesn’t use `<|unk|>` because it breaks all unknown words into subword units automatically.
* **Token ID 50256**: This is reserved for `<|endoftext|>` in GPT-2.
* **Vocabulary Size**: GPT-2 supports 50,257 tokens.

---

## 📈 Future Improvements

* Add training loop to build a character or token-level language model.
* Visualize token frequency or token embeddings.
* Implement a full tokenizer training using Byte-Pair or WordPiece from scratch.

---

* Educational project to understand tokenization and GPT encoding mechanics.


