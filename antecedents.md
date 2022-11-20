---
layout: antecedents
title: "Antecedents"
---

## Recent contributions

Our group has recently contributed in the following areas:

*	Implementation of energy efficient Matrix Profile -MP- kernels on embedded accelerators and low-power heterogeneous SoC platforms. 

*	Extension of programming models for heterogeneous architectures with the goal of exploiting advanced parallelization patterns under the state-of-the-art tasks-based parallel execution model, which enables lightweight asynchronous tasks execution. We have demonstrated the benefits of using this paradigm in heterogeneous architectures and low-power SoCs developing the set of libraries HBB -Heterogeneous Building Blocks- (based on oneTBB).

*	Design and evaluation of novel software optimization techniques at runtime for low-power heterogeneous SoC devices that integrate accelerators, including energy-aware scheduling and mapping strategies, selection of the optimal granularity of the chunk of work assigned to each task, or the synchronization mechanisms that minimize overhead.

*	Hardware co-design in embedded heterogeneous SoC to support fine grain parallelization in GPUs, reconfigurable hardware, or in-memory data structures.


## Previous experience of the research team

For 10 years running, our research group has been working on heterogeneous schedulers based on Intel's [TBB library](https://www.threadingbuildingblocks.org/), now called oneTBB, an open source and public domain tool that represents the current state-of-the-art in pattern-based generic parallel programming in C++. Specifically, in these years we have explored several research lines that we summarize below:

* **Heterogeneous programming with GPUs**. Since 2014 we have been collaborating with Dr. Ruben Gran and later with Dr. Dario Suarez developing heterogeneous versions of streaming applications for execution on Intel architectures with integrated GPUs. This first work resulted in a template (C++ template) to implement the heterogeneous pipeline pattern. The supporting runtime was designed incorporating energy-aware task scheduling policies between CPU and GPU.

* **Heterogeneous programming with FPGAs**. In 2015 we started a collaboration with the group led by Dr. José Luis Núñez-Yáñez, from the Dept. of Electrical and Electronic Engineering, University of Bristol, UK. Dr. Núñez-Yáñez is an expert in FPGAs and our collaboration with him focused on adapting our heterogeneous schedulers, designed initially for CPU+GPU, to also work on CPU+FPGA architectures. As a result of a first research stay at the Univ. of Bristol in 2015, we contributed with a heterogeneous implementation of a data streaming algorithm on a system with 4 Intel Haswell cores, an FPGA and two GPUs (one integrated and one discrete). During a second stay in 2016, we investigated how to incorporate to CPU+FPGA platforms, heterogeneous task schedulers that allow dynamic and adaptive load balancing that had already been developed for CPU+GPU platforms. Nine publications resulted from this collaboration.

* **Energy-aware heterogeneous graph processing**. During 2016 and 2017 we have continued to collaborate with researchers Prof. David Padua and Dr. Maria Garzaran from the Dept. of Computer Science at the University of Illinois at Urbana-Champaign, USA, collaboration that has resulted in the publications where we studied the possibility of applying dynamic scheduling techniques on heterogeneous architectures for graph-based algorithms, studying the impact of schedulers on energy consumption for architectures with embedded GPUs.  We have yet to explore the executions of this type of graph-based algorithms in architectures with FPGAs.

* **Load balancing in branch and bound algorithms**. Also during 2016 and 2017, we collaborated with the SAL group of the University of Almeria. In this context, we contributed with a parallel implementation based on TBB of the "Longest Edge selection in Simplicial B&B" algorithm as well as another parallel algorithm able to compute the minimum size of a branch and bound tree. Two journal publications are the result of this collaboration.  We still have to explore the executions in heterogeneous architectures of this type of patterns.

* **Parallelization of robotic applications on heterogeneous architectures**. During this period we also started a collaboration with the MAPIR research group of the Department of Systems Engineering and Automation of the Univ. of Malaga. As a result of a first joint project, we studied the parallelization with TBB of an optimization algorithm based on a triparametric log-logistic model to reduce power consumption on multicore processors for mobile devices, which resulted in two national patents. More recently we have also worked on a new project that aims to design and implement an autonomous navigation algorithm that incorporates the uncertainty of sensors in mobile systems using MDP and POMDP strategies. Given the real-time and energy consumption minimization constraints of these systems, the use of heterogeneous architecture and especially the incorporation of adaptive task schedulers that know how to respond dynamically and efficiently to sensor uncertainties and environmental variations is justified. This collaboration has resulted in two journals and a PhD Thesis.

* **Raising the abstraction level of the programming model**.  Since 2018 we have been collaborating with Dr. José Daniel García on proposals for high-level parallel programming libraries for different parallelism patterns. Dr. Garcia is the representative of Spain in the International ISO C++ Committee and leader of several projects oriented to facilitate the programmability of heterogeneous architectures, such as the GrPPI project. Since its inception we have been working with the DPC++ language that is part of oneAPI. This standards-based solution allows the programmer to reuse the same kernel on different hardware platforms (CPUs and accelerators such as GPUs and FPGAs), as well as to implement in an optimized way inference functionalities based on Deep Learnig on NCE devices. DPC++'s main benefits are portability and productivity, since it allows developing applications in ISO C++, using C and C++ constructors.

* **Technology transfer to local SMEs and international companies**. Prof. Rafael Asenjo has been working with TBB since 2017. Together with James Reinders and Michael Voss, Principal Engineer at Intel, he has given tutorials on Intel TBB at Supercomputing'20, EuroPar'17, Supercomputing'17 and PPoPP'18 and written the latest book on TBB (Pro TBB). Prof. Asenjo participated in a Panel on Intel oneAPI at Supercomputing'20. Along with Angeles Navarro and Denisa Constantinescu, they have published the first paper validating the improvement in programmability due to oneAPI. Rafael and Denisa earned the oneAPI Innovators recognition in 2020. We have also collaborated with Dr. Antonio Vilches while working as SW Engineer at [Shapelets](www.shapelets.io). Together with Dr. Vilches we have published a paper on optimizing time series processing on low power CPU+GPU using heterogeneous schedulers. Shapelets is an Andalusian micro-SME that adds value to the time series processing used by Spanish companies to which this SME provides its services, solving life cycle management problems of complex devices in industrial platforms such as wind turbines and petrochemical platforms, as well as intelligent diagnosis of patients at risk through cardiac signals, etc.


Although it may seems that the research lines of our group have branched out in recent times, the TBB parallel library has been the backbone of our most recent contributions. This library is now integrated into the Intel oneAPI framework and offers a set of high-level methods and templates that focus on exploiting parallelism at the task level. TBB, or oneTBB since it was integrated into oneAPI, presents a fundamental feature that makes it suitable for implementing irregular and heterogeneous applications: the basic scheduler implements a dynamic load balancing strategy (tasks, in this case) based on the work stealing algorithm. Another advantage of oneTBB is that the source code is available and therefore we can modify and adapt it to our needs. Moreover, being a C++ library, it requires only a C++ compiler. This feature has been crucial when porting our oneTBB-based schedulers to different heterogeneous platforms, from Intel (Ivy Bridge, Broadwell, Kaby Lake, HARP), AMD (Kavery), Samsung (Exynos 5 Octa), Altera (Cyclone V) and Xilinx (Zynq 7002, Ultrascale+ MPSoC) processors.  

Finally, oneTBB, and by extension oneAPI, is a multi-resolution programming model, in the sense that you can use high-level templates (parallel_for, parallel_sort, pipeline, Flow Graph, etc.) if they meet your needs, but you can also port an algorithm directly using low-level tasks. Or even build a new high-level template. All this, and especially the Flow Graph template, makes oneTBB a flexible, adaptable and appropriate library to solve the time series problems we are currently tackling in heterogeneous architectures with CPUs, GPUs, FPGAs and NCEs.


## Previous collaborations

* Antonio Vilches, [Shapelets](www.shapelets.io)
* Rubén Gran and Darío Suárez, [Departamento de Informática e Ingeniería de Sistemas, Universidad de Zaragoza](http://webdiis.unizar.es/gaz/index.php)
* J.L. Nunez-Yanez, [Department of Electrical and Electronic Engineering, University of Bristol, UK](http://www.bristol.ac.uk/engineering/departments/eeng/)
* [Rosa Filgueira](https://www.rosafilgueira.com), Data Intensive Research Group at [EPCC -- University of Edinburgh, UK](https://www.epcc.ed.ac.uk/)
* María Jesús Garzarán and David Padua, [Computer Science Department, University of Illinois](http://cs.illinois.edu/)
* Project [Chapel](https://chapel-lang.org) led by Dr. Brad Chamberlain, from [Cray, Inc.](http://www.cray.com/)
* Project Parallel Programming and PGAS languages of the Parallel Programming Models and Tools for Scalable Systems at [IBM T.J. Watson Research Center](https://research.ibm.com) led by Dr. Calin Cascaval
* Project [Cetus](https://engineering.purdue.edu/Cetus/) of the [ParaMount Group](https://engineering.purdue.edu/paramnt/) led by Prof. Rudolf Eigenmann
* Project Vespa led by Dr. Marcelo Cintra
* Project [Galois](https://iss.oden.utexas.edu/?p=projects/galois) led by Prof. Keshav Pingali
* Adrián Tineo Cabello, [Swiss National Supercomputing Centre, CSCS](http://www.cscs.ch/)
