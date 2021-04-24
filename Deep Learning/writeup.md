# Summary comments regarding parameters used for LSTM RNN model construction
* Train/test ratio: 70% train / 30% test >> total dataset has 543 observations. With such a limited sample set, I want to make the training data as robust as possible
* Batch size: 20 (sequential). I went with 20 as through trial and error it seemed like the right balance between computational efficiency and minimiztion of noise to the model. 
* Input shape: 1 as we are using the model to predict daily prices (i.e. 1 step)
* Epochs: I went with 10. Again, when re-running the model with variable epochs, 10 seemed to be optimal (low loss rate) after which I observed marginal optimization; beyond this, I felt that I risked overfitting.
* Hidden Layers: 1

## Questions
1. Which model has a lower loss?
* With window size = 10, the model using closing prices had a loss of 0.0076 vs. the FNG model which had a loss of 0.0734

2. Which model tracks the actual values better over time?
* The model which uses closing prices tracks actual values better over time. 

3. Which window size works best for the model?
* A Window size of 2 worked best for the price based model, suggesting that the best predictor of the value of BTC at time t, is the value at t-2.