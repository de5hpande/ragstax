# 📦 ragstax

**🔍 Simplify your Retrieval-Augmented Generation (RAG) pipelines with modular, pluggable chunking strategies.**

---

## 🚀 What is `ragstax`?

`ragstax` is a Python library designed to simplify RAG (Retrieval-Augmented Generation) workflows by providing a plug-and-play interface for various **chunking strategies**.

It allows developers and researchers to experiment with different text splitting methods—without rewriting code.


## 🔧 Installation

```bash
pip install ragstax
```

Or, for local development:

```bash
git clone https://github.com/yourusername/ragstax.git
cd ragstax
pip install -e .
```

---

## 🧠 Why use `ragstax`?

✅ Modular chunking strategies  
✅ Easily extendable via OOP  
✅ Supports token-based, sentence-based, and paragraph-based chunking  
✅ Built for RAG pipelines, vector DBs, and LLM apps  

---

## 📦 Available Chunkers

| Chunker Class           | Description                                   |
|-------------------------|-----------------------------------------------|
| `FixedTokenChunker`     | Splits text using token limits and overlaps   |
| `SentenceChunker`       | Groups fixed number of sentences per chunk    |
| `ParagraphChunker`      | Splits by paragraphs and sub-tokenizes        |

---

## 🛠️ Usage

```python
from ragstax.chunking import FixedTokenChunker

chunker = FixedTokenChunker(max_tokens=1000, overlap=250)
chunks = chunker.chunk("This is your long input text...")
print(chunks)
```

Add new strategies by extending the `BaseChunker` class!

---

## 🧩 Adding Your Own Strategy

Create a new file like `my_custom_chunker.py`:

```python
from ragstax.chunking import BaseChunker

class MyChunker(BaseChunker):
    def chunk(self, text: str):
        return text.split("my_separator")
```

Then register it in `ragstax/chunking/__init__.py`.

---

## 📝 License

MIT License. Free to use, fork, and share!

---

## 👨‍💻 Author

Made with ❤️ by [Rishabh Deshpande](https://github.com/de5hpande)
```