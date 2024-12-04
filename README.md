# BERT_Classification

Model Comparison
Model	Precision	Recall	F1 Score
Naive Bayes by Hand	1.00	0.69	0.82
Tf-idf by Hand	1.00	0.88	0.93
Scikit-learn Naive Bayes	1.00	0.66	0.79
Scikit-learn Tf-idf	1.00	0.76	0.87
Word-level TF-IDF	1.00	0.76	0.87
Character-level TF-IDF	1.00	0.82	0.90
Finetuned BERT	0.95	0.90	0.92

### 1.1 Naive Bayes by Hand
The high precision indicates that the model classifies spam messages very accurately, but the low recall shows it misses a significant number of spam messages. This is typical for Naive Bayes when token probabilities fail to capture nuances in text data.

### 1.2 Tf-idf by Hand
Adding the Tf-idf representation improved recall significantly compared to Naive Bayes by hand, as Tf-idf better captures the importance of terms across documents. The precision remains perfect.

### 1.3 Scikit-learn Naive Bayes
Performance is similar to Naive Bayes by hand, with high precision but lower recall. Scikit-learn's implementation might include some optimizations, but the general trends remain consistent.

### 1.4 Scikit-learn Tf-idf
Compared to Naive Bayes in Scikit-learn, the Tf-idf representation improves recall and F1 scores. It demonstrates the ability of Tf-idf to focus on important words and reduce noise.

### 1.5 Experiment with Tf-idf Parameters
Word-level TF-IDF: Precision: 1.0, Recall: 0.76, F1: 0.87
Character-level TF-IDF: Precision: 1.0, Recall: 0.82, F1: 0.90
Explanation:
•	The word-level analyzer creates features based on complete words. It performs well when words alone carry significant meaning.
•	The character-level analyzer generates features based on sequences of characters (n-grams). It captures subword patterns and can handle spelling variations or creative abbreviations, improving recall and F1 scores in noisy data like SMS.
•	Effect on Scores: The character-level TF-IDF improves recall and F1 scores compared to word-level TF-IDF, as it captures more granular features.

### 1.6 Finetuned BERT
BERT achieves the best overall performance with balanced precision and recall. It captures the contextual meaning of words and phrases, making it highly effective for text classification tasks. The slight drop in precision (compared to Tf-idf) is offset by a significant boost in recall and F1 score, indicating better overall robustness.

### 1.7 Summary
Character-level TF-IDF performs better than word-level TF-IDF, especially for noisy data like SMS, due to its ability to capture subword features.
BERT demonstrates the highest F1 score, reflecting its superior ability to understand context and nuances in text.
Naive Bayes (both manual and Scikit-learn) struggles with recall, which makes it less robust for detecting spam compared to other methods.
Tf-idf (by hand and Scikit-learn) bridges the gap between Naive Bayes and BERT, providing high precision and significantly improved recall.


