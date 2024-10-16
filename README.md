# deep-learning-challenge

## OVERVIEW OF PROJECT
The purpose of this project was to develop a machine learning model for Alaphabet Soup, (a nonprofit foundation), that can predict 
if applicants that apply for funding will be succesful if funded by Alphabet Soup.Such analysis assist the foundation in selecting the best applicant for funding, and ensuring that funds are used to ensure the most benefit. 

## Dataset Overview:
The data provided was in a CSV format, contained 34,000 organisations. 

## RESULTS

## Data Preprocessing

The target variable for this model is,  "IS_SUCCESSFUL", this is the binary (0 or 1) variable that indicates if funding was used effectively by the applicant (the organisation).

The features of the model included in metadata is:

EIN and NAME—Identification columns
APPLICATION_TYPE—Alphabet Soup application type
AFFILIATION—Affiliated sector of industry
CLASSIFICATION—Government organisation classification
USE_CASE—Use case for funding
ORGANIZATION—Organisation type
STATUS—Active status
INCOME_AMT—Income classification
SPECIAL_CONSIDERATIONS—Special considerations for application
ASK_AMT—Funding amount requested
IS_SUCCESSFUL—Was the money used effectively

It should be noted that the EIN and NAME identification columns were removed from the data set. These variables were removed as the values included did not provide any insights to the data.  Each EIN and Name awas attached to an Application Type and other Classifications, and thus, they were not needed to identify the organisations or used for analysis. There are a total of 49 features used in the models. 

## Compiling, Training and Evaluating the Model 

I conducted four deep nerual network training models in an attempt to reach 75% accuracy in predicting success of funding for applicants.  In all models I adopted the following: 

Activation function: The ReLU activation function is used in the hidden layers to introduce non-linearity.
-Output layer: The outer layer utilised the Sigmoid activation function with a single (1) neuron.
-Neurons: In all models I reduced the number of neurons with each hidden layer.
-The model saved weights every 5 epoch, this is to monitor the training progress. 

## Model 1:Starter Code
First hidden layer: The first hidden layer had 50 neurons.
Second layer: The second layer had 25 neurons.
Epochs:100
Batch: 320

Rationale: This model was used to create a baseline and uses the general prinicples for this type of maachine learning model. The 

## Evaluation of the model:

The accuracy of the model was:
215/215 - 0s - 2ms/step - accuracy: 0.7261 - loss: 0.5974
Loss: 0.5974100232124329, Accuracy: 0.7260932922363281

Overall this model had 72.61% accuracy with a loss of 59.00%. This model correctly predicted the outcome of funding being used successfully or not 72.61 % of the time. 59% loss suggest that the model is still learning and may need some adjustments to improve the accuracy.

**************************************************************************************************************

## Model 2:Starter Code 1
First hidden layer: The first hidden layer had 60 neurons.
Second layer: The second layer had 35 neurons.
Third layer: The third layer had 15 neurons. 
Epochs:100
Batch: 320

Rationale:
In this model I added a third layer, the rationale for adding an additional layer is to ehance the model to learn more complex patterns of the data. The first model provided a good baseline,however, the aim is to to reach 75% accuracy, hence the addition of a layer and changes to the neurons. 

## Evaluation of the model:
The accuracy of the model was:
215/215 - 1s - 3ms/step - accuracy: 0.7284 - loss: 0.5595
Loss: 0.5595238208770752, Accuracy: 0.7284256815910339

Overall this model had 72.84% accuracy with a loss of 55.95%, meaning it predicted the outcome correclty 72.84% of the time. This model is a slight improvement from the first learning model (+0.23%), which suggests that adding an additional layer is allowing some of the underlying patterns of the data is being picked up as the depth has increased. 

*********************************************************************************************************************

## Model 3: Starter Code 2

First hidden layer: The first hidden layer had 40 neurons.
Second layer: The second layer had 30 neurons.
Third layer: The third layer had 20neurons. 
Fourth layer: The fourth layer had 10 neurons
Epochs: 150
Batch: 128

Rationale: In this model I added an additional layer in an attempt to enhance the ability to read more complex data patterns and enhance the accuracy.  

## Evaluation of this model:
215/215 - 0s - 2ms/step - accuracy: 0.7278 - loss: 0.5647
Loss: 0.5646637678146362, Accuracy: 0.7278425693511963

Overall this model had 72.78% accuracy with a loss of 56.47%. As can be seen, adding an additional layer, reduced the accuracy, in this case the assumption could be made that there is some "overfitting" occuring, that the model was not capturing the underlying patterns.

************************************************************************************************************************

## Model 4: Starter Code 3
In this model I went back to a third layer:
First hidden layer: The first hidden layer had 256 neurons.
Second layer: The second layer had 128 neurons.
Third layer: The third layer had 64 neurons. 
Epochs:100
Batch 3= 256, Batch 4= 512, Batch 5=64

Rationale: I have tried batch normalization and dropout to reduce the overfitting, which may account for the accuracy not improving in previous model. I have also implemented 'EarlyStopping", upon investigation this was suggested once again to manage any overfitting, this stops the training when the validation loss stops improvinging. I also implemented the Reduce LROnPlateu which adjusts the learning rate of the model, this assists in fine tuning the process to assist the learning rate being too high (and thus missing optimal solutions) or too low (and thus, slow).

## Evaluation of this model:
215/215 - 0s - 1ms/step - accuracy: 0.7283 - loss: 0.5524
Loss: 0.5523567199707031, Accuracy: 0.7282798886299133

Overall this model had 72.83% accuracy with a loss of 55.24%.As can be seen, this did improve accuracy of Model 3, however, was not the optimal most optimal model. 


## Summary and Recommendations: 
I developed four models to predict the success of applicants whom apply for funding. The highest level of accuracy I achieved was 72.84%. In terms of Alphabet Soup, although this may be considered ok it does present some risk, in that in nearly 27% of cases they may not be providing funding to the best applicants. There could be other strategies implemented to further improve the training model, such as adjusting the learning rate, changing the number of layers and paramenters of those layers to see if that enhances the accuracy of the model.


