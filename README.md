# Bag-of-Words-Project
### Overview

This project explores how to convert textual data into a structured numerical format using the **Bag of Words (BoW)** technique. BoW is a fundamental concept in Natural Language Processing (NLP) where each document is transformed into a vector that represents the frequency of words, **ignoring grammar and word order**.

The implementation is done in two parts:
- A step-by-step manual construction using Python
- A simplified, library-based approach using `scikit-learn`'s `CountVectorizer`

---

### What Is Bag of Words?

Bag of Words takes a text corpus and produces a **document-term matrix**, where:
- Rows represent each document.
- Columns represent each unique word in the corpus.
- Values represent the number of times a word appears in a document.

> Example document list:
```python
[
  "Hello, how are you!",
  "Win money, win from home.",
  "Call me now.",
  "Hello, Call hello you tomorrow?"
]
```

This is converted to a matrix like:

| Document                           | hello | win | money | call | you | ... |
|-----------------------------------|-------|-----|--------|------|-----|-----|
| "Hello, how are you!"             | 1     | 0   | 0      | 0    | 1   |     |
| "Win money, win from home."       | 0     | 2   | 1      | 0    | 0   |     |
| "Call me now."                    | 0     | 0   | 0      | 1    | 0   |     |
| "Hello, Call hello you tomorrow?" | 2     | 0   | 0      | 1    | 1   |     |

---

### 🔨 Implementation Breakdown

#### Part 1: Manual Construction
The process manually replicates what `CountVectorizer` does internally:
1. **Lowercasing:** Standardizes the text to lowercase for uniform comparison.
2. **Punctuation Removal:** Strips punctuation to avoid treating “hello” and “hello!” as different words.
3. **Tokenization:** Splits sentences into individual words (tokens).
4. **Frequency Counting:** Uses `collections.Counter` to build frequency dictionaries for each document.

#### Part 2: Using `scikit-learn`
- **CountVectorizer** handles tokenization, punctuation removal, and vector construction internally.
- The transformed output is converted into a pandas DataFrame for readability.

---

### ⚙️ Dependencies

Install required libraries using:

```bash
pip install pandas scikit-learn
```

---

### 🔍 Notable Parameters in CountVectorizer

- `lowercase=True`: Auto-converts input to lowercase.
- `token_pattern=r'(?u)\b\w\w+\b'`: Default regex that removes punctuation and filters out single characters.
- `stop_words='english'` (optional): Removes common English words (e.g., "the", "and", "is").

---

### 📁 Files

- `BOW_No_Comments.ipynb`
- `README.md`

---
