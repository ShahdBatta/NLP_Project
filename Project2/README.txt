NLP Project 2: Movie Review Intelligence System (IMDb)
Shahd Batta, Raneem Amer
Supervisor: Dr. Ahmed Fahil
Faculty of Information Technology and Artificial Intelligence

WHAT THE PROJECT DOES
Project 2 continues Project 1 on the same IMDb corpus, task and train/test split.
For any English movie review, the system:
  1. predicts the sentiment (Positive / Negative) with the Project 1 model and
     with the final Project 2 ensemble (DistilBERT + Project 1 model),
  2. finds the aspects the writer commented on (acting, story, music,
     directing, visuals) and the opinion on each one,
  3. retrieves the most similar reviews from the 25,000 training reviews
     using sentence embeddings and cosine similarity.
Final result on the 25,000 test reviews: 91.48% accuracy (Project 1: 88.83%).

FOLDERS
  01_Code/          project2.ipynb, the whole project in one notebook cell
  02_Data/          data source description and the official test split
  03_Results/       metrics, comparison table, confusion matrices, search and prediction outputs
  04_Report/        Project2_Report.pdf
  05_Presentation/  Project2_Presentation.pptx

HOW TO RUN
  1. Open https://colab.research.google.com and upload 01_Code/project2.ipynb
     (File > Upload notebook).
  2. Choose a GPU: Runtime > Change runtime type > T4 GPU > Save.
  3. Run the cell (Runtime > Run all). Allow access to Google Drive when asked.
     The notebook works in the folder MyDrive/NLP_Project.
  4. At the end, the cell prints a public link (https://....gradio.live).
     Open it to use the application. The link stays active while the
     Colab session is running (up to about one week).

  If MyDrive/NLP_Project already contains the Project 1 files
  (data/imdb_train.csv, data/imdb_test.csv, models/*.joblib), they are reused.
  If not, the notebook downloads the official IMDb split from Hugging Face
  and retrains the Project 1 model with the same settings, so it also runs
  from an empty folder.

RUNNING TIME (Colab T4 GPU)
  First run: about 15 minutes (training embeddings ~3 min, DistilBERT on the
  test set ~8 min). Embeddings and DistilBERT predictions are saved in
  MyDrive/NLP_Project, so later runs take a few minutes.
  Without a GPU the notebook still runs, but much more slowly.

PACKAGES
  Installed automatically by the first line of the notebook:
    sentence-transformers, gradio
  Already available in Colab:
    pandas, numpy, scikit-learn, nltk, torch, transformers, datasets,
    matplotlib, joblib
  Pretrained models (downloaded automatically from Hugging Face):
    sentence-transformers/all-MiniLM-L6-v2
    distilbert-base-uncased-finetuned-sst-2-english

USING THE APPLICATION
  Analyze tab: write a review and press "Analyze review".
  Search tab:  describe what you are looking for, choose the number of
               results and press "Search".
  Models tab:  comparison of all models on the test set.
  If the web link does not open, the same analysis can be run inside the
  notebook with: full_demo("your review here")
