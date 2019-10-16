+++
date = "2017-05-16T19:32:13-04:00"
title = "Bandpass signal and its lowpass equivalent"
draft = true
tags =["Communications","Research"]
categories = ["StudyNote"]

+++

## Why do we need modulation?

* The channel is divide by different . The low frequency signal should match the spectral characteristics. 
* high frequency signal is easy to transmit


## lowpass equivalent 

### Preliminary
* Any real, narrowband, and high frequency signal can be represented in terms of a complex low frequency signal, called the lowpass equivalent. 
* Applying signal processing algorithms to lowpass signals is much easier due to lower required sampling rates, which in turn result in lower rates of sampled data. 

* Lowpass signals are low frequency signals, which means that in the time domain, they are slowlly varying signals with no jumps or sudden variations. 

* Fourier transform of a real signal has *Hermitian symmetry*, $X(-f) = X^*(f)$, from which we conclude that $|X(-f)| = |X(f)|$ and $\angle X(-f) = \angle X(f)$. Then we can recover the signal by only transmit the positive frequecy. 
`$X(f) = X_+(f) + X_-(f) = X_+(f) + X_+^*(-f)$`

### hilbert transform 
$\hat{x}(t) = x(t) * \frac{1}{\pi t}$ 

The Fourier transform of $\frac{1}{\pi t}$ is $-j sgn(f)$. Then based on convolution principle, we get
$$\mathcal{F\{\hat{x}}(t)\} = X(f)  (-j sgn(f))$$ 

90degree shift

### Pre-envolope signal 

$ x_+(t) = x(t) + j\hat{x}(t)$ 

$$\mathcal{F}\{x_+(t)\} = X(f) + X(f)sgn(f)= 2X(f)u(f)$$ 


### lowpass equivalent signal

$ x_l(t) = x_+(t)e^{-j2\pi f_c t}$ 

$$\mathcal{F}\{x_l(t)\} = 2X(f+f_c)u(f+f_c)$$ 
