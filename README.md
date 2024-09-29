# Short-Term Campus Load Forecasting using CNN-based En-coder-Decoder Network with Attention

This work presents a novel deep neural network for short-term electric load forecasting for the St. John’s campus of Memorial University of Newfoundland (MUN). The electric load data is obtained from Memorial University of Newfoundland and combined with meteorological data for St. John’s. These datasets are used to formulate a multivariate time-series forecasting problem. A novel deep learning algorithm is proposed, consisting of a 1D Convolutional Neural Network followed by an Encoder-Decoder Network with attention mechanisms. The input for this model includes electric load consumption and meteorological data, while the output is the hourly prediction of the next day's load.

## Data Description

TThe dataset consists of two parts: the first is the electric load dataset, and the second is the meteorological data. The electric load data is obtained from Memorial University of Newfoundland, where the campus uses two meters to monitor electric load at 15-minute intervals. Meteorological information is sourced from weather.gc.ca.

Both datasets are combined to create a single multivariate time series. The main features of the time series are outlined below.

| Parameter        | Value           | 
|:-------------:|:-------------:| 
| Data start date      |January 2nd 2016 | 
| Data end date      |March 31st 2020      |   
| Data interval |1 hour    |    
| Total data points |37221   |    
|Features |08   |    

## Network Architecture

The proposed custom architecture features a 1D convolutional neural network (CNN), which extracts features from the exogenous variables and passes them to the encoder-decoder model. The encoder-decoder model incorporates an attention mechanism that enables it to focus on the most relevant patterns in the extracted temporal features. Both the encoder and decoder consist of GRU units. Following this, a fully connected layer is applied. The 24 output cells of the fully connected layer represent the predicted hourly load profile.

The figure below shows the architecture. 
 
![image](https://github.com/user-attachments/assets/368b5c7d-d7b0-4077-9fd7-b90f11808a3a)


