# Parallel Primes and Gauss-Seidel Synchronization

This project demonstrates two core concepts in parallel programming: scheduling strategies in OpenMP and synchronization in tiled Gauss-Seidel iterations. Both components were benchmarked on an HPC cluster to evaluate performance trade-offs across thread counts and tile sizes.

## Overview

### 1. Parallel Prime Computation

The first task involved benchmarking a parallel prime-checking loop under different OpenMP scheduling strategies: `static`, `dynamic`, and `guided`. Each was tested using 1 to 8 threads.

- **Dynamic scheduling** performed best overall, maintaining high parallel efficiency (~0.95–1.0) with 2–4 threads before tapering off at higher thread counts.
- **Static scheduling** showed reduced efficiency due to uneven workload distribution in this compute-heavy task.

### 2. Gauss-Seidel Synchronization

The second part involved synchronizing a parallel implementation of the Gauss-Seidel iterative method for solving systems of equations. Each thread was required to wait for the thread processing the tile directly above its own before proceeding.

- Implemented efficient inter-thread synchronization to preserve correctness.
- Benchmarked execution time across multiple tile sizes (2–64 elements) and thread counts (1–8).

#### Key Findings:

- **Tile size = 4** produced the fastest execution time, likely due to cache alignment (64-byte cache lines, 8-byte doubles).
- Performance gains plateaued at 4–8 threads due to increased coordination overhead.
- Even at maximum threads, parallel performance remained faster than the serial baseline.

## Concepts & Skills Demonstrated

- OpenMP scheduling (`static`, `dynamic`, `guided`)
- Parallel efficiency and thread scaling
- Inter-thread synchronization strategies
- Cache-conscious tiling (aligned to cache line size)
- Performance benchmarking using SLURM on an HPC cluster

## System & Tools

- Intel Xeon E5-2670 v2 CPUs (Campus Cluster)
- C++17, OpenMP
- SLURM job scheduler
- Singularity container for consistent benchmarking

## 📬 Requesting Access

This project was completed as part of a graduate-level parallel programming course. To comply with academic integrity policies, the full source code is stored in a private repository.

If you would like access to the code for learning, evaluation, or portfolio review purposes, please reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-primes-gs)

When emailing, **please include the phrase "Access Request – hpc-primes-gs" in the subject line** so I can respond promptly.  
I’m happy to grant access provided the intended use is consistent with academic integrity guidelines.
