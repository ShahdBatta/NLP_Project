RESULTS (created by 01_Code/project2.ipynb in the folder results_p2/)

baseline_p1.json                  Project 1 model re-run on the 25,000 test reviews
comparison_table.csv              Project 1 vs Project 2: accuracy, precision, recall, F1
confusion_matrices_p1_vs_p2.png   confusion matrices of Project 1 and the final ensemble
similarity_examples.csv           sentence pairs: Bag of Words vs embedding cosine similarity
semantic_search_examples.csv      top 5 results for the 7 semantic search queries
improved_examples.csv             test reviews that Project 2 fixed (Project 1 wrong)
remaining_errors.csv              test reviews that both systems still get wrong
old_demo_p1_vs_p2.csv             the Project 1 demo reviews, predicted by both systems
final_unseen_examples.csv         the 12 new reviews written by the group, with results
aspect_summary.csv                aspect statistics on 1,000 test reviews
aspect_sentences_sample.csv       aspect sentences found in those 1,000 reviews
aspect_manual_check.csv           20 sentences checked by hand
transformer_test_proba.npy        DistilBERT probabilities for the test set (cache)

Main result (25,000 test reviews):
Version              Representation                            Accuracy  Precision  Recall  F1
Project 1 baseline   BoW + Logistic Regression                 0.8883    0.8913     0.8846  0.8879
Project 2 (a)        MiniLM embeddings + Logistic Regression   0.8129    0.8153     0.8090  0.8122
Project 2 (b)        DistilBERT (SST-2), no training           0.8923    0.9151     0.8648  0.8892
Project 2 (c)        Ensemble: 0.5 x DistilBERT + 0.5 x BoW    0.9148    0.9299     0.8971  0.9132
