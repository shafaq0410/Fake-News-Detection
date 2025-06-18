📰 Fake News Detection using LSTM + Fact Checking APIs


A machine learning project that detects fake news using an LSTM-based neural network combined with real-time claim verification via the Google Fact Check API and NewsAPI.

📌 Features
Binary classification model to detect fake vs. real news

Uses pre-trained Word2Vec embeddings with LSTM

Real-time fact-checking integration via:

🟢 Google Fact Check API

📰 NewsAPI

Clean and extensible pipeline for further enhancements

🛠️ Tech Stack
Python

TensorFlow / Keras

Word2Vec (Gensim)

Google Colab

APIs: Google Fact Check, NewsAPI

NLP Preprocessing: NLTK, Regex, preprocess_kgptalkie

📂 Dataset
The model uses the Fake and Real News Dataset from Kaggle:

Fake news: Fake.csv

Real news: True.csv

🔍 How It Works
Data Preprocessing

Merges title and text

Cleans special characters

Tokenizes and pads sequences

Builds Word2Vec embeddings from scratch

Model Training

Embedding layer uses the Word2Vec weights

LSTM for sequence modeling

Sigmoid output for binary classification

API Integration

Verifies user claims using Google Fact Check API

Retrieves supporting articles using NewsAPI

Returns a final verdict: REAL, INCONCLUSIVE

📈 Results
The model achieves ~99.5% accuracy on test data.

yaml
Copy
Edit
              precision    recall  f1-score   support

           0       0.99      1.00      1.00      4694
           1       1.00      0.99      1.00      4286

    accuracy                           1.00      8980
   macro avg       1.00      1.00      1.00      8980
weighted avg       1.00      1.00      1.00      8980


🚀 Example Usage
python
user_claim = "Landmine Victims Deserve More Than Sympathy. It's Time for a UN Fund To Support Them"
analyze_claim(user_claim)
Output:
🗞 Related News Articles Found:
 - Landmine Victims Deserve More Than Sympathy... (Newsweek)
✅ FINAL VERDICT: LIKELY REAL
🔑 Setup Instructions
Clone the repo and open the notebook in Google Colab

Install required libraries:
pip install gensim nltk wordcloud
Replace the following with your keys:

python
GOOGLE_FACT_CHECK_API_KEY = 'YOUR_GOOGLE_FACT_CHECK_API_KEY'
NEWSAPI_KEY = 'YOUR_NEWS_API_KEY'
Run the notebook!

🧠 Future Improvements
UI for end-users to paste claims and receive verdicts

Add support for more languages and sources

Use pre-trained transformer models (like BERT/RoBERTa)

📬 Contact
Made with ❤️ by Shafaq Ali
