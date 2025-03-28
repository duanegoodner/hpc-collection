# Parallel Gas Simulation with MPI and AMPI

This project simulates a two-dimensional molecular dynamics system—specifically Argon gas particles—using both MPI and AMPI for distributed-memory parallelization. It demonstrates key HPC concepts including domain decomposition, ghost particle exchange, inter-process communication, and load balancing.

## Overview

### Part 1: MPI-Based Simulation
Implemented a parallel version of a Van der Waals gas simulation across a 2D grid using **MPI**. Each simulation region (or "block") is assigned to a unique MPI rank. At fixed intervals, ranks exchange particles that have migrated beyond their boundaries and share ghost particles with neighbors for accurate edge computations.

**Key components:**
- `exchange_particles()`: Transfers particles that migrated out of bounds to neighboring ranks.
- `communicate_ghosts()`: Shares nearby particles with neighboring ranks for boundary calculations.
- Custom MPI datatypes were used for efficient structured communication.

### Part 2: AMPI and Load Balancing
Used **AMPI**, a Charm++-based system that allows over-decomposition of work and automatic load balancing. The simulation was configured with virtual processors, and a `GreedyRefine` strategy was used for load migration.

- Exchange frequency was increased to reduce overhead (20 cycles vs. MPI’s 7).
- AMPI’s lightweight threading model allowed better performance in oversubscribed CPU configurations.

### Part 3: Benchmarking and Performance Analysis
Benchmarked both MPI and AMPI implementations on an HPC cluster using 1 to 36 CPU cores, and across one and two physical compute nodes.

**Findings:**
- **MPI (1 node)** outperformed **MPI (2 nodes)** due to lower communication latency.
- **AMPI** was fastest at lower core counts due to lightweight threads and less overhead.
- **Speedup for MPI** scaled better at higher core counts, while **AMPI** gains plateaued due to thread coordination overhead.

## Concepts & Skills Demonstrated

- MPI point-to-point communication and structured datatypes
- Ghost cell exchange patterns in 2D grid-based simulations
- Performance tradeoffs between MPI and AMPI
- Load balancing using Charm++ strategies
- Benchmarking and scalability analysis on distributed systems

## System & Tools

- Intel Xeon E5-2670 v2 CPUs (Campus Cluster)
- MPI and AMPI (Charm++ v6.9.0)
- SLURM job scheduler
- C++17, CMake, custom MPI types
- Visualized performance trends using time vs. CPU core count and speedup plots

## 📬 Requesting Access

This project was completed as part of a graduate-level parallel programming course. To comply with academic integrity policies, the full source code is stored in a private repository.

If you would like access to the code for learning, evaluation, or portfolio review purposes, please reach out:

📧 [dmgoodner@gmail.com](mailto:dmgoodner@gmail.com?subject=Access%20Request%20–%20hpc-gas-sim)

When emailing, **please include the phrase "Access Request – hpc-gas-sim" in the subject line** so I can respond promptly.  
I’m happy to grant access provided the intended use is consistent with academic integrity guidelines.
