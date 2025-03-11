**Benchmarking Text Classification Algorithms with Feature Extractors**

## Introduction
The goal of this project is to benchmark different text classification algorithms using various feature extraction techniques on the 20 Newsgroups dataset. The models evaluated include:

- Multinomial Naïve Bayes (MNB)
- Logistic Regression
- Support Vector Machine (SVM)
- Decision Trees

Feature extractors used:
- CountVectorizer
- TF-IDFVectorizer
- Word2Vec
- Doc2Vec

## Approach
1. **Data Loading**
   - The dataset is fetched using `fetch_20newsgroups` from `sklearn.datasets`.
   - Preprocessing includes removing headers, footers, and quotes.

2. **Feature Extraction**
   - **CountVectorizer**: Converts text into a sparse matrix of token counts.
   - **TF-IDFVectorizer**: Converts text into term frequency-inverse document frequency (TF-IDF) features.
   - **Word2Vec**: Generates word embeddings using pre-trained models or training on our dataset.
   - **Doc2Vec**: Creates document-level embeddings.

3. **Model Training & Evaluation**
   - Models are trained using each feature extraction technique.
   - Performance is evaluated using accuracy, precision, recall, and F1-score.

4. **Challenges & Solutions**
   - **MNB with Word2Vec & Doc2Vec**: MNB does not support negative values present in Word2Vec/Doc2Vec outputs. **Solution:** Used absolute values or replaced MNB for these cases.
   - **Memory Usage**: Doc2Vec requires significant memory and computational power. **Solution:** Used dimensionality reduction techniques.

5. **Results & Analysis**
   - A comparative table showing the performance of each model with different feature extractors is generated.
   - The best performing combination is identified based on accuracy and F1-score.

## Results
This benchmarking study helps in understanding the effectiveness of different algorithms and feature extraction techniques for text classification tasks. The findings indicate that TF-IDF with SVM and Logistic Regression provide the best results, whereas CountVectorizer works well with MNB.

