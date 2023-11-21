This repository contains an up-to-date list of theses topics [I (Peter Thoman)](https://dps.uibk.ac.at/~petert/)
am currently interested in supervising as part of the CS bachelor and master programs at UIBK.  
Contact me if you are interested in any of these.

**Note** that, while these topics are grouped into Bachelor and Master levels, it's certainly possible
for sufficiently motivated bachelor students to attempt theses at the Master level. The opposite
may also be possible if you have ideas on how to substantially extend a given topic.

- [Bachelor Theses Topics](#bachelor-theses-topics)
  - [Intel Level-0 Backend for Celerity](#intel-level-0-backend-for-celerity)
  - [AMD ROCM Backend for Celerity](#amd-rocm-backend-for-celerity)
- [Master Theses Topics](#master-theses-topics)
  - [Improving the Tracy Profiler for Distributed Memory Applications](#improving-the-tracy-profiler-for-distributed-memory-applications)
  - [A Clang/LLVM Compiler Plugin to Improve the User Experience in SYCL and Celerity](#a-clangllvm-compiler-plugin-to-improve-the-user-experience-in-sycl-and-celerity)

# Bachelor Theses Topics

## Intel Level-0 Backend for Celerity

[Celerity](https://celerity.github.io) is a C++ API and runtime system for programming multi-GPU
applications, primarily for GPU clusters. It is based closely on the industry-standard Khronos
[SYCL API](https://www.khronos.org/sycl).

It features a basic, general SYCL execution backend, and a more optimized (but
vendor-specific) CUDA backend. The goal of this thesis is to implement, test and evaluate a new
[Intel Level-0](https://dgpu-docs.intel.com/technologies/level-zero.html) backend for Celerity.
Primarily, this will require work platform-specific features such as strided data transfers.

Development and testing infrastructure will be made available by the DPS group.

**Prerequisites**:
* Solid C++ knowledge
* Some prior understanding of GPU/accelerator computing is advantageous, but not strictly necessary


## AMD ROCM Backend for Celerity

[Celerity](https://celerity.github.io) is a C++ API and runtime system for programming multi-GPU
applications, primarily for GPU clusters. It is based closely on the industry-standard Khronos
[SYCL API](https://www.khronos.org/sycl).

It currently features a basic, general SYCL execution backend, and a more optimized (but 
vendor-specific) CUDA backend. The goal of this thesis is to implement, test and evaluate a new
[AMD ROCM](https://www.amd.com/en/products/software/rocm.html) backend for Celerity.
Primarily, this will require work platform-specific features such as strided data transfers.

Development and testing infrastructure will be made available by the DPS group.

**Prerequisites**:
* Solid C++ knowledge
* Some prior understanding of GPU/accelerator computing is advantageous, but not strictly necessary


# Master Theses Topics

## Improving the Tracy Profiler for Distributed Memory Applications

[Tracy](https://github.com/wolfpld/tracy) is a modern hybrid tracing/sampling real-time profiler.
It captures a timeline of zones, events and additional information which can be inspected in 
detail in a high-performance UI easily capable of handling millions of events.

Currently, Tracy is primarily designed for profiling single processes running on one machine.
The goal of this thesis is to design and implement improved support for distributed memory 
applications in Tracy. This could be achieved either by a full redesign which handles data from
multiple nodes in a single UI instance, or by providing a better integration for inspecting
several communicating processes in individual instances.

**Prerequisites**:
* Solid C and C++ knowledge
* An understanding of the basics of application profiling
* Some experience with distributed memory programming (i.e. HPC)


## A Clang/LLVM Compiler Plugin to Improve the User Experience in SYCL and Celerity

[Celerity](https://celerity.github.io) is a C++ API and runtime system for programming multi-GPU
applications, primarily for GPU clusters. It is based closely on the industry-standard Khronos
[SYCL API](https://www.khronos.org/sycl).

The goal of this thesis is to design, develop and evaluate a plugin for the Clang/LLVM compiler
infrastructure which identifies common error patterns. Some of these patterns can be recognized
at the library level, which Celerity attempts (e.g. warnings about specific types of capturing),
however, others require more static analysis.

*Examples*:
* Mismatches 

**Prerequisites**:
* Solid C and C++ knowledge
* An understanding of the basics of application profiling
* Some experience with distributed memory programming (i.e. HPC)
