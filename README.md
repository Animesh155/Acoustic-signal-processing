# Acoustic-signal-processing

## 1. Description

This document describes signal processing methods to detect faults in mechanical bearings. The primary purpose is to identify inner-race faults and outer-race faults.

## 2. Dataset Summary

* **Primary Dataset (Aziz et al., 2025):** Contains normal condition data, inner-race fault data, and outer-race fault data. The dataset contains 2,160 files recorded at 10-second intervals.


* **Secondary Dataset (Mendeley Dataset):** Contains vibration data recorded at 600 RPM and 1,800 RPM.


## 3. Signal Processing Methods

### 3.1 Overall Kurtosis Analysis

* Kurtosis calculated over the whole signal did not detect the faults.


* Fault impulses occur in specific frequency bands, not across the whole signal.



### 3.2 Wavelet Decomposition

* The method splits the signal into multiple frequency bands with low-pass filters and high-pass filters.


* **Wavelet Type:** Daubechies 4 (`db4`). The shape of this wavelet matches mechanical impulses.


* **Decomposition Levels:** 6 levels.


* **Sampling Frequencies:**
* 25,600 Hz for the Aziz et al. dataset.


* 44,100 Hz for the Mendeley dataset.




* **Findings:**
* Frequency bands D5 and D6 provide early fault indication.


* Wavelet decomposition reliably detects outer-race faults.


* Inner-race faults show low detection rates and can be missed.





### 3.3 Spectral Kurtosis and Envelope Analysis

* Spectral kurtosis calculates kurtosis values across specific frequency bands.


* A 2D kurtogram identifies the optimal frequency band for filtering.


* **Identified Frequency Band:** 1,000 Hz to 1,400 Hz.


* A band-pass filter removes noise from the selected band before envelope analysis.


* Ten consecutive files per condition provide reliable fault detection.
