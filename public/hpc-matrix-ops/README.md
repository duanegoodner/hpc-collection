# Cache-Aware Matrix Operations and Intro to OpenMP

This project explores the effects of memory hierarchy on performance through tiled matrix transposition and multiplication. It also introduces basic OpenMP directives for loop-level parallelism and evaluates their impact.

## Overview

The project is divided into three components:

### 1. Matrix Transposition
Implemented a tiled matrix transposition algorithm and benchmarked it on an HPC cluster to evaluate the impact of tile size on performance. Results show an optimal tile size near 8–16 elements, depending on cache alignment and prefetching behavior. Larger matrix sizes revealed performance degradation once data size exceeded L3 cache limits.

### 2. Matrix Multiplication
Compared three versions of matrix multiplication:
- **Naïve**
- **Tiled**
- **Transposed**

Both tiled and transposed implementations showed a 2–3× speedup over the naïve version. Performance was comparable between tiled and transposed due to improved spatial locality via transposing matrix B.

### 3. Basic OpenMP
Parallelized simple loops computing squares and primality tests using OpenMP. Multi-threaded versions showed significant speedups, especially for the less complex "squares" computation, with diminishing returns at 4 threads due to coordination overhead.

## Concepts & Skills Demonstrated

- Cache-aware programming: tiling and data locality
- Performance benchmarking across matrix sizes and cache levels
- Matrix multiplication optimization
- Introductory OpenMP (`#pragma omp parallel for`)
- Parallel speedup and efficiency analysis

## System & Tools

- Intel Xeon E5-2670 v2 CPUs (Campus Cluster)
- C++17, CMake
- SLURM job scheduler
- Singularity container for reproducible benchmarking
- OpenMP for thread-level parallelism

## 📬 Requesting Access

This project was completed as part of a graduate-level parallel programming course. To comply with academic integrity policies, the full source code is stored in a private repository.

If you would like access to the code for learning, evaluation, or portfolio review purposes, please reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-matrix-ops)

When emailing, **please include the phrase "Access Request – hpc-matrix-ops" in the subject line** so I can respond promptly.  
I’m happy to grant access provided the intended use is consistent with academic integrity guidelines.
