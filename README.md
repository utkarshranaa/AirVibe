# AirVibe: Airline Sentiment Analysis

AirVibe is an advanced sentiment analysis project focusing on airline tweets. This project classifies customer tweets directed at major U.S. airlines into **positive**, **negative**, or **neutral** sentiments. It leverages deep learning techniques to analyze the sentiment and provide actionable insights based on social media data.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Models](#models)
  - [Baseline Twitter LSTM Model](#baseline-twitter-lstm-model)
  - [Improved Twitter LSTM Model](#improved-twitter-lstm-model)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Overview

AirVibe examines tweets directed at major U.S. airlines to extract and classify customer sentiment. The project aims to:
- **Categorize Tweets:** Distinguish between positive, negative, and neutral sentiments.
- **Address Data Imbalance:** Handle the inherent class imbalance within the dataset.
- **Compare Architectures:** Evaluate two LSTM-based architectures to optimize sentiment detection performance.

## Dataset

The project utilizes the **Twitter Airline Sentiment Dataset**, which includes:
- **Tweets**: Messages directed at major U.S. airlines.
- **Sentiment Labels**: Each tweet is labeled as **positive**, **negative**, or **neutral**.
- **Class Imbalance**: Negative tweets are the most frequent.
- **Dataset Statistics**: 
  - Average tweet length: Approximately 21 words (103.82 characters)
  - Vocabulary size: 17,383 unique words

*Preprocessing Steps Include:*
- Removal of airline names to prevent bias.
- Tokenization of tweets.
- Padding sequences for uniform input length.

## Models

### Baseline Twitter LSTM Model

- **Embedding Layer**: Utilizes randomly initialized word embeddings.
- **Architecture**: Three-layer stacked LSTM with a hidden dimension of 256.
- **Regularization**: Includes a dropout layer (30%) to mitigate overfitting.
- **Output**: A fully connected softmax layer for sentiment classification.

### Improved Twitter LSTM Model

- **Embedding Layer**: Employs pre-trained GloVe embeddings (100-dimensional) for richer representations.
- **Architecture**: Incorporates a Bidirectional LSTM with three stacked layers, capturing context from both past and future inputs.
- **Regularization**: Maintains a dropout layer (30%) and a fully connected softmax output layer.
- **Enhancements**: Although this model shows a slight drop in certain metrics, it improves generalization and semantic understanding of the tweets.

## Results

**Baseline Model Performance:**
- **Test Accuracy:** 92.28%
- **Test F1-Score:** 92.24%
- **Observation:** Occasional misclassification of neutral tweets, often as either positive or negative.

**Improved Model Performance:**
- **Test Accuracy:** 85.84%
- **Test F1-Score:** 85.91%
- **Observation:** Despite a minor drop in overall accuracy, the model exhibits better generalization and deeper semantic understanding.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Acknowledgements

- Appreciation goes to the creators of the **Twitter Airline Sentiment Dataset**.
- Special thanks to the deep learning and natural language processing communities for their insights and research that inspired this project.
