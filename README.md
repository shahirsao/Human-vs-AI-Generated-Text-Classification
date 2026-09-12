# Overview
This project explores classification between human written and AI generated text under different classification scenarios, using a self generated dataset.

This includes classifying a single text between AI or Human written, as well as classifying a pair of answers in response to the same question as Human or AI, given that each pair consists of one of each class.

This project also evaluates performance of Human vs AI classification between generative AI models by training with responses given by one generative AI model, but evaluating using responses given by another.

# Techniques Used
- Logistic Regression on TF/IDF Scores
- Logistic Regression on 300-dimensional FastText embeddings
- A BERT transformer fine-tuned on the training data

# Results
![results](https://github.com/shahirsao/Human-vs-AI-Generated-Text-Classification/blob/main/results.PNG)
The performance of all classification methods was strong, with BERT showing the best results in all cases. As hypothesised the pairwise learning task showed extremely good performance with all approaches achieving above 99% accuracy. Some performance drop was seen when training on Gemini responses but evaluating using Claude responses. However the models seemed to generalise between generative AI models fairly well, with the lowest accuracy shown in cross-model evaluation not falling below 88%.

As an interesting note, the TF/IDF scores showed that the most human indicative word was "you" and the most AI indicative word was "and".

# Dataset
The data used was generated using the OpenRouter API within Python, with the [ELI5 dataset from sentence-transformers on Hugging Face](https://huggingface.co/datasets/sentence-transformers/eli5) being used as a basis. The dataset has been included in the repo and has also been made available on Hugging Face [here](https://huggingface.co/datasets/shahirsao/ELI5-Human-and-AI-Answers) with some additional notes.

# Running Instructions
The notebook should be run by first running `Imports`, then running the cells top to bottom from `Data Preparation`. The notebook is written with the intention that the dataset files are placed within the root of the user's Google Drive. Note that the `AI Response Generation` cell will not run without an OpenRouter API key being assigned to the `API_KEY` value at the top of the cell. 
