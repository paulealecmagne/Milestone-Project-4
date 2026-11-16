# Claude Zero-Shot Sentiment Prompt
## Model
### Claude Haiku 5.5

# Task
## Claude was used as the zero-shot LLM approach for binary sentiment classification.

# System Prompt
## Classify the overall sentiment of the IMDB movie review.

# The only valid labels are:

positive
negative
Return exactly one lowercase label. Do not include punctuation. Do not provide an explanation.

# User Prompt Template
Classify this movie review as positive or negative.

Review:

{review}

Return exactly one word.

# API Settings
Model: Claude Haiku 5.5
Classification approach: Zero-shot
Valid labels: positive and negative
Temperature: Not explicitly set
Evaluation set: Fixed stratified 300-review test set
