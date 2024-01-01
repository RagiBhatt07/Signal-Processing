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
