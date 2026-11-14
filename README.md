# IMDb Sentiment Analysis

NLP Mini Project 1 (Phase 1) · Corpus Option 3: Stanford Large Movie Review Dataset

Classify a movie review as **Positive** or **Negative** with a classical NLP pipeline:
preprocessing, corpus statistics, N-gram analysis, a trigram language model,
Bag of Words, and Logistic Regression / Multinomial Naive Bayes.

## Results (official IMDb test set, 25,000 unseen reviews)

| Model | Accuracy | Precision | Recall | F1 |
|---|---|---|---|---|
| Logistic Regression (unigrams + bigrams) | 0.8883 | 0.8913 | 0.8846 | 0.8879 |
| Multinomial Naive Bayes (unigrams + bigrams) | 0.8564 | 0.8841 | 0.8203 | 0.8510 |

## Files

| File | Content |
|---|---|
| `IMDb_Sentiment_Analysis.ipynb` | Full code with saved outputs |
| `Report.pdf` | Project report |
| `results/` | Tables and figures used in the report |
| `data/imdb_test.zip` | Frozen test set (25,000 reviews, ids `test_0` to `test_24999`) |

## How to run

1. Open the notebook in Google Colab.
2. Runtime → Run all. The notebook downloads the dataset from Hugging Face
   (`stanfordnlp/imdb`) and recreates the same train/test split.
3. For the live demo, remove the `#` before the `input()` line at the end.

**Presentation:** https://imdp-nlp.netlify.app

## Project 2: Movie Review Intelligence System

Phase 2 extends the Project 1 pipeline with modern NLP on the same IMDb data and test split:
sentence embeddings, semantic search, a pretrained DistilBERT model, an ensemble with the
Project 1 model, aspect-based sentiment, and a Gradio web app.

| Model | Accuracy | F1 |
|---|---|---|
| Project 1: BoW + Logistic Regression | 88.83% | 0.888 |
| Project 2: Ensemble (DistilBERT + BoW) | **91.48%** | **0.913** |

Everything is in the [`Project2`](Project2) folder. See [`Project2/README.txt`](Project2/README.txt) for how to run it.