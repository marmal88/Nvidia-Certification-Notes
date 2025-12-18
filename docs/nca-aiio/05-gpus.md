
# Multi Instance GPU (MIG)
With MIG mode users can run jobs in parallel on multi instances of GPUs on the `Ampere` architecture.
- MIG partions a single NVIDIA A100GPU into up to 7 independent GPU instances
- each part runs fully isolated with each own designated memory cache and streaming multiprocessors
- allows users to create the mix that is right for their workloads

## Message Parsing Interface (MPI)
MPI is a standardized and portable API for communicating data via messages.
    - MPI is compatible with (CUDA/CUDA Fortran/OpenACC).
    - MPI is a communication library for parallel computing and distributed tasks

Issues that MPI is trying to address:
    - limitations of a single node compute workload
    - data size too larget to fit into single GPU
    - allows single-node multi GPU application to scale across multiple nodes

Implementation of CUDA-aware MPI was simplified by Unified Virtual Addressing (UVA) in CUDA 4.0 – which enables a single address space for all CPU and GPU memory. 

CUDA-aware implementations of MPI have several advantages:
- CUDA-aware MPI is relatively easy to use
- Applications run more efficiently with CUDA-aware MPI
    - Operations that carry out the message transfers can be pipelined
    - CUDA-aware MPI takes advantage of best GPUDirect technology available


## NVIDIA Collective Commuication Library (NCCL) pronounced "Nickel"
Provides inter-GPU communication primitives (collective operations) that are topology aware and can be easily intergrated into applications. 
- NCCL routines, are optimized over PCIe, Nvidia NVLink and other interconnects 
- Plain english guide to collective operations [link](https://dev.to/lewis_won/from-scatter-to-all-reduce-a-plain-english-guide-to-collective-operations-1695)
    - `broadcast` - sends the same information to designated ranks
    - `all-gather`
    - `all-reduce` - receives information from designated ranks and broadcast to all ranks
    - `reduce` - aggregates the results from different ranks by specified operation (e.g. sum, max, min)
    - `reduce-scatter`
    - p2p send/receive comms - `all-to-all` - 
    - p2p send/receive comms - `gather` - receives parts of the information from designated ranks (reverse of scatter operation)
    - p2p send/receive comms - `scatter` - sends part of the information to designated ranks
- single kernel implementation
 
Benefits:
- `Ease of programming` - simple `C` API that can be accessed from other programming languages
- `Performance` - developers can scale accross nodes without having to configure specific hardware configurations
- `Compatibility` - NCCL is compatible with any multi-GPU parallelization model. Including single-threaded, multi-threaded (one thread per GPU) and multiprocess (MPI combined with multi-threaded operations)

## Communication between GPU
Large language models require multiple GPUs to work, to obtain higher performance splitting the model using tensor parallel (TP) is required.

GPU bottleneck:
- Each GPU must complete their work independently, but must send their results back to every other GPU (all-to-all reduction)
- Minimizing time spent between at the communication layer means GPUs are not idle

Parts of the NVIDIA multi-GPU communications layer
- `NVLink` being the direct, high-speed GPU-to-GPU GPU-to-CPU link
    - 7x the bandwidth of PCIe Gen5 used in conventional x86 servers
    - `NVLink C2C` - is a board level `chip-to-chip` interconnect (e.g. connect Grace CPU with Hopper GPU to create Grace Hopper superchip)
- `NVLink Switch` - acts as a central bi-directional switch to connect many GPUs for all-to-all communication
    - direct point-to-point communication between GPUs, mean each GPU needs to divide its connectivity into as many connections
    - by routing GPUs to `NVLink` switches the overall communication speed is not reduced, but GPU traffic can still be routed
    - the addition of NVLink switch increases cost but also increases overall GPU communication speed
- `NVLink Fusion` extending this ecosystem to integrate custom CPUs and accelerators into a unified, scalable fabric for flexible, hyperscale AI infrastructure
    - 
