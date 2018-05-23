# Neural-Network-Project
Contains the code used for the Neural Network course project which involves video classification.

The project involved creating a model for video classification into various human actions like golf swing,running,walking etc.
The data-set was almost similar to the UCF Sports Action Data Set which can be found here: http://crcv.ucf.edu/data/UCF_Sports_Action.php

We used a simple CNN+RNN based approach. The model can be broken down as follows:
1) Train a CNN on the various categories of videos by using each frame of each video as a data point
2) Remove the fully connected layers from the CNN model and use the features from the last layers.
3) Use these features for an entire video as one single input to the RNN. Eg: ( if video has 50 frames, use 50*1024 sized input to the RNN where 1024 is the size of the last layer of CNN ).

NOTE: The dataset is not included but its structure is as follows. The path is "NNFL_Training_Set/NNFL_Training_Set/" and here you place the the videos in different folder for each category.

There are 4 codes. The task of each is as follows: ( should be run in the same order )
1) NN_Project: Reads videos as data and creates a new dataset with each folder corresponding to one category and the video being broken into frames. This data is further broken into a train and test dataset and it is made sure that the respective proportion of categories in train and test data is same.

2) Train_CNN: Uses the above created datasets to train a CNN based model and saves it.

3) GetRNNData: Loads the saved CNN model,pops the fully connected layers and again passes each video through the network to get the data in the format as required by the RNN (as described above).

4) Train_RNN: Uses the data created above to train a simple RNN model with one LSTM layer and prints the final accuracy on validation data.

