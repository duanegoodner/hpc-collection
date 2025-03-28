# High Performance Computing Collection

This repository showcases a set of advanced high-performance computing (HPC) projects developed using C++, MPI, and OpenMP, and benchmarked on real-world distributed systems. The projects focus on optimizing memory-bound and compute-intensive workloads through tiling, communication pattern design, parallel synchronization, and hybrid MPI/OpenMP execution.

## 📂 Project Overview

| Project Name | Description |
|--------------|-------------|
| [`hpc-irregular-mem-access`](./public/hpc-irregular-mem-access) | Explores cache performance in irregular memory access patterns and compiler optimizations. |
| [`hpc-matrix-ops`](./public/hpc-matrix-ops) | Implements tiled matrix transpose and multiplication with OpenMP loop-level parallelism. |
| [`hpc-primes-gs`](./public/hpc-primes-gs) | Benchmarks OpenMP scheduling for prime checking and synchronizes a parallel Gauss-Seidel solver. |
| [`hpc-gas-sim`](./public/hpc-gas-sim) | Simulates 2D molecular dynamics with MPI and AMPI, including ghost particle exchange and load balancing. |
| [`hpc-dist-hist-sort`](./public/hpc-dist-hist-sort) | Performs a distributed histogram sort using MPI one-sided messaging and quantile-based binning. |

Each project directory includes a detailed summary of methods, performance insights, and the HPC concepts demonstrated.

## 🛠 Technologies Used

- **Languages:** C++17
- **Parallelism:** MPI (OpenMPI), OpenMP
- **Schedulers:** SLURM (Campus Cluster)
- **Environments:** VMFarm, Singularity container
- **Performance Tuning:** Cache optimization, tiling, scheduling strategies, communication pattern design

## 📬 Requesting Access

These projects were completed as part of a graduate-level course in parallel programming. To comply with academic integrity policies, the full source code is stored in private repositories and cannot be made publicly accessible.

If you would like access to any project for **portfolio review**, **learning**, or **evaluation purposes**, feel free to reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-collection)

Please include the phrase **"Access Request – hpc-collection"** in your subject line so I can respond promptly.  
Access is gladly granted as long as the intended use complies with academic integrity guidelines.
