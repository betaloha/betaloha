# Korakit Seemakhupt
<img src="korakit_small.JPG"
     alt="Korakit's photo"
     align="right"/>      
I am a software engineer at Google working in the area of confidential computing. Previously, I was a Ph.D. student in the Department of Computer Science at the University of Virginia and was advised by Prof. Samira Khan. My research focuses on computer network, storage system, real system prototyping of emerging technologies and studing of Remote Procedure Calls in a large scale system. Before that, I worked with Lumio 3D Co., Ltd. I received my B.Eng and M.Eng degrees from Chulalongkorn University in 2014 and 2016 respectively.


## Research

### Memory Efficient RAG for Edge Devices
Deploying Retrieval Augmented Generation (RAG) on resource-constrained edge devices is challenging due to limited memory and processing power.
In this work, we propose addressing the memory constraint by pruning embeddings within clusters and generating embeddings on-demand during retrieval. To avoid the latency of generating embeddings for large tail clusters, the system pre-computes and stores embeddings for these clusters, while adaptively caching remaining embeddings to minimize redundant computations and further optimize latency.

**Key Results: Enable RAG with embedding database 2.31X the memory capacity with TTFT ~1 second and similar generation quality**

### Characterization of Datacenter Communication [SOSP'23]
Remote Procedure Call (RPC) is one of the key enabler of modern scale-out cloud applications. RPC provides location-independent communication and hides the myriad of cloud communication complexities and requirements within the RPC stack. Understanding RPCs is thus one key to understanding the behavior of cloud applications. In this work, to the best of our knowledge, the first large-scale fleet-wide study of RPCs. Our study is conducted at Google, where we measured the infrastructure supporting Google’s user-facing, billion-user web services, such as Google Search, Gmail, Maps, and YouTube, and the information and data management systems that support them. To carry out the study, we examined over 10,000 different RPC methods sampled from over one billion traces, along with statistics collected every 30 minutes over a period of nearly two years. Among other things, we consider the volume, throughput and growth rate of RPCs in the datacenter, the latency of RPCs and their components (the “RPC latency tax”), and the structure of RPC call chains.

**Key Results: The characteristics, scope and complexity of Google's internal production RPCs at hyperscale differ significantly from the assumptions made in prior research.**

### Acceleration of crash consistency support for persistent memory with Near-data processing [Eurosys'23]
To optimize performance, Persistent Memory (PM) programs often bypass the file system and directly access memory. This direct access, however, requires the program to manage crash consistency, which can be computationally expensive. Offloading this task to dedicated hardware, like a PM controller, is a promising approach. However, the diversity of crash consistency techniques and the need for sequential commitment can limit the performance gains.
In this research, we identified two key insights: 1) different crash consistency techniques share common operations, and 2) the execution of crash consistency and program logic can be parallelized, albeit with sequential completion. We validated these findings on a real hardware FPGA platform.

**Key Results: 1.22-1.35X end-to-end speed up for storage applications on FPGA based PIM**

### Supports for in-network data persistence at datacenter scale [ISCA'21]
Recent advancements in storage technologies like persistent memory have significantly reduced local data access latency. However, the network latency between application servers and remote storage backends remains a bottleneck. While techniques like RPC optimization and network device offloading can mitigate network stack latency, server processing still contributes significantly to overall latency.
To address this, our research, PMNet, introduces in-network data persistence by leveraging persistent memory in network devices. This approach removes the server from the critical path of update requests, thereby improving performance. PMNet also addresses common datacenter challenges like packet loss, hardware failures, and multi-path issues.

**Key Results: 1.22-1.35X end-to-end speed up for network storage applications on FPGA based P4 switch**

### Recovery testing of persistent memory program [ASPLOS'20]
Data recoverability of PM programs depends on the correct behavior of PM programs both post-failure and post-failure. Specifically, the post-failure (recovery) program can only access a crash-consistent copy of data created by a pre-failure program. In this research, we develop a run-time software tool that performs automated testing of all potential failure points in the pre-execution program and detects an associate access violation of the post-failure program. We evaluate our tool on a real system using real workloads based on PMDK's libpmemobj.

**Key Results: Our tools found three previously unknown bugs in industry-standard PMDK library**

### Optimization of persistent memory's backend memory operations [ISCA'19]
To effectively utilize emerging persistent memory, the PM system must provide longevity, security, and data integrity. However, operations that provide those supports increase the latency of write access, which cannot be moved off the critical path. Our observations are 1. backend memory operations can be broken down into small sub-operations, and those sub-operations can be parallelized and 2. each backend memory operation only depends on the address and data of write access. Thus, it is possible to pre-execute the backend memory operations. Our researches focus on two approaches for the pre-execution of backend memory operations: 1. software-based pre-execution using LLVM compiler pass and 2. transparent hardware-based approach using execution contexts in the processor.

**Key Results: Improve Persistent-memory based storage application 2.35 $\times$ with manual changes and 2.00X with LLVM optimization**

## Publications

> [EdgeRAG: Online-Indexed RAG for Edge Devices](https://arxiv.org/abs/2412.21023)                 
> **Korakit Seemakhupt**, Sihang Liu, Samira Khan      
> Arxiv
> December 2024          
> [[pdf]](https://arxiv.org/abs/2412.21023)
> [[Source Code]](https://github.com/betaloha/edgerag_release)

> [A Cloud-Scale Characterization of Remote Procedure Calls](https://dl.acm.org/doi/pdf/10.1145/3600006.3613156)                 
> **Korakit Seemakhupt**, Brent E. Stephens, Samira Khan, Sihang Liu, Hassan Wassel, Soheil Hassas Yeganeh, Alex C. Snoeren, Arvind Krishnamurthy, David Culler and Henry M. Levy      
> The 29th ACM Symposium on Operating Systems Principles (SOSP'23)          
> Koblenz, Germany, October 2023.        
> [[pdf]](https://dl.acm.org/doi/pdf/10.1145/3600006.3613156), [[Slides]](https://github.com/betaloha/betaloha/blob/main/Cloud_scale_RPC_characterization_SOSP23.pdf)

> [vPIM: Efficient Virtual Address Translation for Scalable Processing in-Memory Architectures](https://60dac.conference-program.com/presentation/?id=RESEARCH805&sess=sess158)       
> Amel Fatima, Sihang Liu, **Korakit Seemakhupt**, Rachata Ausavarungnirun and Samira Khan         
> Design Automation Conference (DAC)          
> San Francisco, CA, July 2023.        

> [NearPM: A Near-Data Processing System for Storage-Class Applications](https://dl.acm.org/doi/10.1145/3552326.3587456)       
> Yasas Senevirathne, **Korakit Seemakhupt**, Sihang Liu, and Samira Khan         
> Eighteenth European Conference on Computer Systems (EuroSys'23)          
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
> International Symposium on Computer Architecture (ISCA'21)   
> Virtual, June 2021.       
> [[pdf]](https://github.com/betaloha/betaloha/blob/main/PMNet_paper.pdf), [[Slides]](https://github.com/betaloha/betaloha/blob/main/PMNet_ISCA21_Full.pdf), [[Video]](https://youtu.be/R72gRpDcNBw), [[Source code]](http://pmnet.persistentmemory.org/)       
> Artifact available at GitHub      

> [Cross-Failure Bug Detection in Persistent Memory Programs](https://www.cs.virginia.edu/~smk9u/liu_xfd_asplos2020.pdf)        
> Sihang Liu, **Korakit Seemakhupt**, Yizhou Wei, Thomas Wenisch, Aasheesh Kolli, and Samira Khan        
> International Conference on Architectural Support for Programming Languages and Operating Systems (ASPLOS'20)        
> Lausanne, Switzerland, March 2020.        
> [[pdf]](https://github.com/betaloha/betaloha/blob/main/xfPM.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_ASPLOS20_slides.pptx), [[Summary]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_summary.pdf), [[Video]](https://www.youtube.com/watch?v=SgUeTKfHJDk), [[Source code]](https://xfdetector.persistentmemory.org/)       
> Artifact Available and Artifact Evaluated, Functional, Reproduced     

> [Janus: Optimizing Memory and Storage Support for Non-Volatile Memory Systems](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19.pdf)   
> Sihang Liu, **Korakit Seemakhupt**, Gennady Pekhimenko, Aasheesh Kolli, and Samira Khan    
> International Symposium on Computer Architecture (ISCA'19)   
> Phoenix, AZ, June 2019.    
> [[pdf]](https://github.com/betaloha/betaloha/blob/main/Janus_ISCA.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_slides.pptx), [[Lightning Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_lightning_slides.pptx), [[Video]](https://www.youtube.com/watch?v=kJdgvhLur3M&t=)      
> MICRO TOP PICKS 2020 Honorable Mention        


## Work Experiences
### [Google Cloud, Confidential Computing](https://cloud.google.com/security/products/confidential-computing), Software Engineer (2025-)

### [System Research@Google](https://techsysinfra.google/research/), Research Intern/Student Researcher (2022-2023)
- RPC Characterization in Google's fleet

### [Lumio 3D Co., Ltd.](https://lumio3d.com/en/), System Engineer (2016-2018)
- System software and device driver on Nvidia Tegra K1 SoC based system
- Image processing software
- Multi-camera control software

### Chulalongkorn University, Research Assistant (2015-2016)
- Design and implement a printhead controller for an inkjet 3D printer

### Design Gateway Co., Ltd., Intern (2013)
- Integrate and test Ethernet, SATA and HDMI IP on an FPGA
