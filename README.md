# Neural_Network_Charity_Analysis

## Overview of the Analysis
The purpose of this analysis is to utilize data gathered from fictional organization Alphabet Soup, a non-profit foundation dedicated to investing in environmentally and socially responsible organizations. 

The analysis will use application data collected from Alphabet Soup's business team over the years and predict whether new applications from organizations will be a good investment for Alphabet Soup.
## Results
- Data Preprocessing
    - The target variable for this model is "IS_SUCCESSFUL".
    - The features for this model are:
        - APPLICATION_TYPE
        - AFFILIATION
        - CLASSIFICATION
        - USE_CASE
        - INCOME_AMT
        - SPECIAL_CONSIDERATIONS
        - ASK_AMT
    - The following variable are neither features nor targets, and were removed from the input data:
        - EIN
        - NAME

- Compiling, Training, and Evaluating the Model
    - The initial model was created with the following parameters:
        - Input Layer:
            - 43 features
        - First Hidden Layer:
            - 80 nodes
            - RELU activation function
        - Second Hidden Layer:
            - 30 nodes
            - RELU activation function
        - Output Layer:
            - 1 node
            - Sigmoid activation function
        - ![Neural Net Model Summary](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/Deliv2-nn-summary.JPG)

        - These parameters were chosen to allow for the wider range of features an initial learning capacity sufficient to provide actionable steps towards optimization of the model. RELU was chosen as a means of implementing a more complex approach than simple classification, as it was initially unclear which featuers had significant impact on the target variable.
    - The initial neural network model did not achieve the desired performance of 75% accuracy, as shown here:
        - ![Neural Net Initial Accuracy](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/Deliv2-initial-neural-net.JPG)
    - The following steps were taken in an attempt to increase model performance to 75% accuracy:
        - Optimization 1
            

## Summary