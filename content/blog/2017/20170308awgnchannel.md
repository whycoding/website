+++
draft = false
date = "2017-05-16T19:24:54-04:00"
title = "AWGN channel"
tags =["Communications","Research"]
categories = ["StudyNote"]

+++

## What is AWGN channel?

When a message $\mathbf{x}$ is sent to a noisy channel, the output message $\mathbf{y}$ is not the original one. If the channel is AWGN channel,the relation between input and output of the channel is 
$$\mathbf{y} = \mathbf{x} + \mathbf{n}$$
where $\mathbf{n} \sim N(0,\sigma^2)$ is the Gaussian noise. 

The name Additive White Gaussian Noise (AWGN) comes from 3 aspect:
 
* The noise is added to the original message directly;
* In frequency domain, the noise has uniform power across the frequency band which is an analogy to the color white.
* In time domain, the noise is consistent to Gaussian noise.



## Why we use AWGN channel?

AWGN channel model is an important model in communication system. The reason as follows: 

* There are many kinds of noise in a communication system. Based on Central Limit Theorem, the summation of many random processes tends to be a Gaussian random variable. 
* AWGN channel can not describe some complex situration very well, but it is simple enough and the result can give the researcher basic knowledge. 



## How to simulate in AWGN channel?

The behavior of AWGN channel relies on signal-to-noise ratio (SNR) which is defined as the ratio of signal power to the noise power, often expressed in decibels as  
$$\mathrm{SNR} = 10\log_{10}(\frac{P_{signal}}{P_{noise}}), $$ where $P$ is the average power. 

However $\mathrm{SNR}$ usually related to bandwidth, if we do not want to take bandwidth into consideration, we usually use the notation $E_b/N_0$. $E_b$ is the energy per information bit. $N_0$ is the noise power spectral density. It is a normalized signal-to-noise ratio (SNR) measure, also known as the "SNR per bit". 

In order to get $E_b$, we should know the relationship between $E_b$ and $E_s$ (the energy per modulated bit or the energy per symbol). 
$$E_s = R_c R_m E_b$$ where $R_c$ is the code rate, $R_m = \log_2(M)$ is the number of information bits that one symbol can express. For example, for BPSK, $R_m=\log_2(2)=1$, for QPSK, $R_m=\log_2(4)=2$. And $E_s$ is usually normalized as 1. 

For AWGN channel, the noise power spectral density (N0) is given by,
$$N_0 = 2 \sigma^2$$ 

Therefore $E_b/N_0$ can be represented as $$\frac{E_b}{N_0} = \frac{E_s}{R_c R_m N_0} = \frac{1}{R_c R_m 2 \sigma^2}$$
If we write in dB with BPSK, $$\frac{E_b}{N_0} \mathrm{(dB)}= 10\log_{10}\frac{1}{2 R_c \sigma^2}\mathrm{(dB)}$$
then we can get the variance of the noise by

$$\sigma^2= 1/(2 R_c 10^{\frac{E_b}{N_0}/10})$$














