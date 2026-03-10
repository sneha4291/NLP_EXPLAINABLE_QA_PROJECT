Explainable Question Answering using BERT
Project Overview

This project implements an Explainable Question Answering (QA) system using BERT.
The model extracts answers from a given text context and provides explanations by analyzing important tokens that influence the prediction.

In addition to predicting answers, the system also computes performance metrics such as Accuracy, Precision, Recall, and F1-score and generates visualizations for token influence and confidence scores.

The dataset used for this project is the SQuAD, a widely used benchmark for machine reading comprehension.

Problem Statement

Question Answering (QA) systems aim to automatically extract the correct answer to a question from a given text passage.

Instead of searching manually through documents, the model reads the context and predicts the answer span that best matches the question.
Example:

Context
Sachin Tendulkar is a famous Indian cricketer. He is widely regarded as one of the greatest batsmen.

Question
Who is Sachin Tendulkar?

Predicted Output
Answer: cricketer
Confidence Score: 0.37
Model Architecture

The system uses BERT, a transformer-based language model designed for understanding contextual relationships between words.

Input format used by BERT:

[CLS] Question [SEP] Context [SEP]

The model processes this sequence using transformer encoder layers and predicts:

• Start token position
• End token position

These positions determine the answer span inside the context.

Typical BERT configuration:

Layers: 24
Hidden size: 1024
Attention heads: 16
Explainability Approach

To understand the model's predictions, token importance is analyzed.

Steps used:

Tokenize the input text (question + context).

Merge subword tokens.

Assign influence scores to tokens.

Identify the most influential tokens.

Compute a token influence ratio.

Token Influence Ratio is defined as:

Token Influence Ratio = Important Tokens / Total Tokens

Example:

Total Tokens = 82
Important Tokens = 16

Token Influence Ratio = 0.19
Graphs are generated to visualize token importance for each example
Dataset

The project uses the SQuAD (Stanford Question Answering Dataset).

Dataset contents:

• Context paragraph
• Question
• Answer span within the context

Example:

Context
Wikipedia paragraph

Question
What does BERT stand for?

Answer
Bidirectional Encoder Representations from Transformers

Performance Evaluation

Model performance is evaluated using standard machine learning metrics.

Metrics used:

Accuracy
Precision
Recall
F1 Score

Definitions:

Precision
Precision = TP / (TP + FP)

Recall
Recall = TP / (TP + FN)

F1 Score
F1 = 2 × (Precision × Recall) / (Precision + Recall)

Evaluation process:

Select validation examples from the dataset.

Predict answers using the QA model.

Compare predicted answers with true answers.

Compute TP, FP, and FN values.

Calculate Precision, Recall, and F1 Score.

Average the scores across examples.

Example results:

Precision ≈ 0.81
Recall ≈ 0.78
F1 Score ≈ 0.79

Visualizations

The project generates several visual outputs:

• Important token graphs for each example
• Confidence score graph
• Token influence ratio graph

All graphs are saved in the qa_results/ folder
Tools and Technologies

Programming Language
Python

Libraries Used

Transformers
PyTorch
NumPy
Pandas
Matplotlib

Development Environment

Google Colab
References

Research Papers

Attention Is All You Need

BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding

Dataset

SQuAD – Stanford Question Answering Dataset

GitHub Resources

HuggingFace Transformers Repository
