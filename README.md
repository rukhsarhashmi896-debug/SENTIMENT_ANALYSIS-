Sentiment Analysis using NLP and Machine Learning
A machine learning project that classifies text comments and reviews as
Positive or Negative using Natural Language Processing (NLP),
TF-IDF feature extraction, and Logistic Regression.
Project Overview
This project uses the Sentiment140 dataset to train a binary
sentiment classification model. It includes data cleaning, exploratory
analysis, model training, evaluation, error inspection, and a function
for predicting the sentiment of new text.
Technologies and Libraries
- Python
- Pandas and NumPy
- Regular Expressions (re)
- Matplotlib and Seaborn
- Scikit-learn
- KaggleHub
- Jupyter Notebook / Google Colab
Dataset
- Dataset:
  Sentiment140
- Source: Kaggle (kazanova/sentiment140)
- Labels used: 0 → Negative, 4 → Positive
The notebook downloads the dataset using KaggleHub, locates the CSV
file, and loads the text and sentiment columns for processing.
Project Workflow
1. Install and import the required libraries.
2. Download and load the Sentiment140 dataset.
3. Select the text and sentiment columns.
4. Map numeric labels to Positive and Negative.
5. Check and remove missing values and duplicate comments.
6. Explore the sentiment distribution.
7. Clean text by converting it to lowercase, removing URLs and
   usernames, retaining hashtag words, expanding common contractions,
   and removing unwanted characters.
8. Split the data into training and testing sets (80% / 20%) using
   stratified sampling.
9. Convert text into numerical features using TF-IDF.
10. Train a Logistic Regression classifier.
11. Evaluate predictions using accuracy, a confusion matrix, and a
    classification report.
12. Inspect incorrectly classified comments.
13. Test the prediction function with sample reviews and custom user
    input.
Model Details
TF-IDF Vectorizer
The notebook uses the following configuration:
- max_features=50000
- ngram_range=(1, 3) --- unigrams, bigrams, and trigrams
- min_df=2
- max_df=0.95
- sublinear_tf=True
- stop_words=None
- strip_accents="unicode"
Logistic Regression
The classifier is configured with:
- C=2.0
- max_iter=2000
- solver="lbfgs"
- class_weight=None
- random_state=42
Evaluation
The notebook evaluates the model using:
- Accuracy score
- Confusion matrix
- Classification report (precision, recall, and F1-score)
- Inspection of negative comments incorrectly predicted as positive
Note: Actual evaluation scores depend on the dataset version and
execution environment. Run the notebook to generate the current results;
no fixed accuracy is claimed here.
How to Run
Option 1: Google Colab
1. Download or clone this repository.
2. Open Sa_NLP1.ipynb in Google
   Colab.
3. Run the notebook cells from top to bottom.
4. Allow KaggleHub to download the Sentiment140 dataset.
5. Use the final input cell to enter a comment and view its predicted
   sentiment and confidence.
Option 2: Jupyter Notebook
1. Clone the repository:
   git clone https://github.com/<your-username>/<your-repository-name>.git
   cd <your-repository-name>
2. Install the dependencies:
   pip install pandas numpy matplotlib seaborn scikit-learn kagglehub jupyter
3. Launch Jupyter:
   jupyter notebook
4. Open Sa_NLP1.ipynb and run all cells.
Example
The notebook includes positive and negative review examples, such as:
- "This product is absolutely terrible."
- "I hate this product and would never recommend it."
- "Amazing quality and excellent customer service."
- "I really love this product."
The model returns a sentiment label and a confidence value derived from
its predicted class probabilities. Confidence is not a guarantee that a
prediction is correct.
Repository Structure
.
├── Sa_NLP1.ipynb
└── README.md
The dataset is downloaded at runtime and is not included in this
repository.
Limitations
- The model predicts only two classes: Positive and Negative.
- Performance depends on the training data, text preprocessing, and
  vocabulary learned by TF-IDF.
- Sarcasm, mixed opinions, context-dependent language, spelling
  variations, and domain-specific expressions may be misclassified.
- The confidence value should not be interpreted as a guaranteed
  probability of correctness.
Future Improvements
- Add more diverse and domain-specific labeled data.
- Experiment with class weighting and hyperparameter tuning.
- Compare Logistic Regression with Linear SVM and other classifiers.
- Analyze errors such as sarcasm, negation, and mixed sentiment.
- Evaluate performance on a separate real-world review dataset.
Author
Your Name

If you found this project useful, consider giving the repository a ⭐ on
GitHub.
