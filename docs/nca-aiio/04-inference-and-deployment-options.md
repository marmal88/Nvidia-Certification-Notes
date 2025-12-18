## 2. NVIDIA NGC Catalog
NGC is a portal of enterpise software managemet tools to support end-to-end AI and digital twin workflows

NGC consists of 
- NVIDIA NeMo - suite of tools to build, monitor and optimize agents across their lifecycles
- BioNemo - suite of tools for biotech research (clara family of open source models for biomed research)
- Riva Studio - customizable ai voice agents (automatic speech recognition, text to speech, neural machine translation) 
- NGC private registry
    - unified catalogue of GPU optimized containers, pre-trained models, SDK's and helm charts
    - Nvidia NIM (Neural Inference Microservices) - GPU optimized docker containers


---
## 3. Triton Inference Server
Triton Inference server allows teams to deploy any AI model across frameworks and across devices. 

### 3.1.1 Features
- Current frameworks supported: `TensorRT`, `Pytorch`, `ONNX`, `OpenVino`, `RAPIDS FIL`, `vLLM` and more
- Current devices supported: `x86`, `ARM`, `CPU` and `AWS inferentia`
- Built in `readiness` and `liveness` checks for integration into Kubernetes
    - can deploy Triton inference server with K8s with Helm on `GCP`, `AWS`, `Nvidia fleet command`
- Built in `HTTP/Rest` or `GRPC` endpoints

### 3.2 Dynamo-Triton
The Triton inference server has been incorporated into Nvidia Dynamo platform with the new name Dynamo Triton.

#### 3.2.1 Dynamo Platform
NVIDIA Dynamo platform is a open source low latency and modular framework for serving generative AI models in distributed environments. 

Nvidia Dynamo supports AI inference backend (e.g. mistralrs, cuda) and features LLM specific optimzations (e.g. disaggregated serving)

Dynamo addresses the challenges of distributed and disaggregated inference serving via the 4 components
- GPU resource planning - Plans and schedules GPU resources in multi-node deployments to allocate them across pre-fill and decode
- Smart router - KV- cache aware routing engine that efficiently directs incoming traffic across large GPU fleets in multi-mode deployment
- Low latency communications library - inference data transfer library that accelerates the transfer of KV cache between GPUs and different memory and storage types
- KV cache manager - cost aware KV cache offloading engine designed to transfer KV cache across various memory hierachy freeing up GPU

![dynamo platform](./assets/dynamo_platform.png)

---
## 4. Robotics and Edge AI


### 4.1 Embedded Devices
#### 4.1.1 NVIDIA Thor
Delivers over 2070 FP4 TFLOPS of AI compute and 128 GB of memory with power configurable between 40W and 130W

Comes with:
- NVIDIA ISSAC ROS - autonomous mobile robots
- NVIDIA Metropolis - video analytics with AI agents
    - deploy interactive AI agents that can interact with video to do analytics
    - derive richer insights from existing video feed
- NVIDIA Holoscan - sensor processing 

#### 4.1.2 NVIDIA Jetson Orin


### 4.2 NVIDIA OMNIVERSE
OpenUSD - is a OSS framework for creating, simulating and collaborating in 3D worlds
    - framework allows developers to control and curate 3D assets in a 3D scene 
    - developed by Pixar studios, now central to Nvidia Omniverse
NVIDIA Omniverse - is a platform of API's and SDKs that enable developers to integrate OpenUSD and NVIDIA RTX (raytracing) into software tools and simulation workflows 
    - building 3D applications and services on Universal Scene Description (OpenUSD) and NVIDIA RTX (Real time raytracing)
    - 
NVIDIA ISSAC - is a OSS framework built on NVIDIA OMNIVERSE that enables developers to simulate/test robotic solutions in a virtual environment
    - ROS - for autonomous mobility development
    - GR00T - for humanoid robots
    - SIM - for interacting with Nvidia Omniverse 3D assets


