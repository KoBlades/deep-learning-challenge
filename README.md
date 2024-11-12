# Deep Learning Challenge: Module 21

## Overview of the Analysis
The purpose of this analysis is to develop a machine learning model that predicts the likelihood of success (`IS_SUCCESSFUL`) for various applications based on their features. The analysis involves preprocessing the data, selecting relevant features, defining a neural network model, training the model, and evaluating its performance. The goal is to build a model that can predict whether an application is successful, using input features such as the amount requested, the type of application, and others.

---

## Results

### Data Preprocessing

- **Target Variable(s):**
  - **`IS_SUCCESSFUL`**: This is the target variable that we are trying to predict, representing whether the application was successful (1) or not (0).

- **Feature Variables:**
  - **`APPLICATION_TYPE`**: The type of application, which likely affects success.
  - **`ASK_AMT`**: The amount requested, which can influence approval chances.
  - **`SPECIAL_CONSIDERATIONS`**: Whether there are special considerations for the application.
  - **`CLASSIFICATION`**: The classification type of the organization, which may affect how the application is evaluated.

- **Variables to Remove (Neither Targets Nor Features):**
  - **`EIN`**: This is an identifier and doesn’t contribute to predicting the target.
  - **`NAME`**: This is also an identifier and not useful for prediction.

---

### Compiling, Training, and Evaluating the Model

- **Neurons, Layers, and Activation Functions:**
  - **Neurons per Layer**:
    - 128 neurons in the first hidden layer.
    - 64 neurons in the second hidden layer.
  - **Activation Functions**:
    - **ReLU** (Rectified Linear Unit) was used for hidden layers, as it is widely used for deep neural networks and helps with non-linear relationships.
    - **Sigmoid** was used in the output layer, as this is a binary classification problem (predicting success or failure).

- **Achieving Target Performance:**
  - The goal was to achieve an accuracy of at least **0.75**. However, we faced a trade-off between underfitting and overfitting.
    - Initially, reducing the number of neurons significantly decreased accuracy, which suggested that the model was underfitting with too few neurons.
    - After increasing complexity and using regularization methods like **dropout** and **early stopping**, the model showed improved performance, but it didn’t fully achieve the target of **0.75 accuracy**.

- **Steps Taken to Increase Model Performance:**
  - **Experimented with different numbers of neurons**: Adjusted the number of neurons in hidden layers.
  - **Implemented dropout regularization**: To prevent overfitting and improve generalization.
  - **Used early stopping**: To avoid overfitting and to stop training once the model’s performance on the validation set no longer improved.
  - **Tried different optimizers**: Using **Adam** optimizer and adjusting learning rates helped improve convergence.
  - **Batch normalization**: Added to stabilize training, though it didn’t lead to a significant improvement.
  - **Changed features**: Used features that were more relevant to the model.

---

## Final Model Performance

The final model achieved an accuracy of approximately **0.60**, which is below the target of **0.75**. While this result shows some progress, the model still needs improvement in order to achieve the desired level of performance.

---
