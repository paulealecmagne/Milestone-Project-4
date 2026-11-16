# Milestone Project 4
## IMDB Sentiment Analysis Model Comparison

## Project Overview
This project compares three approaches to sentiment analysis using the IMDB movie review dataset:

1. VADER
2. TF-IDF + Multinomial Naive Bayes
3. Claude Haiku 5.5

The goal is to compare the models based on predictive performance, hard-case performance, speed, and cost.

## Dataset
The project uses the IMDB movie review dataset with two sentiment labels:

- Positive
- Negative

A fixed and stratified test set of 300 reviews was used across all three models to maintain a consistent comparison.

### Dataset Files
The full IMDB dataset and training split are not included in this repository due to GitHub file-size limitations.

The repository includes:
- `test_300.csv` - fixed 300-review evaluation set
- `hard_cases.csv` - 30 challenging sentiment examples used for additional evaluation

## Models

### VADER
VADER serves as the rule-based baseline and does not require training.

### TF-IDF + Naive Bayes
The reviews are converted into TF-IDF features and classified using Multinomial Naive Bayes.

### Claude Haiku 5.5
Claude Haiku 5.5 is evaluated using zero-shot classification through the Anthropic API.

## How to Run
```bash

## 1. Install dependencies
pip install -r requirements.txt

## 2. Configure the Claude API
ANTHROPIC_API_KEY=your_api_key_here

## 3. Run the notebooks in order
01_data.ipynb
02_vader.ipynb
03_classic_ml.ipynb
04_llm.ipynb
05_compare.ipynb

## Results
Model	Accuracy	Macro-F1	Hard Cases	Sec / 1K	Cost / 1K
VADER	69.67%	68.84%	70%	2.487	$0
TF-IDF + Naive Bayes	84.00%	84.00%	70%	0.009	$0
Claude Haiku 5.5	92.00%	91.96%	100%	860.997	$0.053

## Key Findings
Claude Haiku 5.5 achieved the strongest overall performance and correctly classified all 30 hard-case examples.
TF-IDF + Naive Bayes provided the best balance between performance, speed, and cost.
VADER provided a useful rule-based baseline but had more difficulty with complex language such as sarcasm and negation.

## Final Recommendation
For large-scale and straightforward sentiment classification, TF-IDF + Naive Bayes provides a practical and efficient option.
For more complex or context-dependent language, Claude provides stronger performance, particularly for sarcasm, negation, contrast, and implicit sentiment.
A hybrid approach could use Naive Bayes for routine classifications and Claude for more difficult or uncertain cases.
