## What is CUDA?
Compute Unified Device Architecture (CUDA) is both a parallel computing platform and a programming model that allows users to use GPUs for general purpose comuting.

When talking about CUDA one can mean architecture framework behind using and operating GPUs. 


---
### 1.1 CUDA Toolkit
Nvidia CUDA toolkit is a complete development environment that allows programmers to use GPUs for general purpose computing.

It provides essential tools such as `cuBLAS`, `cuDNN`, performance profilers, compiler (NVCC) and runtime

### 1.2 Cuda Python 
Nvidia Cuda python brings GPU compute to python, the de-facto language for modern data science.

- cuPy a SciPy and numpy standin for GPU computing with python
- Numba a python compiler by anaconda to compile python code on CUDA capable GPUs


---
### 1.3 CUDA-X libraries
A plethora of libraries that brings the power of GPU to everyday compute tasks.

### 1.3.1 Cuda Math
| CUDA library | Description | Column3 |
| --------------- | --------------- | --------------- |
| cuBLAS | Basic Linear algebra | Item3.1 |
| cuFFT | Fast Fourier transform | Item3.2 |
| cuRAND | Random number generation ||
| cuSOLVER | Dense and sparse direct solvers ||
| cuSPARSE | BLAS for sparse matrices ||
| cuTensor | tensor accelerated linear algebra ||
| cuDSS | direct sparse solver ||
| CUDA Math API | standard math operations ||
| nvmath-python | (beta) standard math operations ||
| AmgX | linear solvers for simulations and implicit unstructured methods ||

#### 1.3.1 RAPIDS
RAPIDS brings GPU to typical data science operations, with drop in libraries for the following frameworks.

| Data science framework | RAPIDS equivalent | docs |
|---|---|---|
| Python | cuDF | [docs](https://docs.rapids.ai/api/cudf/stable/) |
| Numpy & SciPy | cuPy | [docs](https://docs.cupy.dev/en/stable/) |
| Sklearn | cuML | [docs](https://docs.rapids.ai/api/cuml/stable/) |
| NetworkX | cuGraph| [docs](https://docs.rapids.ai/api/cugraph/stable/) |
| dask | `dask_cuda`| [docs](https://docs.rapids.ai/api/dask-cuda/stable/) |
| spark | `spark-rapids` | [docs](https://nvidia.github.io/spark-rapids/) |

### 1.3.2 Deep Learning Core libraries
Nvidia CUTLASS - base linear algebra and tensor operations across CUDA's execution and memory hierachy
TensorRT-LLM - deep learning inference optimizer for production deployments
    - optimizer provides for both `post training quantization` and `quantization aware training`
CUDA Deep Neural Network library (CuDNN) - a library of GPU accelerated primitives for deep neural networks. CuDNN provides implementations of standard routines such as forward or backward convolution, matmul, pooling and normalization.
    - Popular deep learning frameworks like Pytorch and Tensorflow already use CuDNN as part of their code.
    - CuDNN SDK's are available in `python` and `C++`, and is split into `frontend` and `backend` api's
        - frontend - abstraction layer with the more common deep learning operations
        - backend - lower level more legacy C level interface


---
### 1.4 Nsight Developer tools
A set of libraries that enable developers to build, debug, profile and develop software on GPUs
- 



---
### 1.5 CUDA Tile
A programming abstraction that is meant to be intuitive to `python` and `C++` users, to remove overhead of managing memory hardware.

Developers operate on `NIVIDIA cuTile`, specify operations on chunks of data rather than managing threads.
- CUDA Tile was launched with CUDA 13.1
- `cuTile` is a virtual instruction set for tile based parallel programming
    - moves away from single-instruction multiple threads (SIMT) as a programming model
- CUDA developers can focus on the `cuTile` as the base abstraction and not worry about memory management
    - builds on other libraries like `NVIDIA CUTLASS` and `NVIDIA CUDA-X`


