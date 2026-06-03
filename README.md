# Research Paper Recommender

Paste an ArXiv paper link and instantly find semantically similar research papers — ranked by match score.

## How It Works

1. You paste an ArXiv paper URL
2. The backend fetches the paper abstract via ArXiv API
3. A sentence embedding model converts the abstract into a vector
4. Cosine similarity is computed against 500+ pre-embedded papers
5. Top 5 most similar papers are returned with match scores

## Tech Stack

- **ML**: Sentence Transformers (`all-MiniLM-L6-v2`), Cosine Similarity
- **Backend**: Python, FastAPI, SQLite
- **Frontend**: React, Vite, Tailwind CSS
- **Data**: ArXiv API

## Run Locally

**Backend**
```bash
https://github.com/saurav856/paper_recommender.git
cd paper_recommender/backend
python -m venv venv
venv\Scripts\activate
pip install fastapi uvicorn sentence-transformers scikit-learn requests arxiv
python ingest.py
uvicorn main:app --reload
```

**Frontend**
```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:5173`

## Example

Paste `https://arxiv.org/abs/1706.03762` (Attention Is All You Need) to find similar transformer and language model papers.
