# High Performance Computing Collection

This repository showcases a set of advanced high-performance computing (HPC) projects developed using C++, MPI, and OpenMP, and benchmarked on real-world distributed systems. The projects focus on optimizing memory-bound and compute-intensive workloads through tiling, communication pattern design, parallel synchronization, and hybrid MPI/OpenMP execution.

## 📂 Project Overview

| Project Name | Description |
|--------------|-------------|
| [`hpc-irregular-mem-access`](./public/hpc-irregular-mem-access/README.md) | Explores cache performance in irregular memory access patterns and compiler optimizations. |
| [`hpc-matrix-ops`](./public/hpc-matrix-ops/README.md) | Implements tiled matrix transpose and multiplication with OpenMP loop-level parallelism. |
| [`hpc-primes-gs`](./public/hpc-primes-gs/README.md) | Benchmarks OpenMP scheduling for prime checking and synchronizes a parallel Gauss-Seidel solver. |
| [`hpc-gas-sim`](./public/hpc-gas-sim/README.md) | Simulates 2D molecular dynamics with MPI and AMPI, including ghost particle exchange and load balancing. |
| [`hpc-dist-hist-sort`](./public/hpc-dist-hist-sort/README.md) | Performs a distributed histogram sort using MPI one-sided messaging and quantile-based binning. |

Each project directory includes a detailed summary of methods, performance insights, and the HPC concepts demonstrated.

## 🛠 Technologies Used

- **Languages:** C++17
- **Parallelism:** MPI (OpenMPI), OpenMP
- **Schedulers:** SLURM (Campus Cluster)
- **Environments:** VMFarm, Singularity container
- **Performance Tuning:** Cache optimization, tiling, scheduling strategies, communication pattern design

## 🔐 Code Access

To request access to the source code for portfolio review, collaboration, or evaluation purposes, please email:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-collection)

Just include **"Access Request – hpc-collection"** in your subject line. I'm happy to share, as long as usage aligns with academic integrity guidelines.

🔗 **Note:** Each project is linked as a Git submodule under the `./submodules/` directory. Once collaborator access is granted, you can initialize and pull the code like this:

```bash
git clone https://github.com/duanegoodner/hpc-collection.git
cd hpc-collection
git submodule update --init --recursive
```
If you've already cloned the repo and need to pull submodule changes later, use:
```bash
git submodule update --remote --merge
```
---
