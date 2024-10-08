# Short-Term Campus Load Forecasting using CNN-based Encoder-Decoder Network with Attention

This work presents a novel deep neural network for short-term electric load forecasting for the St. John’s campus of Memorial University of Newfoundland (MUN). The electric load data is obtained from Memorial University of Newfoundland and combined with meteorological data for St. John’s. These datasets are used to formulate a multivariate time-series forecasting problem. A novel deep learning algorithm is proposed, consisting of a 1D Convolutional Neural Network followed by an Encoder-Decoder Network with attention mechanisms. The input for this model includes electric load consumption and meteorological data, while the output is the hourly prediction of the next day's load.

## Data Description

TThe dataset consists of two parts: the first is the electric load dataset, and the second is the meteorological data. The electric load data is obtained from Memorial University of Newfoundland, where the campus uses two meters to monitor electric load at 15-minute intervals. Meteorological information is sourced from weather.gc.ca.

Both datasets are combined to create a single multivariate time series. The main features of the time series are outlined below.

<div align="center">

| Parameter        | Value           | 
|:-------------:|:-------------:| 
| Data start date      | January 2nd 2016 | 
| Data end date      | March 31st 2020      |   
| Data interval | 1 hour    |    
| Total data points | 37221   |    
| Features | 08   |    

</div>

## Network Architecture

The proposed custom architecture features a 1D convolutional neural network (CNN), which extracts features from the exogenous variables and passes them to the encoder-decoder model. The encoder-decoder model incorporates an attention mechanism that enables it to focus on the most relevant patterns in the extracted temporal features. Both the encoder and decoder consist of GRU units. Following this, a fully connected layer is applied. The 24 output cells of the fully connected layer represent the predicted hourly load profile.

The figure below shows the architecture. 
 
![image](https://github.com/user-attachments/assets/425a9b3d-d61f-48be-ba83-94fb7acbade0)

## Results

The metrics used to evaluate performance include Mean Absolute Error and Mean Absolute Percentage Error. 

### Mean Absolute Percentage Error (MAPE)

Mean Absolute Percentage Error (MAPE) is an evaluation metric that is defined as: 

```math
\text{MAPE} = 100 \cdot \frac{1}{N} \sum_{i=1}^{N} \left| \frac{G_i - P_i}{G_i} \right|
```

This metric is independent of the scale of data and can be used to compare an algorithm across different time series. Although if a time series has zero or near zero values, this evaluation metric becomes infinite. It also penalizes negative and positive errors asymmetrically.  A more accurate algorithm would have lower MAPE compared to a less accurate model.

 ### Mean Absolute Error (MAE)

Mean absolute error is the average of the absolute difference between a predicted/forecasted value and ground truth. It can be written as: 
```math
\text{Mean Absolute Error} = \frac{\sum_{i=1}^{N} |P_i - G_i|}{N}
```
Here, P and G are predictions and ground values respectively. N is the number of values in the dataset. If an estimator is more accurate, it would result in a lower MAE. An inaccurate estimator would result in a higher MAE.


The proposed architecture shows significant improvement compared to state-of-the-art algorithms found in the current AI lanscape. This can be observed in the plots below. 

<p align="center">
  <img src="https://github.com/user-attachments/assets/06f62391-e26f-44b9-b88f-f449173dfca4" alt="Image 1" width="75%">
  <img src="https://github.com/user-attachments/assets/201c72f8-8cfb-4bc9-ac8b-5565de9d947c" alt="Image 2" width="75%">
</p



