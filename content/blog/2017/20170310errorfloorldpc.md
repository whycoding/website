+++
title = "Error floor of LDPC Codes"
draft = true
date = "2017-05-16T20:02:12-04:00"
tags =["Communications","Research"]
categories = ["StudyNote"]

+++


## Definition
* This phenomenon can be characterized as an abrupt decrease in the slope of a code's performance curve from the moderate-SNR waterfall region to the high-SNR floor region. 
* The frame error rate (FER) reduction slows down as the noise level decreases.


## Reason
The error floor has been attributed to certain sub-graphs of an LDPC code's Tanner graph induced by so-called trapping sets.

They are attributed to a particular structure in the codes’ Tanner graphs, known as trapping sets, which traps the message-passing algorithms commonly used to decode LDPC codes, and prevents decoding from converging to the correct codeword.

On the other hand, the detected errors, or decoder failures, happen when the decoder is unable to converge to any codeword after the maximum decoding iterations and there are still unsatisfied parity checks. 



* Trapping set
 * Definition: A $(w, v)$ trapping set is a set of $w$ variable nodes (VNs) which induces a subgraph with $v$ odd-degree check nodes and an arbitrary number of even-degree check nodes (CNs). 
 * The combinations of bit nodes that prevent the LDPC decoder from converging to the transmitted codeword are defined as trapping sets.
* Instanton
* Pseudo-codeword


---
## Mitigate the error floor from decoder

* New schedule
 * H. Xiao, "Graph-based message-passing schedules for decoding LDPC codes"
 * A. I. Vila Casado, "Informed dynamic scheduling for belief-propagation decoding of LDPC codes"
* Averaged decoding
 * S. Lander, "Algorithmc and combinatorial analysis of trapping sets in structured LDPC codes"
* Post-processing
 * list all possible syndromes and corresponding error bits in look-up table
 *E. Cavus, "A performace improvement and error floor avoidance technique for belief propagation decoding of LDPC codes"*
  * Erase bit decisions (or bit LLR) based on trapping set and redecode with BEC decoder (or SP decoder)
 *Y. Han, "Low-Floor Decoders for LDPC Codes"*
 * select one neighboring bit to flip and redecode, if fail flip another one
 *J. Kang, "An iterative decoding algorithm with backtracking to lower the error-floors of LDPC codes"*
 * strengthen unsatisfied check node message and weaken satisfied check node message
 *Z. Zhang, "Lowering LDPC error floors by postprocessing"*
 * select bits to flip, erase or scale based on sign and magnitude change
 *X. Zhang, A two-stage decoding algorithm to lower the error-floors for LDPC codes*

## Approximate the error floor
* By trapping set (T. Richardson, "Error floors of LDPC codes")
 * form a list of trapping set
 * calculating the contribution of each trapping set

* By instanton

