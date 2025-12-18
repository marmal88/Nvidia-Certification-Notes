



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
    - GPU intensive applications like CAD, rendering and AI
- Virtual Desktop (vPC) - [docs](https://www.nvidia.com/en-us/data-center/virtual-pc/?ncid=no-ncid)
    - workloads for general business users (e.g. windows, video streaming)
- Application streaming (vApps) - [docs]()
    - Application virtualization similar to Citrix or Remote Desktop Session Host (RDSH)

Benefits:
- performance indistinguisable from bare metal
- management and monitoring
- optimizes resource utilization
- responsive to evolving team requirements

