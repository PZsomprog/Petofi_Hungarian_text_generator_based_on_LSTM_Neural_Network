# Petofi_Hungarian_text_generator_based_on_LSTM_Neural_Network
this repository contains a hungarian text generator notebook, an LSTM model and their inputs and "inoutpreparator" notebooks as well.

contributors: Szilard Novoth, Zsombor Pancsics
Associated youtube video: https://www.youtube.com/watch?v=BIR2rPZESKM

The repository contains 3 main functions:
-the I. is the preparation of the input data
-the II. is the usind the word2vec NN model to fit the prepared data to the LSTM network
-the II. is the fine-tuned LSTM network which is able to generate sentences using the prepared and processed input




I (the preparation of the input texts (children novels))

1. The first merges multiple text files (utf-8 txt files) to a single file. This file will be the training, test and validation dataset.
2. The second preprocesses a text file. It expands contractions, removes spaces before new lines, removes excess new line characters. Furthermore it replaces punctuations, breaks sentences into new lines, separates words and build the training, test and validation database.

The usage of the program:

1. Collect al txt file you want to merge into a folder: input_generator(text_merger)/books. (The folder structure under it doesn’t matter)
2.  Run the textmerger.ipynb notebook file. The code merges all files in the book folder. The output file called “combinedalldata” is created with input_generator(text_merger)
3. Copy the output file into the inputs/combinedtext folder
4. The folder inputs/dictionaries contains two text files called "abbreviations" and "punctuations”. These will be read into a python dictionary which will replace the elements of the left column with the elements in the right column if found in the text. (Caution the  = caracter is the separator in the text files, spaces will be also taken into account.)
5. Run textcleaner.ipynb. It creates files to the output folder. These files are the following: prepareddata (the entire tokenized text) and databasetrain,databasetest,databasevalid (the training, test and validation data respectively)



II (wordtovec generates vectors from input text words)

The usage of the program:
As input the w2v notebook waits only 1 file this is the output of the last section. Here it is called: "prepareddata"

III (LSTM generator DeepLearning based model)

The usage of the program:
As input it requires: 
-databasetest
-databasetrain
-databasevalid
-metadata
-prepareddata
-vectors

While running, as output text will be generated
