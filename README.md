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
        - ![Neural Net Model Summary]()
    - 
    - 

## Summary