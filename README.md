# Milestone 1: Text Summarization & Paraphrasing

## Overview
This project is developed as part of a Virtual Internship program. It focuses on two important Natural Language Processing (NLP) tasks:  
1. **Text Summarization** – Condensing large volumes of text into shorter, coherent summaries while preserving key information.  
2. **Text Paraphrasing** – Rewriting sentences with different wording and structure without changing the original meaning.  

Both tasks are implemented using state-of-the-art transformer-based models from Hugging Face.

---

## Objectives
### Text Summarization
Summarization is implemented using the following pretrained models:  
- T5 Base  
- BART Base  
- Pegasus-xsum  

### Text Paraphrasing
Paraphrasing is implemented using the following pretrained models:  
- Pegasus Paraphrase  
- T5 Paraphrase  
- BART Paraphrase  

---

## Dataset
The dataset consists of publicly available literary works from [Project Gutenberg](https://www.gutenberg.org/):

- **The Adventures of Sherlock Holmes** by Arthur Conan Doyle  
  [Download link](https://www.gutenberg.org/files/1661/1661-0.txt)

- **Wuthering Heights** by Emily Brontë  
  [Download link](https://www.gutenberg.org/files/768/768-0.txt)

These texts are loaded programmatically for preprocessing and experimentation:

```python
file_urls = [
    "https://www.gutenberg.org/files/1661/1661-0.txt",  # Sherlock Holmes
    "https://www.gutenberg.org/files/768/768-0.txt"     # Wuthering Heights
]

loaded_texts = load_multiple_text_files(file_urls)

for key, data in loaded_texts.items():
    print(f"{key} ({data['source']}): {len(data['text']):,} characters")
    print(f"Preview: {data['text'][:150]}...")
