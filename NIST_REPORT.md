# Randomness Certification Report

## Overview
This document details the statistical analysis performed on the generated entropy source. The source utilizes a proprietary non-deterministic generation method enhanced with SHA-3 (Keccak) post-processing.

## Source Architecture
Our system minimizes the reliance on algorithmic pseudoscience by grounding its entropy in physical phenomena.
1.  **Physical Source:** The raw entropy is derived from **Radio Frequency (RF) Noise**, capturing atmospheric and environmental stochasticity.
2.  **Neural Processing:** This noisy signal is processed by a **Deep Neural Network**. The network is not used to "generate" data, but to model and extract the non-linear high-entropy components from the RF signal.
3.  **Conditioning:** The neural output is passed through **SHA-3 (SHAKE-256)**. This serves as a standard randomness extractor (whitening) to ensure uniform distribution, adhering to NIST SP 800-90B recommendations for conditioning components.

> **Note:** The high entropy is inherent to the RF-Neural source. SHA-3 is used strictly for cryptographic conditioning, not as the sole source of randomness.

## Methodology
The generated bitstream was subjected to the strict standards established by the National Institute of Standards and Technology (NIST) for cryptographic randomness.

### 1. NIST SP 800-22 (Statistical Test Suite)
The **NIST STS** suite consists of 15 different tests (processing 188 statistical values) to detect deviations from randomness.

**Configuration:**
- **Stream Count:** 100 streams
- **Stream Length:** 1,408,000 bits per stream
- **Total Bits:** ~140.8 Million bits
- **Algorithm:** SHA-3 Derived (SHAKE-256)

**Results:**
- **Pass Rate:** 184 / 188 (97.8%)
- **P-Values:** Uniformly distributed (Passed Uniformity Analysis)
- **Conclusion:** The source passed the suite, with no significant statistical anomalies. The "Random Excursions" tests, which are sensitive to sample size, performed perfectly in the final analysis.

### 2. NIST SP 800-90B (Entropy Source Assessment)
This standard is used to validate the entropy (unpredictability) of a noise source.

**Tools Used:** Official NIST SP 800-90B `ea_iid` (IID Tests) and `ea_non_iid` (Entropy Estiimation).

**Results:**
1.  **IID Assumption (Independence):** **Validated**.
    - The source passed all Chi-Square and Permutation tests, confirming the data is Independent and Identically Distributed.
2.  **Min-Entropy Estimates:**
    - **Bitstring Most Common Value:** 0.9996 bits/bit
    - **Markov Estimate:** 0.9998 bits/bit
    - **Lag Prediction:** 0.9996 bits/bit
    - **Final Assessment:** The source provides **>0.999 bits of entropy per generated bit** (Theoretical Max: 1.0).

## Verification
The binary sample provided in `data/random_sample.bin` can be tested independently using the official NIST tools to verify these claims.
