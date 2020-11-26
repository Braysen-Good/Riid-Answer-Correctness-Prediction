# Braysen Goodwin
## RIID Answer Correctness Prediction

This repo contains python notebooks for training models for the [RIID Answer Correctness Prediction](https://www.kaggle.com/c/riiid-test-answer-prediction) Kaggle competition. These notebooks must be ran in the kaggle notebook editor (due to private packages for the competition) and must have access to the following datasets:
  * riiid-test-answer-prediction -> the default data provided by the competition
  * riiid-train-data-multiple-formats -> data in a pickle format for faster reading

This repo has the following models:
  * GBM (Gradient Boost Machine) -> used to predict based off of a single interaction with question data with no tags (subject info). Uses a gradient boost machine from [LightGBM](https://lightgbm.readthedocs.io/en/latest/).
  * Auto-Encoder -> used to predict based off of a single interaction with question data **with** tags (subject info). Uses a set of two supervised auto-encoders to encode the tags (subject info) for each question along with the entire interaction data (base interaction data + question data + encoded tag data) to predict the probability that the user will get the answer correct.
  * RRN -> used to predict based off of a single interaction with question data **with** tags (subject info) and a hidden state generated from the user's previous actions. This allows for the model to predict with the context of the user.