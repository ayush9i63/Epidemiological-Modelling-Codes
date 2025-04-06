# Epidemiological Modeling with Machine Learning

## Project Overview

The goal of this project is to analyze an epidemiological system using mathematical and computational methods and to explore the real-world significance of the results. The project begins with the Susceptible-Infected (SI) model, followed by a detailed analysis of the Susceptible-Exposed-Infected-Recovered (SEIR) model. Additionally, a new model including quarantine individuals (SEIQR) is proposed and analyzed.

Key parameters such as disease-free equilibrium (K0), endemic equilibrium (Ke), and basic reproduction number (R0) are calculated. Various methods, including Jacobian matrix analysis, dominant eigenvalue of the next-generation matrix, and stability analysis, are used to understand the equilibrium points and long-term behavior of the system.

Machine learning techniques, specifically neural networks, are employed to solve the differential equations, and the results are compared with traditional mathematical methods using Mean Squared Error (MSE). Additionally, a sensitivity analysis is conducted to understand the factors influencing the spread of the disease.

## Machine Learning Approach

### Data Preparation
- The time series data (X) is created using time points from the Runge-Kutta 4th order (RK4) solution.
- The corresponding susceptible (y_S) and infected (y_I) populations are prepared as the target variables.
- The data is split into training and validation sets, with 80% used for training and 20% for validation.

### Neural Network Model
- A feedforward neural network model is built using TensorFlow/Keras.
- **Architecture**:
  - Input layer with 64 units and ReLU activation.
  - One hidden layer with 64 units and ReLU activation.
  - Output layer with 2 units to predict susceptible and infected populations.
  
### Model Training
- The model is compiled with the Adam optimizer and Mean Squared Error (MSE) as the loss function.
- The model is trained for 100 epochs with a batch size of 32 using the training data.

### Prediction & Evaluation
- The trained model predicts susceptible and infected populations over the entire time range.
- The predicted values are compared to the true values obtained from the RK4 method.
- A visualization is created comparing the predicted and true values for both susceptible and infected populations.

### Performance Evaluation
- The model’s performance is evaluated by calculating the Mean Squared Error (MSE) between the predicted and true values.
- The results demonstrate how well the neural network approximates the solution provided by traditional mathematical methods.

## Files in this Repository

- `Epidemiological_Modelling.py`: Contains all Code

## Requirements

- Python 3.x
- TensorFlow >= 2.x
- NumPy
- Matplotlib

