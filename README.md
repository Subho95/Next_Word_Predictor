# Next_Word_Predictor

The popular book “Alice’s Adventures in Wonderland” written by Lewis Caroll has been used as training dataset for this project. The e-book can be downloaded from http://www.gutenberg.org/files/11/11-0.txt in Plain Text UTF-8 format. The downloaded book has been stored in the root directory with the name ‘wonderland.txt’. 

Preprocessing has been done on the collected text. First we transform it into lower cases and form a dictionary with the characters. We also eliminated some poor characters and symbols. Then we create an input window of 100 characters (SEQ_LENGTH = 100) and shift the window one character at a time until we reach the end of the book. 

The model is given an input of 100 character sequences and it outputs the respective probabilities with which a character can succeed the input sequence. The model consists of 3 hidden layers. The first two hidden layers consist of 256 LSTM cells, and the second layer is fully connected to the third layer. The number of neurons in the third layer is same as the number of unique characters in the training set (the vocabulary of the training set). The neurons in the third layer, use softmax activation so as to convert their outputs into respective probabilities. The loss used is Categorical cross entropy and the optimizer used is Adam.

1. sys
2. tensorflow_version 1.x
3. matplotlib inline
4. pickle
5. numpy
6. os 
7. keras
