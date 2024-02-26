# cuda_masterclass
Cuda MasterClass code base from Udemy

## Section 1: Introduction to CUDA programming and CUDA programming models

### Introduction to parallel computing

- **Process**: A process is an instance of a computer program that is being executed.

- **Context**: Collection of data about process which allows processor to suspend or hold the execution of a process and restart the execution later.

- **Thread**:
  - Thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler.
  - Thread is component of a process. Every process have at least one thread called main thread which is the entry point for the program.

- **Parallelism**
  - Task Level Parallelism: Asign different task on same or different data. Each worker execting different tasks.
  - Data Level Parallelism: Same task on different data. Each worker doing the same task simutanously, but each of them are working with different data.

- **Parallelism vs. Concurrency**

- **Super computing, heterogenous computing and GPU**

- **CUDA**: (Compute Unified Device Architecture) is a parallel computing platform and application programming interface(API) model creted by Nvidia.

- **GPGPU**: General Purpose Computing in Graphic Processing Unit

