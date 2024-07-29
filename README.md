# deep-learning-challenge
## Module 21 Deep Learning Report

## Overview
* The purpose of this analysis is to create a binary classifier that can help Alphabet Soup, a nonprofit foundation, select the applicants for funding with the best chance of success in their ventures. Using a dataset of over 34,000 organizations, we will apply deep neural network algorithms to predict the success of these applicants based on various features provided in the dataset.


## Results
# Data Preprocessing
  # Target Variable:
    - IS_SUCCESSFUL: This variable indicates whether the funding was used effectively.
  # Feature Variables:
    - APPLICATION_TYPE
    - AFFILIATION
    - CLASSIFICATION
    - USE_CASE
    - ORGANIZATION
    - STATUS
    - INCOME_AMT
    - SPECIAL_CONSIDERATIONS
    - ASK_AMT
  # Removed Variables:
    - EIN and NAME were removed as they are identification columns and do not contribute to the predictive power of the model.
  # Steps Taken:
    1. **Read Data:** Loaded the charity_data.csv into a Pandas DataFrame.
    2. **Identified Variables:** Determined target and feature variables.
    3. **Dropped Columns:** Removed EIN and NAME columns.
    4. **Unique Values:** Analyzed unique values for each column and combined rare categorical variables into a new category "Other" where appropriate.
    5. **Encoded Categorical Variables:** Used pd.get_dummies() to encode categorical variables.
    6 **Split Data:** Split the preprocessed data into features (X) and target (y) arrays and further into training and testing datasets.
    7. **Scaled Data:** Applied StandardScaler to the training and testing features datasets.

### Compiling, Training, and Evaluating the Model

  # Initial Model:
    1. Neural Network Structure:
      - Input Layer: Number of input features.
      - First Hidden Layer: 80 neurons, ReLU activation function.
      - Second Hidden Layer: 30 neurons, ReLU activation function.
      - Output Layer: 1 neuron, Sigmoid activation function.
    2. Compilation: Compiled the model using the Adam optimizer and BinaryCrossentropy loss function.
    3. Training: Trained the model for 100 epochs.
    4. Evaluation: Evaluated the model using the test data.

  # Optimized Model:
    1.  Adjustments Made:
      - Removed Features: Removed STATUS, ORGANIZATION, and USE_CASE columns.
      - Increased Neurons: Increased the number of neurons to 200 in the first layer, 100 in the second layer, 50 in the third layer, and 20 in the fourth layer.
      - Tried Different Activation Functions: Experimented with ReLU, tanh, and sigmoid.
      - Tried Different Loss Functions: Tested BinaryCrossentropy, CategoricalCrossentropy, SparseCategoricalCrossentropy, and MeanSquaredError.
      - Tried Different Optimizers: Used SGD, RMSprop, Adam, and Adamax.
      - Increased Epochs: Trained the model for more epochs.

### Below we have the initial performance:
<img title="a title" alt="Alt text" src="./Screenshot2.png">

### And here we have the optimized performance:
<img title="a title" alt="Alt text" src="./Screenshot1.png">

## Summary
  - The initial model achieved a 75% accuracy in predicting whether a charity application should be approved.
  - Despite various optimization attempts, including adjusting the input data, increasing the number of neurons and hidden layers, and trying different activation functions, loss functions, and optimizers, the model's accuracy did not significantly improve beyond 75%.
  - This consistent accuracy suggests that the dataset might be incomplete or that additional relevant features are needed for better predictive performance.

## Recommendations
  To potentially improve the classification problem, a different model such as a Random Forest or Gradient Boosting could be explored. These models can handle feature importance and interactions more effectively, which might help in identifying more nuanced patterns in the data that a deep neural network might miss. Additionally, gathering more comprehensive data with additional relevant features could also enhance the model's performance.

## Conclusion
  While the deep learning model provides a reasonable accuracy of 75%, it is evident that the current dataset might have limitations. Future work should focus on obtaining more detailed data and exploring different machine learning algorithms to achieve better predictive accuracy.


