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
  - [SimSYCL: A SYCL Implementation for Development, Testing and Simulation](#simsycl-a-sycl-implementation-for-development-testing-and-simulation)
  - [Extending Sylkan with Local Storage Support](#extending-sylkan-with-local-storage-support)
  - [Static Analysis of SYCL Compute Kernels to Determine Data Access Mapping Functors](#static-analysis-of-sycl-compute-kernels-to-determine-data-access-mapping-functors)

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
* Mismatches between the specified access mode of buffers and the actual accesses performed
* Detect invalid reference captures in host command groups

**Prerequisites**:
* Solid C and C++ knowledge
* Some experience with compiler development is advantageous


## SimSYCL: A SYCL Implementation for Development, Testing and Simulation

The Khronos [SYCL API](https://www.khronos.org/sycl) has several implementations, but they
are primarily designed for high performance on specific hardware. They often require heavy
compilation infrastructure, which increases development times, and their performance focus
can make debugging harder.

The goal of this thesis is to design and develop a SYCL implementation which is focused on
fast compilation, development and testing. It should function as a library-only,
single-threaded implementation of the SYCL standard with minimal dependencies.
Additional features designed for these use cases should be provided, such as the ability to 
simulate executing the program on hardware devices with different properties for functional
(but not performance) testing.

Additionally, the compile times and capabilities of the developed implementation should be
evaluated on a set of standard SYCL code bases.

**Prerequisites**:
* Solid C++ knowledge
* Some prior understanding of GPU/accelerator computing is advantageous, but not strictly necessary


## Extending Sylkan with Local Storage Support

[Sylkan](https://dl.acm.org/doi/10.1145/3456669.3456683) is a prototype implementation of the
Khronos [SYCL API](https://www.khronos.org/sycl) targeting any device which supports 
[Vulkan](https://www.vulkan.org/) compute.

The goal of this thesis is to update Sylkan towards newer versions of the SYCL standard,
while also developing support for a variety of missing features. The most important of these
is local storage, which should be mapped to the equivalent Vulkan features.

A comprehensive evaluation across several different target hardware platforms should also be
performed, with a particular focus on comparing the performance to existing SYCL implementations
on platforms which support both Vulkan and other SYCL backends.

Development and testing infrastructure will be made available by the DPS group.

**Prerequisites**:
* Solid C++ knowledge
* Some prior understanding of GPU/accelerator computing is advantageous
* Some experience with compiler development is advantageous


## Static Analysis of SYCL Compute Kernels to Determine Data Access Mapping Functors

In the [Celerity](https://celerity.github.io) system, programmers are required to specify
the data dependencies of compute kernels via a mechanism known as
[Range Mappers](https://celerity.github.io/docs/range-mappers). While some higher-level
abstractions exist to simplify this task, it still, in principle, represents a duplication of
information which already exists within the computation itself -- and like any such duplication,
it introduces a productivity overhead in development and maintenance.

The goal of this thesis is to research, design and implement an algorithm which statically
analyzes kernels, and implicitly derives the required range mappers from this analysis.
Note that the expectation is that this will only be possible for a subset of kernels fulfilling
certain regularity criteria.

**Prerequisites**:
* Solid C and C++ knowledge
* Some experience with compiler development is advantageous
