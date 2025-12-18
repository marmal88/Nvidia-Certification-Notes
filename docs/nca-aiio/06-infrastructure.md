



## Nvidia Data Center GPU Manager `DCGM`
Is a suite of tools for managing Nvidia Data Center GPUs in a cluster environment
    - Available on Linux `x86_64` and `aarch64`
    - Offers two interfaces `dcgmi` and `DCGM exporter` to interact with cluster
        - DCGM exporter allows for the monitoring of resources by exporting GPU metrics
        - dgcmi is a CLI tool to manage and monitor cluster GPU resources


## Nvidia vGPU
Nvidia virtual GPUs creates virtual GPUs to be shared across virtual machines. [docs](https://www.nvidia.com/en-us/data-center/virtual-solutions/)  
    - Able to aggregate GPUs and allocate resources to machines based on workload type

Editions (3 available):
- Virtual Workstations (vWS) - [docs](https://www.nvidia.com/en-us/design-visualization/virtual-workstation/?ncid=no-ncid)
    - Use cases include AI training and 
- Virtual Desktop (vPC) - [docs](https://www.nvidia.com/en-us/data-center/virtual-pc/?ncid=no-ncid)
- Application streaming (vApps) - [docs]()
    - GPU intensive applications like CAD and 

