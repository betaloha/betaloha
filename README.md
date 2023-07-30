# Korakit Seemakhupt
<img src="korakit_small.JPG"
     alt="Korakit's photo"
     align="right"/>      
I am a fifth-year Ph.D. student in the Department of Computer Science at the University of Virginia. I am advised by Prof. Samira Khan. My research focuses on computer network, storage system, real system prototyping of emerging technologies and studing of Remote Procedure Calls in a large scale system. Before that, I worked with Lumio 3D Co., Ltd. I received my B.Eng and M.Eng degrees from Chulalongkorn University in 2014 and 2016 respectively.

## Research

### Acceleration of crash consistency support for persistent memory with Near-data processing [Eurosys'23]
To avoid the overhead from software context switching and redirection, PM programs usually access the memory directly--bypassing the file system. Consequently, PM programs are responsible for providing crash consistency which increases the overhead of program execution. One of the solutions is to offload crash consistency processing to a processor close to the PM such as a PM controller in the Optane DCPMM. However, there is a wide array of crash consistency techniques, and crash consistency support execution is serialized with the execution of the program's logic. Thus, the overhead from naively offloading crash consistency support to dedicated hardware offsets the performance benefits. In this research, we have made two important observations: 1. seemingly different crash consistency support techniques, share common sub-operations, and 2. the execution of crash consistency support operations and PM program's logic can be parallelized, but they need to be committed in-order. We evaluate the whole system on real hardware using our FPGA evaluation platform.

### Supports for in-network data persistence at datacenter scale [ISCA'21]
The recent adoption of fast local storage systems such as persistent memory drastically reduces the latency of accessing data locally. However, the latency between application logic processing and storage backends, which are typically placed in separate server racks in a typical data center, is significant. While there are attempts that mitigate the latency of the network stack such as optimizing RPC processing or move the processing of stateless read requests into network devices, server processing is still a major part of the round-trip latency. With such observation, our research, PMNet adds persistent memory to persist update requests in network devices to provide **in-network data persistence** and move the server off the critical path of update requests while tackling challenges in common datacenter such as packet loss, hardware failure, and multi-path problems.


### Recovery testing of persistent memory program [ASPLOS'20]
Data recoverability of PM programs depends on the correct behavior of PM programs both post-failure and post-failure. Specifically, the post-failure (recovery) program can only access a crash-consistent copy of data created by a pre-failure program. In this research, we develop a run-time software tool that performs automated testing of all potential failure points in the pre-execution program and detects an associate access violation of the post-failure program. We evaluate our tool on a real system using real workloads based on PMDK's libpmemobj.

### Optimization of persistent memory's backend memory operations [ISCA'19]
To effectively utilize emerging persistent memory, the PM system must provide longevity, security, and data integrity. However, operations that provide those supports increase the latency of write access, which cannot be moved off the critical path. Our observations are 1. backend memory operations can be broken down into small sub-operations, and those sub-operations can be parallelized and 2. each backend memory operation only depends on the address and data of write access. Thus, it is possible to pre-execute the backend memory operations. Our researches focus on two approaches for the pre-execution of backend memory operations: 1. software-based pre-execution using LLVM compiler pass and 2. transparent hardware-based approach using execution contexts in the processor.


## Publications

> [vPIM: Efficient Virtual Address Translation for Scalable Processing in-Memory Architectures](https://60dac.conference-program.com/presentation/?id=RESEARCH805&sess=sess158)       
> Amel Fatima, Sihang Liu, **Korakit Seemakhupt**, Rachata Ausavarungnirun, Samira Khan         
> Design Automation Conference (DAC)          
> San Francisco, CA, July 2023.        

> [NearPM: A Near-Data Processing System for Storage-Class Applications](https://dl.acm.org/doi/10.1145/3552326.3587456)       
> Yasas Senevirathne, **Korakit Seemakhupt**, Sihang Liu, and Samira Khan         
> Eighteenth European Conference on Computer Systems (EuroSys '23)          
> Rome, Italy, May 2023.        
> [[pdf]](https://dl.acm.org/doi/10.1145/3552326.3587456), [[Source Code]](https://github.com/Systems-ShiftLab/NearPMHW)
> Artifact Available

> [Write Prediction for Persistent Memory Systems](https://www.cs.virginia.edu/~smk9u/PMWeaver_pact21.pdf)       
> Suyash Mahar, Sihang Liu, **Korakit Seemakhupt**, Vinson Young, and Samira Khan         
> International Symposium on Parallel Architectures and Compilation Techniques (PACT)          
> Virtual, Sep 2021.        
> [[pdf]](https://github.com/betaloha/betaloha/blob/main/PMWeaver_pact21.pdf), [[Source code]](https://pmweaver.persistentmemory.org/)       
> Artifact Available, Artifact Evaluated--Reusable, and Results Reproduced

> [PMNet: In-Network Data Persistence](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA2021.pdf)   
> **Korakit Seemakhupt**, Sihang Liu, Yasas Senevirathne, Muhammad Shahbaz and Samira Khan    
> International Symposium on Computer Architecture (ISCA)   
> Virtual, June 2021.       
> [[pdf]](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA2021.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA21_Full.pptx), [[Video]](https://youtu.be/R72gRpDcNBw), [[Source code]](http://pmnet.persistentmemory.org/)       
> Artifact available at GitHub      

> [Cross-Failure Bug Detection in Persistent Memory Programs](https://www.cs.virginia.edu/~smk9u/liu_xfd_asplos2020.pdf)        
> Sihang Liu, **Korakit Seemakhupt**, Yizhou Wei, Thomas Wenisch, Aasheesh Kolli, and Samira Khan        
> International Conference on Architectural Support for Programming Languages and Operating Systems (ASPLOS)        
> Lausanne, Switzerland, March 2020.        
> [[pdf]](https://www.cs.virginia.edu/~smk9u/liu_xfd_asplos2020.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_ASPLOS20_slides.pptx), [[Summary]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_summary.pdf), [[Video]](https://www.youtube.com/watch?v=SgUeTKfHJDk), [[Source code]](https://xfdetector.persistentmemory.org/)       
> Artifact Available and Artifact Evaluated, Functional, Reproduced     

> [Janus: Optimizing Memory and Storage Support for Non-Volatile Memory Systems](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19.pdf)   
> Sihang Liu, **Korakit Seemakhupt**, Gennady Pekhimenko, Aasheesh Kolli, and Samira Khan    
> International Symposium on Computer Architecture (ISCA)   
> Phoenix, AZ, June 2019.    
> [[pdf]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_slides.pptx), [[Lightning Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_lightning_slides.pptx), [[Video]](https://www.youtube.com/watch?v=kJdgvhLur3M&t=)      
> MICRO TOP PICKS 2020 Honorable Mention        


## Work Experiences

### Google LLC, Research Intern/Student Researcher (2022, 2023)
- RPC Characterization in Google's fleet

### Lumio 3D Co., Ltd. (2016-2018)
- System software and device driver on Nvidia Tegra K1 SoC based system
- Image processing software
- Multi-camera control software

### Chulalongkorn University, Research Assistant (2015-2016)
- Design and implement a printhead controller for an inkjet 3D printer

### Design Gateway Co., Ltd., Intern (2013)
- Integrate and test Ethernet, SATA and HDMI IP on an FPGA
