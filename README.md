# AUBot
Implementing a chatbot for university FAQs using a DNN model vs an LSTM model

### Install

This project requires **Python** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org/)
- [matplotlib](http://matplotlib.org/)
- [scikit-learn](http://scikit-learn.org/stable/)

You will also need to have software installed to run and execute a [Jupyter Notebook](http://jupyter.org/install.html).

### Run
- Upload the file on Jupyter Notebooks/ Google colab a long with the dataset.
- Press run all

# Data
The dataset covers 45 different intents (45 json objects) that the chatbot can answer. Most notably, it includes questions related to opening hours of different offices, registration, ordering transcripts, and basic greetings.

_**Each Json Object has the following features:**_
1.  `tag`: The title of the intent.
2. `patterns`:Example/training examples for this intent.
3. `responses`: Output of the chatbot once it identifies this intent.


# Implementation Description

## Assumptions
This model assumes that all inputs it receives are in the form of formal english sentences. It also assumes that the uqestion asked is covered by the Chatbot's knowledgebase.

## Preprocessing
The preprocessing procedure that was followed for the DNN model includes the following:
  1. Tokenization
  2. Stemming
  3. One-Hot Encoding (Bag of Words)

For the LSTM model:
  1. Stemming
  2. Tokenization (using Tokenizer \& pad sequences)
       - Turns the sentence into a vector of numbers instead of 1's and 0's
  
## Models
### LSTM
  - 1 embedding layer
  - 3 LSTM layers of size training.shape[1], 250, and 350 respectively
  - 1 dense layer (size = Number of intent classes) with softmax activation function (for multi-class classification) 
   
### DNN
  - 7 fully connected tflearn layers of sizes ranging from 200 to 600 neurons and relu activation function
  - 1 fully connected tflearn layer with softmax activation function
  
  
## Results
Both models were providing accurate results, however, the DNN model, surprisingly, had a much higher accuracy compared to the LSTM model. The accuracy and loss curves can be found in the report pdf file.
