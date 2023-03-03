# Neural_Network_Charity_Analysis
## Overview
From Alphabet Soup’s business team, Beks received a CSV containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization

With your knowledge of machine learning and neural networks, you’ll use the features in the provided dataset to help Beks create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup.
## Results
The category of focus for the model is one called “IS_SUCCESSFUL” as that would be what my model will be predicting. 

Two categorical variables needed to be transformed into bins before encoding them to integer values: Application Type and Classification, so I grouped them into no more than 10 bins. I used OneHotEncoder to convert the categorical data to integers. This involved creating a separate DataFrame and then merging it back into the original then weighed the variables appropriately.

I designed a Deep Learning model with keras Sequential function from TensorFlow. My first Hidden Layer of the model had 80 neurons and the second layer had 40 neurons. For compiling the model, I measured metric loss with binary_crossentropy and used the adam optimizer. I set callback checkpoints to save every 5 epochs when running the model. Over all, I fit and trained the model on 100 epochs.

Results
The initial evaluation of the model resulted in less than 73% accuracy, so I attempted several changes to the model to optimize the accuracy. Test 1: Lowered Neurons, Added Hidden Layer

This did not improve the accuracy.

Test 2: Kept Original Neurons, Added Hidden Layer

This did not improve the accuracy.

Test 3: Change the Compile Optimizer

Several of the keras optimizers significantly reduced the accuracy of the model. The adamax optimizer showed negligible improvement, but the accuracy was still below 73%

Test 4: Change the activations

I attempted many combinations of changing activations with tanh, gelu, swish, sigmoid, and relu, but none of these improved the accuracy of the model.

## Summary
I was not pleased with the performance of any versions of my model. When that is the case in Machine Learning, the issue may be with the data itself. Some concerns may be:

The categories of data given for these charitable donations do not have a correlation with donation success.
The definition of donation success needs to be revisited.
The sample size, although in the tens of thousands, is still insufficient.
With time, study, and reevaluation of data collection, I am confident a more robust model can be developed.
