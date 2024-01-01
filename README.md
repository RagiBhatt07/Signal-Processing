# Audio Declipping with Social Sparsity
    Paper Implementation: https://hal.science/hal-01002998/document

## Introduction
This notebook outlines the implementation of an audio declipping algorithm based on the paper "AUDIO DECLIPPING WITH SOCIAL SPARSITY". The algorithm aims to restore audio signals that have been subject to clipping by employing iterative thresholding algorithms and leveraging the principle of social sparsity.

## Problem Statement
Clipping occurs when the amplitude of an audio signal exceeds the maximum limit that can be represented in the digital domain, resulting in truncation. This often leads to distortion that is unpleasant to the ear. The goal of declipping is to estimate the original signal amplitudes that were lost due to clipping.

## Approach
The implementation will involve several key steps:
1. Representing the clipped audio signal in a sparse domain using a time-frequency dictionary.
2. Formulating and solving an optimization problem to find the best sparse representation that fits the clipped signal while respecting the clipping constraints.
3. Employing advanced thresholding operators to maintain social sparsity.
4. Iterating the process until convergence.

## Operators:

- Lasso Operator:
        This operator adjusts coefficients by shrinking them based on their magnitude relative to a threshold value. 
        $$\widetilde{\alpha}_{tf}^{L} = S_{\lambda}^{L}(\alpha_{tf}) = \alpha_{tf} \left(1 - \frac{\lambda}{|\alpha_{tf}|}\right)_+$$

- Windowed Group-Lasso (WGL) Operator:
        The WGL operator is a variation of the Lasso operator, which takes into account the neighborhood of each coefficient. 
        $$\widetilde{\alpha}_{tf}^{WGL} = S_{\lambda}^{WGL}(\alpha_{tf}) = \alpha_{tf} \left(1 - \frac{\lambda}{\sqrt{\sum_{t' \in N(t)}|\alpha_{t'f}|^2}}\right)_+$$
        
In this equation, the denominator of the shrinkage term is the sum of the squares of the coefficients in the neighborhood N(t).


- Empirical Wiener (EW) Operator:
        This operator adjusts coefficients by shrinking them based on their magnitude relative to a threshold value. 
        $$\widetilde{\alpha}_{tf}^{EW} = S_{\lambda}^{EW}(\alpha_{tf}) = \alpha_{tf} \left(1 - \frac{\lambda^2}{|\alpha_{tf}|^2}\right)_+$$

- Persistent Empirical Wiener (PEW) Operator:
        The PEW operator is a variation of the EW operator, which takes into account the neighborhood of each coefficient. 
        $$\widetilde{\alpha}_{tf}^{PEW} = S_{\lambda}^{PEW}(\alpha_{tf}) = \alpha_{tf} \left(1 - \frac{\lambda^2}{\sum_{t' \in N(t)}|\alpha_{t'f}|^2}\right)_+$$
        
In this equation, the denominator of the shrinkage term is the sum of the squares of the coefficients in the neighborhood N(t).
​




## Signal Output:
![image](https://github.com/RagiBhatt07/Signal-Processing/assets/124009502/ab3d2235-19bb-408d-97ae-35a96f89dac3)

