# Overview
This project explores classification between human written and AI generated text under different classification scenarios, using a self generated dataset.

This includes classifying a single text between AI or Human written, as well as classifying a pair of answers in response to the same question as Human or AI, given that each pair consists of one of each class.

This project also evaluates performance of Human vs AI classification between generative AI models by training with responses given by one generative AI model, but evaluating using responses given by another.

# Techniques Used
- Logistic Regression on TF/IDF Scores
- Logistic Regression on 300-dimensional FastText embeddings
- A BERT transformer fine-tuned on the training data

