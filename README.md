# Korakit Seemakhupt
<img src="korakit_small.JPG"
     alt="Korakit's photo"
     style="float: right; margin-right: 10px;" />
I am a third-year Ph.D. student in the Department of Computer Science at the University of Virginia. I am advised by Prof. Samira Khan. My research focuses on computer network, storage system and real system prototyping of emerging technologies. Before that, I worked with Lumio 3D Co., Ltd. I received my B.Eng and M.Eng degrees from Chulalongkorn University in 2014 and 2016 respectively.

Contact Email: korakit@virginia.edu

## Research
### Supports for in-network data persistence at datacenter scale
Recent adoption of fast local storage system such as all-flash storage and persistent memory drastically reduces the latency of accessing data locally. However, because application logic processing and storage backends are placed in separate server racks in typical datacenter deployment, the latency of network including network stack processing becomes a bottleneck. While there are prior works that mitigate the latency of the network stack such as using RDMA as a transport protocol or optimizing RPC processing, server's processing is still a major part of the round-trip latency. With such observation, our research, PMNet adds persistent memory to persist update requests in network devices to provide **in-network data persistence** and move the server off the critical path of update requests while tackling challenges in common datacenter such as packet loss, hardware failure and multi-path problems.     

### Integration of in-network data persistence with in-network compute
Apart from mitigating update requests' latency, other in-network compute can also exploit **in-network data persistence**. In-network compute using traditional programmable network switch offers line-rate computing performance but lacks large memory support. Therefore, adding more memory capacity can greatly expand the capability of such system. In addition, persistent memory also offers data persistence; the data stored in persistent memory is not lost when failure such as power loss or software bug happens. Thus, in-network compute applcation can avoid frequent checkpointing which is expensive. Our research focuses on how to provide a common interface to allow other in-network compute to exploit **in-network data persistence**.      

## Publications

> [PMNet: In-Network Data Persistence](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA2021.pdf)   
> **Korakit Seemakhupt**, Sihang Liu, Yasas Senevirathne, Muhammad Shahbaz and Samira Khan    
> International Symposium on Computer Architecture (ISCA)   
> Virtual, June 2021.       
> [[pdf]](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA2021.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/PMNet_ISCA21_Full.pptx), [[Video]](https://youtu.be/R72gRpDcNBw), [[Source code]](http://pmnet.persistentmemory.org/)       
> Artifact available at GitHub      

> [Cross-Failure Bug Detection in Persistent Memory Programs](https://www.cs.virginia.edu/~smk9u/liu_xfd_asplos2020.pdf)        
> Sihang Liu, **Korakit Seemakhupt**, Yizhou Wei,Thomas Wenisch, Aasheesh Kolli, and Samira Khan        
> International Conference on Architectural Support for Programming Languages and Operating Systems (ASPLOS)        
> Lausanne, Switzerland, March 2020.        
> [[pdf]](https://www.cs.virginia.edu/~smk9u/liu_xfd_asplos2020.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_ASPLOS20_slides.pptx), [[Summary]](https://www.cs.virginia.edu/~smk9u/Liu_XFD_summary.pdf), [[Video]](https://www.youtube.com/watch?v=SgUeTKfHJDk), [[Source code]](https://xfdetector.persistentmemory.org/)       
> Artifact Available and Artifact Evaluated, Functional, Reproduced     

> [Janus: Optimizing Memory and Storage Support for Non-Volatile Memory Systems](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19.pdf)   
> Sihang Liu, **Korakit Seemakhupt**, Gennady Pekhimenko, Aasheesh Kolli, and Samira Khan    
> International Symposium on Computer Architecture (ISCA)   
> Virtual, June 2021.       
> [[pdf]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19.pdf), [[Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_slides.pptx), [[Lightning Slides]](https://www.cs.virginia.edu/~smk9u/Liu_Janus_ISCA19_lightning_slides.pptx), [[Video]](https://www.youtube.com/watch?v=kJdgvhLur3M&t=)
> MICRO TOP PICKS 2020 Honorable Mention        


## Work Experiences

### Lumio 3D Co., Ltd. (2016-2018)
- System software and device driver on Nvidia Tegra K1 SoC based system
- Image processing software
- Multi-camera control software

### Chulalongkorn University, Research Assistant (2015-2016)
- Design and implement a printhead controller for an inkjet 3D printer

### Design Gateway Co., Ltd., Intern (2013)
- Integrate and test Ethernet, SATA and HDMI IP on an FPGA
