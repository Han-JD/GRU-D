# GRU-D
AUC score (mean ± std) for mortality prediction in the paper: 0.8424 ± 0.012; my research got: 0.8419.

This research is inspired by 'Recurrent Neural Networks for Multivariate Time Series with Missing Values' pytorch version (https://arxiv.org/abs/1606.01865).

This is my first Python3, Pythorch, and neural network project. After taking ‘Deep learning specialization’ at Coursera, I became interested in the multivariate time series problems. For these problems, I tried various models, such as the ARIMA model, LSTM, and GRU. I decided to use GRU-D as the model because of its effectiveness.

Upon conducting further research, I found a variation of the code that was developed by a user, zhiyongc, in Github. I found that his code is not the same as the paper. I tried to make a new variation of GRU-D through Pytorch code. I got help from zhiyongc’s code, Pytorch code, and many other resources on the web that helped me develop this GRU-D variation.

I try to get the same results as the paper, but I am still far from there.
1. I only tried PhysioNet data (https://physionet.org/challenge/2012/) because this one described the processes and outcomes better than other data.
2. In the paper, they used 33 inputs, but I found more than 33 inputs (37 including MechVent). The mean number of time steps and the maximum number of time steps also did not match with the raw data, suggesting that I might have missed something.
3. In the paper, the number of hidden states(h) of GRU-D is 49, but I do not have any clue why that is.
4. The number of parameters in the paper is 18838 with 33 input variables and 49 hidden states. According to Rahul Dey and Fathi M. Salem (2017), the total number of parameters in the GRU RNN equals 3×(n^2+nm+n). where m is the input dimension and n is the output dimension. Since GRU-D has a different structure, the way to calculate would be similar.
5. I am unsure of the process of selecting the time steps when the data has to be shortened. I tried random selection, but, in the end, I chose the timeline with most parameters with the first and last one.
6. I reduce the learning rate by a certain step. 

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
