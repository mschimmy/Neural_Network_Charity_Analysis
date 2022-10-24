# Neural Network Charity Analysis

## Overview of the Analysis

The client, Alphabet Soup, is a nonprofit foundation that uses donations to invest in organizations that protect the environment, improve people's well-being, and unify the world. The client requests a machine learning model that can analyze the impact of each donation and vet potential recipients to ensure that the foundation's money is being used effectively. The charity CSV dataset used in this analysis was provided by the client and contains features of more than 34,000 organizations that have received funding from Alphabet Soup and the success of each campaign.

### Purpose of the Analysis

The purpose of this analysis is to create a binary classifier that is capable of predicting whether applicants will be successful if funded by the client. A deep-learning neural network model was developed and trained using Python's TensorFlow library to evaluate data input and produce precise decision-making results for the client. The process and results of the deep learning neural network are discussed below.

## Process & Results

### Data Preprocessing

- What variable is considered the target for your model?
  - The target variable for the model is the "IS_SUCCESSFUL" column.
- What variables are considered to be the features of your model?
  - Variables considered features of the model include the encoded variables for the following columns: "APPLICATION", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT
  ![Charity Data Features and Target Variables](https://github.com/mschimmy/Neural_Network_Charity_Analysis/blob/main/Resources/Images/charity_features_%26_target.png)
  <sub>Charity Data Features and Target Variables</sub>

- What variable(s) are neither targets nor features, and should be removed from the input data?
  - Two variables, "EIN" and "NAME" were neither targets nor features and were removed from the dataset before training the model.
  ![Charity Data Dropped Variables](https://github.com/mschimmy/Neural_Network_Charity_Analysis/blob/main/Resources/Images/charity_dropped_variables.png)
  <sub>Charity Data Dropped Variables</sub>

### Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network?
  - In the standard neural network, there were two hidden layers, the first with 80 neurons and the second with 30, and the activation function for the two hidden layers was the "relu" function. The output layer uses the "sigmoid" function.
  - In the optimized neural network, there were three hidden layers: the first with 80 neurons, the second with 50 neurons, and the third with 30 neurons. The activation function for the three hidden layers was the "tanh" function. The output layer activation function was the "sigmoid" function.
  ![Standard Neural Network Setup](https://github.com/mschimmy/Neural_Network_Charity_Analysis/blob/main/Resources/Images/standard_neural_network_setup.png)
  <sub>Standard Neural Network Setup</sub>

  ![Optimized Neural Network Setup](https://github.com/mschimmy/Neural_Network_Charity_Analysis/blob/main/Resources/Images/optimized_neural_network_setup.png)
  <sub>Optimized Neural Network Setup</sub>

- Were you able to achieve the target model performance?
  - The optimized neural network model was not able to achieve the target model performance of 75%. The standard and optimized neural networks achieved an accuracy score of 72.595% and 73.038% respectively.
- What steps did you take to try and increase model performance?
  - In an attempt to increase the standard model's performance, a third hidden layer was added to the neural network, more neurons were added to each of the hidden layers, and a different activation function was used in the hidden layers. The number of epochs used to fit the model was also increased from 100 to 150. The number was not significantly increased to avoid model overfitting.
  ![Optimized Neural Network Model Training](https://github.com/mschimmy/Neural_Network_Charity_Analysis/blob/main/Resources/Images/optimized_neural_network_training.png)
  <sub>Optimized Neural Network Model Training</sub>

## Summary

The standard neural network model has an accuracy score of 72.595%. After steps were taken to optimize the model (discussed and shown above) the model's performance increased to 73.038%. Neither model was able to achieve the target model performance of 75%. Generally, if a neural network model does not meet performance expectations, it's usually due to one of two causes: inadequate or inappropriate model design for a given dataset, or insufficient or ineffective training data.  The most straightforward means of improving neural performance is tweaking the model design and parameters using the characteristics of the input data to determine what parameters should be changed. This can be accomplished by doing the following:
- check out the input dataset
- add more neurons to a hidden layer
- add additional hidden layers
- use a different activation function for the hidden layers
- add additional epochs to the training regimen

Several different models could be used to solve this classification problem, one recommendation would be to use a simple logistic regression model to classify applicants as either being successful or not. In a logistic regression model, a combination of input variables is used to mathematically determine the input's probability of belonging to one of two groups; if the probability is above a predetermined cutoff, the sample is assigned to the first group, otherwise, it's assigned to the second. A logistic regression model would be similar to creating a basic neural network that uses the sigmoid activation function, as both models use the sigmoid curve to produce the probability (between 0 and 1) of the input data belonging to the first group.
