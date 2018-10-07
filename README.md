# GRU-D
inspired by 'Recurrent Neural Networks for Multivariate Time Series with Missing Values' pytorch ver
https://arxiv.org/abs/1606.01865


This is my the first Python3, Pythorch, and neural network project. After taking ‘Deep learning specialization’ at Coursera, I became interested in the multivariate time series problems. For these problems, I tried various models, such as the ARIMA model, LSTM, and GRU. I decided to use GRU-D as the model because of its effectiveness. Unfortunately, when I was looking for the original code for this model, I was unable to find it. 

However, upon conducting further research, I found a variation of the code that was developed by a user, zhiyongc, in Github.  I found that his code is not the same as the paper. First, the number of the time steps or sizes does not impact the number of the parameters because the code uses only one unit. After realizing it, I tried to make a new variation of GRU-D through Pytorch code by myself. I got help from zhiyongc’s code, Pytorch code, and many other resources on the web that helped me developed this GRU-D variation.

I try to get the same results as the paper, but I am still far from there.

1. I only tried PhysioNet data because this one is described better than other data.
2. In the paper, they used 33 inputs, but I found more than 33 inputs (37 including MechVent). The mean number of time steps and the maximum number of time steps also did not match with the raw data. I might have missed something.
3. In the paper, the number of hidden states(h) of GRU-D is 49. I do not have any clue why that is.
4. The number of parameters do not match. In my calculation and code, 10 (# of parameter per step per inputs) * 33 (# of inputs) * 49 (# of steps) = 16170 and + a for output calculation. The number of parameters in the paper is 18838. It might be due to untold areas like how the output was gotten.
5. I am unsure of the process of selecting the time steps when the data has to be shortened.

I plan to work on functions like dropout, early stopping, and bidirectional.

Update(Oct.07.2018)
plane dropout with three variation
  + moon : [Moon et al.2015] Taesup Moon, Heeyoul Choi, Hoshik Lee, and Inchul Song. 2015. Rn- ndrop: A novel dropout for rnns in asr. Au- tomatic Speech Recognition and Understanding (ASRU).
  + Gal : [Gal2015] Yarin Gal. 2015. A theoretically grounded application of dropout in recurrent neural networks. arXiv:1512.05287.
  + mloss : Semeniuta, S., Severyn, A., & Barth, E. (2016). Recurrent dropout without memory loss. arXiv preprint arXiv:1603.05118.
  
planning to work on implenting weighted dropout
https://github.com/salesforce/awd-lstm-lm
Regularizing and Optimizing LSTM Language Models https://arxiv.org/abs/1708.02182
An Analysis of Neural Language Modeling at Multiple Scales https://arxiv.org/abs/1803.08240


