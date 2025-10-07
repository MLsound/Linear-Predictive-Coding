# Linear Predictive Coding (LPC) for Speech Analysis

This repository contains the full implementation and analysis for a practical assignment on **Linear Predictive Coding (LPC)**, a core technique in Digital Signal Processing and Time Series Analysis, particularly optimized for speech signals.

The project models the human speech production system as an all-pole filter (the **vocal tract**) excited by either a periodic impulse train (for voiced sounds) or random noise (for unvoiced sounds).

## Key Implementations:

* **LPC Coefficient Estimation:** Implementation of the **autocorrelation method** to solve the Yule-Walker equations ($\mathbf{R}\mathbf{h} = \mathbf{r}$), estimating the coefficients that model the vocal tract filter.
* **Analysis and Segmentation:** Processing of an audio signal (`estocastico.wav`) using **Hamming windowing** and **Overlap-Add** (OLA) segmentation to ensure quasi-stationarity.
* **Excitation Signal ($\hat{x}[t]$) Calculation:** Estimation of the excitation signal via the **prediction error** ($\hat{x}[t] = y[t] * h_f[t]$), with careful handling of filter transients across segments.
* **Synthesis and Reconstruction:** Implementation of the all-pole synthesis filter (AR filter) using the difference equation for **speech reconstruction** ($\hat{y}[t]$).
* **Frequency Response Analysis:** Calculation and visualization of the magnitude response for both the **predictor filter** ($|H_f(e^{j\omega})|$) and the **synthesis filter** ($|H_i(e^{j\omega})|$), illustrating the formant structure.

## Optative Features (Speech Modification):

1.  **Vocal Replacement (Timbre Modification):** Modifying the *vocal tract model* by substituting the LPC coefficients of all detected vowel segments with a target vocal's coefficients.
2.  **Fundamental Frequency (F0) Alteration:** Manipulating the *pitch* by subsampling and concatenating the estimated excitation signal ($\hat{x}[t]$) in voiced segments.