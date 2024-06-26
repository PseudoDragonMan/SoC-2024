![image](https://github.com/PseudoDragonMan/SoC-2024/assets/132740618/33435c10-7930-483b-a3d7-0d1d6a9852ff)
For the first assignment of this project, we were asked to create a Stock Price Predictor using reinforcement learning. Deep Q-learning was my choice for implementing this. 
I made use of a Neural Net with one hidden layer and 100 nodes for the Q-value network
The data set I made use of belongs to Apple and I made use of recorded data between 1-1-2020 and 1-1-2023 with each day having each one of the following parameters ('open', 'highest', 'lowest', 'close')
I have implemented the DQN algorithm at its plainest and the state variables were taken to be the above-mentioned parameters and the action variable gave me the predicted 'close' rate of the next day. In retrospect, the 'open' parameter of the day in question could also have been included.
All the values in question were normalised to obtain values between 0 and 1. The action space was taken to be all decimal numbers less than 1 with 4 digits after the decimal point.
I used the epsion greedy technique for exploration starting off with a high epsilon value which gradually comes down and goes no further lower than a pre-defined minimum.
The reward is the reciprocal of the absolute difference between the predicted price and the observed price.
The most prevalent problem I faced was the volatility in the predictions. This volatility was hard to tame with the relatively simple model that was implemented. I had no choice but to make a policy a function of the previous predicted value and the previous observed value. All the volatility was contained by the the previous observed value and the model was relatively more sucessful than earlier
