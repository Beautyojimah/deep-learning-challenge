# Alphabet Soup Charity Funding Predictor (Deep learning challenge)

## Overview
The objective of this project is to develop a binary classification model that can predict the applicants for funding with the best chance of success in their ventures. This will help Alphabet Soup, a nonprofit foundation make more informed decisions about which organizations to fund, maximizing the effectiveness of their donations.

The dataset contains information on over 34,000 organizations that have received funding from Alphabet Soup over the years, including various characteristics of each organization and a binary variable indicating whether the funding was used effectively.

Within the `Deep_learning` folder are the script and H5 file for the initial modela nd the optimised model, as well as a report in docx.
 
# Dependencies
- Pandas
- Sklearn
- Tensorflow

## Data Preprocessing

- The dataset was loaded into a Pandas DataFrame.
- Columns `EIN` and `NAME` were dropped as they are identification columns and don't contribute to the predictive power of the model.
- Rare categorical values in the `APPLICATION_TYPE` and `CLASSIFICATION` columns were binned into an "Other" category.
- Categorical variables were one-hot encoded.
- The data was split into training and testing sets, and features were scaled using `StandardScaler`.

## Neural Network Model

**Model Architecture**:
The initial neural network model consisted of:
- Input feature: 43 neurons (based on the number of input features after preprocessing), using the ReLU activation function.
- First layer : 80 neurons, using the ReLU activation function.
- Hidden layer : 30 neurons, using the ReLU activation function.
- Output layer: 1 neuron, using the Sigmoid activation function (for binary classification).

The model was compiled using the Adam optimizer, binary cross-entropy loss (appropriate for binary classification), and accuracy was used as the evaluation metric.

## Model Optimization

To achieve a target accuracy of 75%, several optimization strategies (hyperparameter tuning) were implemented:

- Additional columns (`STATUS` and `SPECIAL_CONSIDERATIONS`) were dropped as they have little variance.
- Outliers were removed from the numerical column `ASK_AMT`
- Additional hidden layers were added to the model.
- Activation functions were experimented with, including `LeakyReLU`, `relu` and `sigmoid`.
- Decreasing the learning rate to 0.0005.
- Increasing the number of epochs to 120.


## Results

The optimized model achieved an accuracy of 75% with a loss of 56%. Further tuning and experimentation may improve the results even further.

## Conclusions and Recommendations

The neural network model provided a reasonably accurate prediction of the success of funded organizations. For further improvements, other machine learning models, such as Random Forest or Gradient Boosted Trees, could be considered and compared against the neural network. Additionally, further feature engineering or gathering additional data might also enhance the model's performance.
