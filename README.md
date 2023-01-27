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

##  VANNILA-RNN based TREE MODEL
A RNN based NLP model was developed to pick the sentiment of the comment and was used to label the comment using the six labels

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/RNN/model.png?raw=true" width="700" alt="accessibility text">
</p>

The above image was produced using the plot_model function from tensorflow.
the diagram of the model clearly shows that the data first goes through the text_vectorization layer then the embedding layer and then through the vannila-rnn layer and then it goes through dropouts to introduce some bias and finally all the features go thorugh 6 different sigmoid layers which can produce 6 independent outputs
the above model architecture was achived using the Keras Functional API

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/RNN/image.png?raw=true" width="400" alt="accessibility text">
</p>

```sh
model_rnn.compile(optimizer= tf.keras.optimizers.Adam(learning_rate=1e-5)  ,
                     loss = ['binary_crossentropy' , 'binary_crossentropy' , 'binary_crossentropy' , 
                     'binary_crossentropy' , 'binary_crossentropy' , 'binary_crossentropy'] , metrics='accuracy')
```
```sh
model_rnn.fit(x = x_train , y = [y_train.toxic , y_train.severe_toxic , y_train.obscene 
                                    , y_train.threat , y_train.insult , y_train.identity_hate] ,
                batch_size=32, epochs=15,
                 validation_data=(x_val , [ y_val.toxic , y_val.severe_toxic , y_val.obscene 
                                            , y_val.threat , y_val.insult , y_val.identity_hate]))
```

The average loss of all 6 outputs is 0.0845

The average accuracy from all 6 outputs is 0.967

##  LSTM based TREE MODEL
A LSTM based NLP model was developed to pick the sentiment of the comment and was used to label the comment using the six labels

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/LSTM/model.png?raw=true width="500" alt="accessibility text">
</p>

The above image was produced using the plot_model function from tensorflow.
the diagram of the model clearly shows that the data first goes through the text_vectorization layer then the embedding layer and then through the LSTM layer and then it goes through dropouts to introduce some bias and finally all the features go thorugh 6 different sigmoid layers which can produce 6 independent outputs
the above model architecture was achived using the Keras Functional API

<p align="center">
  <img src="https://github.com/VIKNESH1211/Toxic-comment-classification/blob/main/LSTM/LSTM_LOSS.jpg?raw=true" width="400" alt="accessibility text">
</p>

```sh
model_LSTM.compile(optimizer= tf.keras.optimizers.Adam(learning_rate=1e-5 ) ,   
                     loss = ['binary_crossentropy' , 'binary_crossentropy' , 'binary_crossentropy' , 
                     'binary_crossentropy' , 'binary_crossentropy' , 'binary_crossentropy'] , metrics= ["accuracy"])
```
```sh
model_LSTM.fit(x = x_train , y = [y_train.toxic , y_train.severe_toxic , y_train.obscene 
                                    , y_train.threat , y_train.insult , y_train.identity_hate] ,
                batch_size=512, epochs=30,
                 validation_data=(x_val , [ y_val.toxic , y_val.severe_toxic , y_val.obscene 
                                            , y_val.threat , y_val.insult , y_val.identity_hate]))
```

The average loss of all 6 outputs is 0.078

The average accuracy from all 6 outputs is 0.964

