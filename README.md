# Short-Term Campus Load Forecasting using CNN-based En-coder-Decoder Network with Attention

This work presents a novel deep neural network for short-term electric load forecasting for the St. John’s campus of Memorial University of Newfoundland (MUN). The electric load data is obtained from Memorial University of Newfoundland and combined with meteorological data for St. John’s. These datasets are used to formulate a multivariate time-series forecasting problem. A novel deep learning algorithm is proposed, consisting of a 1D Convolutional Neural Network followed by an Encoder-Decoder Network with attention mechanisms. The input for this model includes electric load consumption and meteorological data, while the output is the hourly prediction of the next day's load.

## Data Description

The dataset consists of two parts: the first is the electric load dataset, and the second is the meteorological data. The electric load data is obtained from Memorial University of Newfoundland. The campus uses two meters to monitor electric load at 15-minute intervals. Meteorological information is sourced from weather.gc.ca.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

## Network Architecture
