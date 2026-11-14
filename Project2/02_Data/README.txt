DATA SOURCE

Corpus: Stanford Large Movie Review Dataset (IMDb), the same corpus as Project 1.
  A. L. Maas, R. E. Daly, P. T. Pham, D. Huang, A. Y. Ng and C. Potts,
  "Learning word vectors for sentiment analysis," ACL 2011.
  Original page: https://ai.stanford.edu/~amaas/data/sentiment/
  Loaded from Hugging Face: https://huggingface.co/datasets/stanfordnlp/imdb

Size: 50,000 English movie reviews with binary labels
  (0 = Negative, 1 = Positive).
Split: the official split, used without changes.
  Train: 25,000 reviews (12,500 positive, 12,500 negative)
  Test:  25,000 reviews (12,500 positive, 12,500 negative)

FILE IN THIS FOLDER
  imdb_test.csv   the official test split used for every result in the project
                  columns: id (test_0 ... test_24999), text, label

The training file (imdb_train.csv, same format with ids train_0 ... train_24999)
is not included because of its size. To reproduce both files exactly:

  from datasets import load_dataset
  ds = load_dataset("stanfordnlp/imdb")
  train_df, test_df = ds["train"].to_pandas(), ds["test"].to_pandas()
  train_df.insert(0, "id", [f"train_{i}" for i in range(len(train_df))])
  test_df.insert(0, "id", [f"test_{i}" for i in range(len(test_df))])

The notebook does this automatically when the files are not found.

VALIDATION SET
Model settings were chosen on a validation set made of 10% of the training
data (stratified split, random_state = 42). The test set was used only for
the final evaluation.
