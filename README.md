## OVERVIEW OF PROJECT

The purpose of this project was to develop a machine learning model for Alphabet Soup, a nonprofit foundation, that can predict if applicants applying for funding will be successful if funded by Alphabet Soup. Such analysis assists the foundation in selecting the best applicants for funding, ensuring that funds are used to ensure the most benefit.

## Dataset Overview

The data provided was in CSV format and contained 34,000 organizations.

## RESULTS

## Data Preprocessing

The target variable for this model is **IS_SUCCESSFUL**, which is a binary (0 or 1) variable that indicates if funding was used effectively by the applicant (the organization).

The features of the model included in the metadata are:

- **EIN and NAME**—Identification columns
- **APPLICATION_TYPE**—Alphabet Soup application type
- **AFFILIATION**—Affiliated sector of industry
- **CLASSIFICATION**—Government organization classification
- **USE_CASE**—Use case for funding
- **ORGANIZATION**—Organization type
- **STATUS**—Active status
- **INCOME_AMT**—Income classification
- **SPECIAL_CONSIDERATIONS**—Special considerations for application
- **ASK_AMT**—Funding amount requested
- **IS_SUCCESSFUL**—Was the money used effectively?

It should be noted that the EIN and NAME identification columns were removed from the dataset. These variables were removed as the values did not provide any insights. Each EIN and NAME was attached to an Application Type and other classifications, making them unnecessary for identifying organizations or for analysis. There are a total of 49 features used in the models.

## Compiling, Training, and Evaluating the Model

I conducted four deep neural network training models in an attempt to reach 75% accuracy in predicting the success of funding for applicants. In all models, I adopted the following:

- **Activation function**: The ReLU activation function is used in the hidden layers to introduce non-linearity.
- **Output layer**: The outer layer utilized the Sigmoid activation function with a single (1) neuron.
- **Neurons**: In all models, I reduced the number of neurons in each hidden layer.
- **Model saving**: The model saved weights every 5 epochs to monitor training progress.

## Model 1: Starter Code

- **First hidden layer**: The first hidden layer had 50 neurons.
- **Second layer**: The second layer had 25 neurons.
- **Epochs**: 100
- **Batch size**: 320

**Rationale**: This model was used to create a baseline and employs general principles for this type of machine learning model. Using 50 neurons for the first layer aligns with 49 features, and 25 for the next layer is common practice for deep learning.

### Evaluation of the Model:

The accuracy of the model was:

215/215 - 0s - 2ms/step - accuracy: 0.7261 - loss: 0.5974
Loss: 0.5974100232124329, Accuracy: 0.7260932922363281

Overall, this model had 72.61% accuracy with a loss of 59.00%. This model correctly predicted the outcome of funding being used successfully 72.61% of the time. The 59% loss suggests that the model is still learning and may need adjustments to improve accuracy.

---
## Model 2: Starter Code 1

- **First hidden layer**: The first hidden layer had 60 neurons.
- **Second layer**: The second layer had 35 neurons.
- **Third layer**: The third layer had 15 neurons.
- **Epochs**: 100
- **Batch size**: 320

**Rationale**: In this model, I added a third layer to enhance the model's ability to learn more complex patterns. The first model provided a good baseline, but the aim is to reach 75% accuracy, hence the addition of a layer and changes to the neurons.

### Evaluation of the Model:

The accuracy of the model was:

215/215 - 1s - 3ms/step - accuracy: 0.7284 - loss: 0.5595
Loss: 0.5595238208770752, Accuracy: 0.7284256815910339

Overall, this model had 72.84% accuracy with a loss of 55.95%, meaning it predicted the outcome correctly 72.84% of the time. This model is a slight improvement from the first model (+0.23%), suggesting that adding an additional layer helps capture underlying patterns.

---

## Model 3: Starter Code 2

- **First hidden layer**: The first hidden layer had 40 neurons.
- **Second layer**: The second layer had 30 neurons.
- **Third layer**: The third layer had 20 neurons.
- **Fourth layer**: The fourth layer had 10 neurons.
- **Epochs**: 150
- **Batch size**: 128

**Rationale**: In this model, I added an additional layer to enhance the ability to read more complex data patterns and improve accuracy.

### Evaluation of the Model:

The accuracy of the model was:

215/215 - 0s - 2ms/step - accuracy: 0.7278 - loss: 0.5647
Loss: 0.5646637678146362, Accuracy: 0.7278425693511963

Overall, this model had 72.78% accuracy with a loss of 56.47%. Adding an additional layer reduced the accuracy; thus, it could be assumed that some "overfitting" is occurring, and the model is not capturing underlying patterns.

---

## Model 4: Starter Code 3

In this model, I reverted to a third layer:

- **First hidden layer**: The first hidden layer had 256 neurons.
- **Second layer**: The second layer had 128 neurons.
- **Third layer**: The third layer had 64 neurons.
- **Epochs**: 100
- **Batch sizes**: 256, 512, 64 (for different runs)

**Rationale**: I tried batch normalization and dropout to reduce overfitting, which may explain the lack of accuracy improvement in previous models. I also implemented **EarlyStopping** to manage overfitting, stopping training when the validation loss stops improving. Additionally, I implemented **ReduceLROnPlateau**, which adjusts the learning rate to help fine-tune the training process.

### Evaluation of the Model:

The accuracy of the model was:

215/215 - 0s - 1ms/step - accuracy: 0.7283 - loss: 0.5524
Loss: 0.5523567199707031, Accuracy: 0.7282798886299133

Overall, this model had 72.83% accuracy with a loss of 55.24%. While this model improved upon Model 3, it was not the most optimal.

---

## Summary and Recommendations

I developed four models to predict the success of applicants applying for funding. The highest level of accuracy achieved was 72.84%. In terms of Alphabet Soup, while this may be considered acceptable, it presents some risk, as nearly 27% of cases may not provide funding to the best applicants. Other strategies could be implemented to improve the training model, such as adjusting the learning rate or changing the number of layers and parameters of those layers to enhance model accuracy.











 









