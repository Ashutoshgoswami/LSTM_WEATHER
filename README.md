# LSTM_WEATHER

This code workflow involves preprocessing weather data, building an LSTM model for time series forecasting, and training it on temperature predictions using the following steps:

**Data Preprocessing:**
Loading and Cleaning Data:

The dataset is read from a CSV file (testset.csv).
Missing columns are filled using forward fill (ffill).
The data is resampled on a daily basis using the mean of weather features.
Handling Missing Data:

Forward fill method is applied to handle missing values in the dataset.
Feature Selection and Scaling:

The features relevant to weather prediction are chosen, and the data is normalized using MinMaxScaler to ensure values lie between 0 and 1.
Creating Sequences:

Sequences of length 10 are generated to serve as input for the model. The sequence length of 10 refers to 10 time steps (days).
The target variable is temperature (_tempm), which is used for forecasting.
Model Architecture:
LSTM Model:

A Sequential LSTM model is built with three LSTM layers.
Dropout layers are added after each LSTM layer to prevent overfitting.
A Dense layer with a single output node is used for the final prediction (temperature).
Model Compilation:

The model is compiled with Adam optimizer and mean_squared_error loss function, suitable for regression problems.
Model Training:
Early Stopping & Checkpoints:

Early stopping is used to prevent overfitting by halting training if the validation loss doesn't improve.
Model checkpoints are used to save the best model weights during training.
Training Process:

The model is trained over 100 epochs with an 80-20 training-validation split.
A batch size of 64 is used, which dictates how many sequences are processed before updating model weights.
Loss Progress:

The training loss and validation loss are monitored. The model improves over time, achieving a final validation loss of around 0.0023.
