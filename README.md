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
Sample Predictions
| Index | Actual Price | Predicted Price | Absolute Error | Error (%) | 
| 892 | $154,500 | $145,263 | $9,237 | 5.98% | 
| 1105 | $325,000 | $326,992 | $1,992 | 0.61% | 
| 218 | $311,500 | $223,417 | $88,083 | 28.28% | 
| 1061 | $81,000 | $108,255 | $27,255 | 33.65% | 
| 67 | $226,000 | $204,789 | $21,211 | 9.39% | 


🏠 Most predictions fall within a 2–6% error range — not bad for a model that never stepped foot in a house.
Real-Life Analogy
Training on log prices is like trying to guess someone’s age in dog years — it smooths out the extremes. But when you want real-world accuracy, you convert back to human years and maybe add a little correction if your model thinks everyone’s 7.




