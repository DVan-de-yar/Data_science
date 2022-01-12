# Sentiment analysis with Recurrent Neural Network
Imported packages for loading  and processing the dataset, displaying visualizations and creating trainable models.

Used a negative and positive book reviews data sets to train a recurrent neural network model , to predict whether a review was 'good' or 'bad', depending on the language used in the review title. 

Labels of 0 and 1 where assigned to the reviews. Then calculated the mean length of a review , the standardard deviation, plotted a box plot to display this data and calculated the total number of unique words in the reviews.

Tokenized array that had all the reviews to give numeric values in place of all the unique words in the datasset (range of 1 - (number of unique words + 1)).

Preprocess the array by using the keras padding function, which takes the now tokenized array, a max length(maxlen) value which is the rounded mean value calculated earlier and returns an array with the shape length of dataset : max length. Use zero to pad values if the review is less than max length and removing values from lists with more than max length values.

Split the data into train and test data using the sklearn train_test_split function. Split the array with the train dataset being 80% of the data and the remainder will be the test data. The labels that where created earlier are the y_train and y_test values. Values are shuffled to diversify the data the model is trained on.

Created a asess_model function that uses sklearn.metrics functions to makes a prediction for the test set given the model and reports the precision, recall and f1 score as well as printing the confusion matrix.

Created a model , add first layer which is an embedding layer used for the classification of the words in the data set. Then used spatialDropout and BatchNormalization to allow the model to have greater variability when training the model. Added a RNN layer for the neural network to train the model with a relu ativation function and dense layer with a softmax activation function for the output.

Fit the test data to the model and run for 5 epochs with a batch size of 10. Assign the model fitting to a object so that the .history function can be used on the objectv to return the loss and accuracy for the model.

Used the assess_function to return values for the models performance at out_dim 10,25,50 and 100(out_dim is a argument of the embbedding layer, which changes the total number of parameters for the models. By comparing the precision, recall, f1 score and confusion matrix of each out_dim it was determined that 100 was the best out_dim value.

Created a function to plot accuracy and loss of both train and test data. Then displayed these visualizations.

Finally passed a new array of reviews to the model after they were tokenized and preprocessed to see how well the model would predict the review value.

