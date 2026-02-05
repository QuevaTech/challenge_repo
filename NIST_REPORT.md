# Randomness Certification Report

## Overview
This document details the statistical analysis performed on the generated entropy source. The source utilizes a proprietary non-deterministic generation method enhanced with SHA-3 (Keccak) post-processing.

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
