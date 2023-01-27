# Toxic-comment-classification
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white) ![Keras](https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white) ![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

This repository consists of experimental classification models for text toxicity identification.
_____________

## ABOUT THE DATA SET
The JIG-SAW Toxic Comments data set was used to train the model , The data set has 159571 entries with six classes ore six targets which are toxic, severe_toxic , obscene , threat , insult & identity_hate.

The total number of multi labeled comments were 9865 , 

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/clean/multi.jpg?raw=true" width="700" alt="accessibility text">
</p>

##  VANNILA-RNN
A RNN based NLP model was developed to pick the sentiment of the comment and was used to label the comment using the six labels

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/RNN/model.png?raw=true" width="700" alt="accessibility text">
</p>
