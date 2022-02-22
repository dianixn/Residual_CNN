# Residual_CNN

%%%%% Invited paper for WSA 2021 - Interpolation-ResNet

An invited paper released in WSA 2021, which introduce a low complexity solution for channel estimation called Interpolation-ResNet. Conpared with the ReEsNet, Interpolation-ResNet has slightly improved performance and the number of parameters is reduced by 82% (when pruning is not applied). (https://github.com/dianixn/Interpolation-ResNet and https://arxiv.org/abs/2201.09934)

%%%%%

%% ReEsNet from 'Deep Residual Learning Meets OFDM Channel Estimation'

Repeat the results of the paper called 'Deep Residual Learning Meets OFDM Channel Estimation' using MATLAB R2020b

I am quite confused about that paper, therefore, I kindly have 2 guesses from the reference provided and the total parameters mentioned in that paper. I also propose a simple design with almost same performance and 82% reduction on parameters in the paper 'Low Complexity Channel estimation with Neural Network Solutions' and code @ https://github.com/dianixn/Interpolation-ResNet. 

It is defined as ReEsNet. I think they did not release the code so I am not sure what I did is hundred percent correct, so just have fun.

It is a version of my part code indeed but long long ago, so if there is any errors let me know. It works, at least I can send you a copy of trained DAG NN. If you have any question let me know. If the kernel of transposed convolutional layer is [11, 11], then 53k parameters. 

%% MMSE

MMSE_Channel_Tap.m is based on the assumption that jakes model.

LMMSE.m is linear MMSE, used profile to view some information so I made it as a module.

%% Training

Run ResNN_pilot_regression.m to train the residual CNN.

ResImNet.m is the untrained DAG network which deploys interpolation to resize the output.

Residual_transposed.m the untrained DAG network which deploys the transpose convolution to resize the output.

%% Test

Use Demonstration_of_H_regression.m to test.

%% Channel

Simple Rayleigh channel and Doppler shift Rayleigh channel.

WINNER2 Channel is not deployed, and you can download the WINNER2 packet so you can use the WINNER2 channel. Go https://github.com/dianixn/Win2_Channel for simple implementation of WINNER2 channel, but I suggest you to have a check on MATLAB offical page :)

%% Result

I know the MSE performance is worse than the results of the paper called 'Deep Residual Learning Meets OFDM Channel Estimation', but we should have a common knowledge on LS so my LS and MMSE time domain estimation resluts are consistent with the paper called 'On channel estimation in OFDM systems', which is strong enough to be a reference. You can also compare the result of ChannelNet from the original paper. 
