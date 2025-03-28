# Distributed Histogram Sort with MPI and OpenMP

This project implements a distributed-memory histogram-based sort for 64-bit integers using both MPI and OpenMP. It explores load balancing, parallel quantile estimation, hybrid parallelism, and several MPI communication strategies for performance optimization.

## Overview

### Phase 1: Rebalancing Data

Data are initially distributed unevenly across MPI ranks. The `rebalance()` function redistributes data using:

- `MPI_Allreduce` to calculate global data size
- `MPI_Exscan` for prefix sum offsets
- **One-sided communication** (`MPI_Win_create`, `MPI_Put`) to transfer data directly into remote buffers

The result is a globally balanced dataset across all ranks, ready for parallel processing.

### Phase 2: Histogramming

The `findSplitters()` function computes approximately equal-sized bins using an **iterative quantile estimation algorithm**:

- Ranks sample local quantiles and send them to root via `MPI_Gather`
- Root refines splitter guesses and broadcasts them using `MPI_Bcast`
- Ranks count elements per bin using binary search and return results
- This loop continues until bin counts converge within 1% error

Unnecessary `MPI_Barrier` calls were experimentally removed to significantly reduce runtime (up to 10x improvement).

### Phase 3: Data Movement

The `moveData()` function uses the final splitters to redistribute sorted segments to their correct ranks:

- Local sorted data are split via binary search
- `MPI_Exscan` and `MPI_Reduce` coordinate data offsets
- Final transfer is done with `MPI_Put` into exposed memory windows

Each rank then sorts its received segment locally, completing the global histogram sort.

## Benchmarking & Optimization

- Benchmarked on the Campus Cluster across 1–2 nodes, varying tasks per node
- Compared execution time and time-per-byte across all major phases
- Found **best speedups** with increased task density per node
- Removing `MPI_Barrier` calls significantly improved histogramming phase performance

## Concepts & Skills Demonstrated

- Hybrid parallelism with MPI and OpenMP
- One-sided MPI communication (`MPI_Win_create`, `MPI_Put`)
- Quantile-based histogram binning
- Load balancing and global sorting
- Benchmarking and tuning for distributed systems
- Critical thinking on collective vs. point-to-point communication

## System & Tools

- Intel Xeon E5-2670 v2 CPUs (Campus Cluster)
- C++17, CMake
- MPI (OpenMPI), OpenMP
- SLURM job scheduler
- Custom benchmarking and data visualization

## 📬 Requesting Access

This project was completed as part of a graduate-level parallel programming course. To comply with academic integrity policies, the full source code is stored in a private repository.

If you would like access to the code for learning, evaluation, or portfolio review purposes, please reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-dist-hist-sort)

When emailing, **please include the phrase "Access Request – hpc-dist-hist-sort" in the subject line** so I can respond promptly.  
I’m happy to grant access provided the intended use is consistent with academic integrity guidelines.
