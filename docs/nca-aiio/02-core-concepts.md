# Core concepts


## Topics covered in the exam include:
According to the website (11/12/25) the following topics are covered during the exam
- Accelerated computing use cases
- AI, machine learning, and deep learning
- GPU architecture
- NVIDIA’s software suite
- Infrastructure and operation considerations for adopting NVIDIA solutions

## Prerequsite
Readings
- Difference between AI, ML and DL [link](https://blogs.nvidia.com/blog/difference-deep-learning-training-inference-ai/)
- Difference between deep learning training and inference [link](https://blogs.nvidia.com/blog/difference-deep-learning-training-inference-ai/)
- Recommender systems [link](https://blogs.nvidia.com/blog/whats-a-recommender-system/)
    - Nvidia Merlin recommender application framework GPU accelerated recommender system



## Other recommended readings
- What is cuda all about anyway [link](https://www.nvidia.com/en-us/on-demand/session/gtc25-S72571/)
    - base unit of compute - streaming multiprocessor (SM)
    - each SM comprise of 4 execution units, each able to execute a **warp** (32 threads of individual CUDA cores)
    - all threads running on the SM utilize the same L1 cache, which functions as the user controlled shared memory.
    - hierachical execution model
        - grid to represent all work to be done
        - grid to be compised of many blocks with **equal** number of treads
        - threads within the same block execute the same code. They operate independently but can synchromize to exchange data.

