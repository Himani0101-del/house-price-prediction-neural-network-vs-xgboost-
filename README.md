# house-price-prediction-neural-network-vs-xgboost-
Welcome to my machine learning playground, where we try to guess house prices better than your average real estate agent — using deep learning, gradient boosting, and a little post-prediction therapy.
Project Overview
This project tackles the classic regression problem: predicting house prices based on features like square footage, number of bedrooms, location, and more.
We explore two modeling approaches:
- A neural network trained on log-transformed prices
- An XGBoost model trained on raw prices
And yes, we added a post-prediction correction factor to help our neural network stop lowballing luxury listings. Because not every house is a starter home.
 Models Used
1. Neural Network (PyTorch)
- Architecture: Fully connected layers with Leaky ReLU
- Regularization: Dropout layers to prevent overfitting
- Target Transformation: Log(price) for smoother learning
- Scaling: MinMaxScaler for input features
- Post-Prediction Correction: +7% upward adjustment for high-end bias
2. XGBoost
- No scaling or transformation
- Handles missing data natively
- Outperforms NN in RMSE and R²
- No correction needed — it just gets it
Bias Analysis
We grouped predictions by price range and found:
- Neural net underpredicts high-end homes
- Relative error is higher for low-priced homes
- Correction factor improves accuracy at the top end







