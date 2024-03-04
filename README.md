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

### Introduction for CUDA programs
[kernel.cu](section_1_introduction/kernel.cu) is a template and automatically generated by Visual Studio when a CUDA project created.

- **Basic steps of CUDA program**
  - Initialization of data from CPU
  - Tranfer data from CPU context to GPU context
  - **Kernel launch with needed grid/block size**
  - Transfer results back to CPU context from GPU context.
  - Reclaim the memory from both CPU and GPU.

- **Elements of CUDA program**
  - **Host code (main function)** -> code that is going to run in CPU
  - **Device code** -> code that is going to run in GPU
    - `__global__ void hello_cuda(int x, ...)`
    - Modifier: device code must have modifiers such as `__global__`, `__host__`, `__device__`
    - Return type: device code must has `void` return type. If you want to return some variables from kernel, you have to explicitly tranfer those memories using specific CUDA runtime function calls.
    - Call kernel function: `hello_cuda << <1,1 >> > ();` you have to specify kernel launch parameters

- **Grid & Block**
  - **Grid**: is a collection of all the threads launch for a kernel
  - **Block**: Threads in a grid organized in to groups called thread blocks.