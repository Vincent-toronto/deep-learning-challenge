# Module 21 Neural Network Model

Overview:
In this report, I created a neural network model to determine whether an applicant would be successful if AlphabetSoup funded them. 
To process the data from Excel, we used get_dummies, split a train and test data set, and called the data first before we used Tensorflow to design a neural network, adding different hidden layers to optimize the model.


Results:
I used a CSV file with the attributes below for X:

    APPLICATION_TYPE—Alphabet Soup application type
    AFFILIATION—Affiliated sector of industry
    CLASSIFICATION—Government organization classification
    USE_CASE—Use case for funding
    ORGANIZATION—Organization type
    STATUS—Active status
    INCOME_AMT—Income classification
    SPECIAL_CONSIDERATIONS—Special considerations for application
    ASK_AMT—Funding amount requested

 Y was set as Is Successful or Not successful.
 The variables EIN and NAME were removed from the data set as they were identified.

 Compiling, Training, and Evaluating the Mode:
 
 In the neuro network model, initially, we used 2 hidden layers to train the model to increase accuracy. The first layer had 80 units, and the second had 30. However, with 2 hidden layers, the accuracy was only 0.731. 

_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense (Dense)               (None, 80)                3520      
                                                                 
 dense_1 (Dense)             (None, 30)                2430      
                                                                 
 dense_2 (Dense)             (None, 1)                 31        
                                                                 
=================================================================
Total params: 5981 (23.36 KB)
Trainable params: 5981 (23.36 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________
 
 To increase the accuracy, I tested out using 3 hidden layers and 20 units in the third hidden layer running 100 epochs.
 
 _________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 dense_9 (Dense)             (None, 80)                3520      
                                                                 
 dense_10 (Dense)            (None, 30)                2430      
                                                                 
 dense_11 (Dense)            (None, 20)                620       
                                                                 
 dense_12 (Dense)            (None, 1)                 21        
                                                                 
=================================================================
Total params: 6591 (25.75 KB)
Trainable params: 6591 (25.75 KB)
Non-trainable params: 0 (0.00 Byte)
_________________________________________________________________

However, this was also not able to increase the accuracy to 75% and made it worse to 0.729. 
 
 
 In the second attempt, I stayed with the 2 hidden layers and increased the units to 50 units from 30, and the results to the accuracy were Accuracy: 
 0.7297.

 In the third attempt, I increased the Bin compositions to application_type_data < 1000 and classification_data < 2000 while keeping the hidden layers and units the same as in the second attempt and increased the epochs to q20. In the end, the accuracy was Accuracy: Accuracy: 0.7269, which still did not reach the 75% mark.

 Summary:
  In summary, despite the optimization tests we performed, adding 1 more hidden layer, increasing the units of neurons, binning, and adding more epochs did not increase the accuracy to the 75% mark. Potential next steps to optimize the model could be dropping some columns in the data to see if it will make a bigger difference. 
