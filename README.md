# 🔎 Traditional Search vs Vector Search (Semantic Search Demo)

This project demonstrates the difference between:

- **Traditional keyword-based search**
- **Semantic vector search using embeddings**

It shows how traditional search fails to understand meaning, while vector search successfully retrieves semantically similar results.

---

# 📌 Problem Statement

Given the following documents:

```python
documents = [
    "Affordable vehicle for students",
    "Best gaming laptop",
    "Budget friendly smartphone"
]
```

We search for:

```
cheap car
```

Even though:
- cheap ≈ affordable  
- car ≈ vehicle  

Traditional search fails to retrieve the correct result.

---

# 🧾 1️⃣ Traditional Search (Keyword Matching)

Traditional search works by:

- Splitting the query into words
- Checking if those exact words exist in the document
- Returning matching documents

### ❌ Limitation

Since `"cheap"` and `"car"` do not literally appear in:

```
"Affordable vehicle for students"
```

The traditional search returns **no result**.

This demonstrates the weakness of lexical keyword-based search systems.

---

# 🧠 2️⃣ Vector Search (Semantic Search)

Vector search works differently:

1. Convert documents into **embeddings**
2. Convert the query into an embedding
3. Compare embeddings using similarity search
4. Return the most semantically similar document

---

## 📦 Embedding Model Used

```
all-MiniLM-L6-v2
```

From the **SentenceTransformers** library.

This model converts text into dense numerical vectors that capture semantic meaning.

---

## ⚡ Vector Indexing with FAISS

We use **FAISS** to:

- Store embeddings
- Perform nearest neighbor search
- Retrieve the most similar document efficiently

---

# ⚙️ Installation

```bash
pip install sentence-transformers faiss-cpu numpy
```

If using GPU:

```bash
pip install faiss-gpu
```

---

# ▶️ How to Run

Simply run the Python script:

```bash
python main.py
```

---

# 🚀 Output Comparison

Query:

```
cheap car
```

Results:

| Method              | Output                                  |
|---------------------|------------------------------------------|
| Traditional Search  | ❌ No result                            |
| Vector Search       | ✅ "Affordable vehicle for students"    |

---

# 🎯 Key Takeaway

Traditional search:
- Relies on exact word matching
- Cannot understand synonyms
- Fails on paraphrased queries

Vector search:
- Understands semantic meaning
- Handles synonyms and context
- Produces more accurate results

This is why modern AI-powered search systems rely on embeddings and similarity search instead of only keyword-based ranking.

---

# 📚 Tech Stack

- Python
- SentenceTransformers
- FAISS
- NumPy

---

# 📌 Future Improvements

- Add hybrid search (BM25 + Vector)
- Add larger dataset
- Add top-K retrieval instead of k=1
- Add evaluation metrics

---

⭐ If you found this useful, feel free to star the repository!
