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

        - A boxplot was created using the initial scaled data to determine whether significant outliers existed in the dataset and may be influencing the model.

            ![Boxplot](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/boxplot.JPG)

        - Optimization 1
            - Review of AFFILIATION and USE_CASE columns show that the Other category in each held very low counts, and were dropped to reduce noise in the feature set.
                - Results show negligible improvement to model performance.

        - Optimization 2
            - An additional hidden layer was added to the model with 20 nodes.
                - Results show minimal improvement to model performance.
            - After running the model with optimization 2, the Status column was deemed neither feature nor target variable, and was removed from the data set.
        
        - Optimization 3
            - A function was created to iterate through hyperparameter options of activation functions, number of nodes per layer, number of layers in the model and optimizer function when compiling.
                - Results show minimal improvements once again with max_value of nodes equal to 60, and max_value of layers equal to 5.
                ![Optimization 3 Accuracy Results](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/Opt3-Keras-Tuner.JPG)
                - Further manipulation of the dataset occurred after Optimization 3 in which the column SPECIAL_CONSIDERATIONS_N was removed. The removal was supported as SPECIAL_CONSIDERATIONS_Y contained binary data which reflected whether an application contained special considerations or not.
            
        - Optimization 4
            - The Keras Tuner function was altered to reduce max_value for nodes in layers to reduce potential of overfitting the model with training data.
                - Results showed negligible improvements in model performance from previous optimization step.
                ![Keras Tuner Optimization 4](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/kt.search1.JPG)
        
        - Optimization 5
            - The max_value of nodes per layer was increased to 100, the tuner epochs increased to 100, and the maximum number of hidden layers was increased to 10.

                - The model's best hyperparameters are shown here:
                    ![Optimization 5 Hyperparameters](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/kt.hp.best1.JPG)
                - Results once again showed neglibile improvement to model performance. Accuracy score still below target of 75%.

                ![Optimization 5 Keras Tuner](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/opt5-Keras-Tuner.JPG)

        - Optimization 6
            - Using the initial neural network model, the number of nodes in the first layer was increased to 100 with the RELU activation function. The second hidden layer had 30 nodes, and used the SIGMOID activation function, while the third hidden layer had 20 nodes and also used the SIGMOID activation function. The purpose of this model was to determine whether the initial hidden layer using RELU could supply sufficient data to the subsequent hidden layers to utilize a binary classifier as their base.

                ![Optimization 6 Model Summary](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/opt6-model-summary.JPG)

                - Results show slightly poorer performance of the model with this iteration, with an accuracy score of 72.6%

                    ![Optimization 6 Accuracy Score](https://github.com/JorMerr/Neural_Network_Charity_Analysis/blob/main/Resources/img/opt6-accuracy.JPG)

        - Optimization 7
            - In the final attempt at optimizing the model, a new scaler, RobustScaler, was used to scale the data in an attempt to normalize outliers in the dataset.The model parameters used the Keras Tuner function with a max value of nodes of 100 per layer, max value of hidden layers of 10, and max value of epochs of 100.

                - Results show that after approximately 17hrs of iteration, the model was only able to provide an accuracy of 72.9%.

                ![Optimization 7 Tuner Search]()

                - The best hyperparameters of the model are shown here:

                ![Optimization 7 Hyperparameters]()

                - The final accuracy of the model was 72.96%, not sufficient to meet the criteria of 75%.

                ![Optimization 7 Accuracy]()


## Summary