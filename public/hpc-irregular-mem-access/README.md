# Irregular Memory Access and Compiler Optimizations

This project explores the performance implications of memory access patterns and compiler optimizations on modern CPU architectures.

## Overview

The assignment is divided into two parts:

### Part 1: Irregular Memory Access
Benchmarks were run on a program that performs pseudorandom accesses to elements of a large array. The goal was to analyze how execution time is affected by array size and CPU cache behavior. Results show a sharp increase in access time when the total array size exceeds the 64KB L1 cache limit, highlighting the impact of cache misses on performance.

### Part 2: Compiler Optimization Effects
Five short C++ programs were compiled and benchmarked using `-O0` (no optimization) and `-O3` (aggressive optimization) flags. Execution times were recorded for each version, demonstrating how optimization can dramatically improve runtime performance—especially in compute-heavy or memory-bound code.

## Concepts & Skills Demonstrated

- Memory hierarchy and spatial/temporal locality
- Effects of CPU cache on performance
- Benchmarking using SLURM and a Singularity container
- Compiler optimization flags (`-O0` vs. `-O3`)
- Interpreting performance results using timing data

## System & Tools

- Intel Xeon E5-2670 v2 CPUs (Campus Cluster)
- CMake & C++17
- SLURM job scheduler
- Singularity container for controlled benchmarking environment

## 📬 Requesting Access

This project was completed as part of a graduate-level parallel programming course. To comply with academic integrity policies, the full source code is stored in a private repository.

If you would like access to the code for learning, evaluation, or portfolio review purposes, please reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-irregular-mem-access)

When emailing, **please include the phrase "Access Request – hpc-irregular-mem-access" in the subject line** so I can respond promptly.  
I’m happy to grant access provided the intended use is consistent with academic integrity guidelines.
