
# Computer Architecture
In this repository, I keep the files and notes and other stuff that I worked with them while watching prof. onur Mutlu Computer Architecture courses. I try to write here what I enjoyed learning them.


## session 1
#### How to do the paper/ talk reviews?
1.	Summary
 - What is the problem the paper is trying to solve?
 - What are the key ideas of the paper? Key insights?
 - What is the key contribution to literature at the same time it was written?
 - What are the most important things you take out of it?
2.	Strengths
 - Does the paper solve the problem well?
3.	Weaknesses
 - This is where you should think critically. Every paper/idea has a weakness. This does not mean the paper is necessarily bad. It means there is room for improvement and future research can accomplish this.
4.	Can you do much better? Present your thoughts/ideas.
5.	What have you learned/enjoyed/disliked in the paper? Why?
Review should be short and concise (~half a page or shorter)

#### Advice on paper/talk reviews
* When doing the reviews, be very critical
* Always think about better ways of solving the problem or related problems
* Do background reading 
* Reviewing a paper/talk is the best way of learning about a research problem/topic
* Think about forming a literature survey topic or a research proposal

***

What I googled for and read about them, which I was not familiar with in the slides.


#### Expressive Memory: 
There is a paper and also a presentation on YouTube about this. I watched that presentation and noted what I learned about “expressive memory” below.

Only hardware (like caches, prefetchers, memory controllers) and software (imposing programmability and portability challenges) optimizations independently is not enough to get higher performance for new applications like Machine Learning. Also, with growing HW/SW sophistication, traditional interfaces limit optimization effectiveness, so it is time for a richer interface between hardware and software. “**XMem**” or **expressive memory** is proposed by prof. Onur Mutlu research team to solve this challenge. Expressive memory is **a new cross-layer abstraction which interferes between the application and the underlying hardware**. Expressive memory  <span style="color:red">**communicates high level program semantics from the application to the underlying system and architecture which can then be used to aid in performance optimization**</span>. Expressive memory provides a new way to perform many traditional hardware and software optimizations (like: Cache Management, Data placement in DRAM, Data Compression, Approximation, DRAM cache Management, NVM management, NUCA/ NUMA Optimization, etc). Exposing key program information allows the hardware to better adapt to the application and thereby provide **better program ability**, **portability** and **resource efficiency**.

---

#### ["Future Computing Architecture" Presentation on YouTube](https://www.youtube.com/watch?v=kgiZlSOcGFM&list=PL5Q2soXY2Zi8D_5MGV6EnXEJHnV2YFBJl&index=1)
Prof. Onur Mutlu is from [Kapadokya, Turkey](https://www.youtube.com/watch?v=KlS_ZUuttPU).

##### Why do we do computing? 
 - To solve problems (Prof.’s answer)
 - To gain insight – not just number crunching (Hamming’s answer) - 1962
 - To enable better life and future
 
##### How does a computer solve problems? 
 By orchestrating electrons
 
##### How do problems get solved by electrons? 
With the help of the transformation hierarchy (the broader view of computer architecture)

##### What is computer architecture? 
It is the **science/engineering** and **art** of designing computing platforms (hardware, interface, system SW, and programming model) to achieve a set of design goals. Different platforms demand different goals.

##### Expanded View of Computer Architecture
Our axiom (assumption or maybe presumption) as computer architects is to achieve the highest energy efficiency and performance we must take the expanded view of computer architecture and co-design across the hierarchy from algorithms to devices and specialize as much as possible within the design goals.

##### What kind of a future do we want?
We as designers design for future not for now. In first step we want a **reliable**, **secure**, and **safe** future. Secondly, we want a **sustainable** and **energy-efficient** one (better quality of life). Then we need a **high performance** to solve the toughest and all problems. **<span style="color: blue;">Also, the future is more personalized and private in every aspect of life: health, medicine, spaces, devices, robotics, etc.</span> **

Increasingly demanding applications: Dream and applications will come. As applications push boundaries, computing platforms will become increasingly strained.

#### Three key issues in future platforms:
-	Fundamentally secure/reliable/safe architectures
-	Fundamentally energy-efficient architectures
-	Memory-centric (data-centric) architectures
-	Architectures for Genomics, Medicine, Health

##### Secure/ Reliable/ Safe Architecture
**Security**: it is about preventing unforeseen consequences.

**One major problem**: We do not seem to have design principles for guaranteeing reliability and security.

**Focus is on**: data storage systems (memory) – memory is a critical component of all computing systems: server, mobile, embedded, desktop, sensor … Main memory must scale (in size, technology, efficiency, and management algorithms) to maintain performance growth and technology scaling benefits. As Memory scales, it becomes unreliable, data from all of Facebook’s servers worldwide proves this. Because as the density increase, **cells get closer to each other, and also they get smaller, so noise can affect them easily**.
 
#### DRAM RowHammer
A simple hardware failure mechanism can create a widespread system security vulnerability.
                               

More than 80% of the DRAM chips tested by Prof.’s group were vulnerable to these errors. This is a scaling problem because this does not happen before 2010 but in 2012 and 2013 all the chips that were manufactured exhibit these errors and doesn’t depend on the manufacturer.
           
Google researchers Mark Seaborne and Thomas Dooley actually showed that you could gain kernel privileges by exploiting this little hardware vulnerability.

**RowHammer generally**: It is like breaking into an apartment by repeatedly slamming a neighbor’s door until the vibrations open the door you were after.

**Apple’s patch for RowHammer**: This issue was mitigated by increasing memory refresh rates.

##### How do we keep memory secure?
1.	**Understand**: Methodologies for failure modeling and discovery (modeling and prediction based on read device data)
2.	**Architect**: principled co-architecting of system and memory (good partitioning of duties across the stack)
3.	**Design and Test**: Principled design, automation, testing (High coverage and good interaction with system reliability methods)
There are two other solutions
1.	**New technologies**: replace and augment DRAM with a different technology like NVM
2.	**Embracing un-reliability**: Design memories with different reliability and store data intelligently across them
Fundamental Solutions to security require co-design across the hierarchy.


##### Energy-Efficient Architectures (Memory-centric (data-centric) architectures)
Today, data access is the major performance and energy bottleneck, and our current design principles cause great energy waste. Processing of data is performed far away from the data at great system cost.

###### Perils of processor-centric design
1.	Grossly imbalanced systems
    - Processing done only in one place
    - Everything else just stores and moves data: data moves a lot
        - Energy Inefficient
        - Low Performance
        - Complex
2.	Overly complex and bloated processor (and accelerators)
    - To tolerate data access from memory
    - Complex hierarchies and mechanism
        - Energy Inefficient
        - Low performance
        - Complex
 
**Bitter Fact**: A memory access consumes **<span style="color:red">~1000X</span>** the energy of a complex addition.
 
 
 
 

##### Architectures for Genomics, Medicine, Health
Genome Analysis: Sequencing – mapping – variant calls – scientific discovery

**Bottleneck is the mapping step, we can sequence very fast.**

***

#### [“Enabling In-Memory Computation” presentation on YouTube](https://www.youtube.com/watch?v=njX_14584Jw&list=PL5Q2soXY2Zi8D_5MGV6EnXEJHnV2YFBJl&index=16)


Main memory is a critical component of all computing systems: server, mobile, embedded, desktop, sensor, etc. Main memory must scale in size, technology, efficiency, cost, and management algorithm to maintain performance growth and technology scaling benefits.

DRAM and memory controllers, as we know them today, are (will be) unlikely to satisfy all requirements. Some emerging non-volatile memory technologies like PCM enable new opportunities: memory + storage merging 

We need to rethink the main memory system to fix DRAM issues and enable emerging technologies

Major trends affecting main memory:
1.	Need for main memory capacity, bandwidth, QoS increasing
    - **Multi-core**: the increasing number of cores/agents
    - **Data-intensive applications**: increasing demand/hunger for data
    - **Consolidation**: cloud computing, GPUs, mobile, heterogeneity
2.	Main memory energy/power is a key system design concern
    - **<span style="color:red">About 40-50% energy spent on off-chip memory hierarchy</span>** [Lefurgy, IEEE computer’03]
    - **<span style="color:red">More than 40% on DRAM</span>** [Ware, HPCA’10][Paul, ISCA’15]
    - **<span style="color:red">DRAM consumes power even when not used because of periodic refreshing</span>**
3.	DRAM technology scaling is ending
    - ITRS projects that DRAM will not scale easily below X nm
    - Scaling has provided many benefits
	   - The higher capacity (density)
       - Lower cost
       - Lower energy
       
##### ISCA 2000 work by Lim et al.:
Core count doubles every 2 years, although DRAM DIMM capacity doubles every 3 years. In other words, **memory capacity per core is expected to drop by 30% every two years**.

A work by the prof. Mutlu’s group in collaboration with Google in “Google workloads for consumer devices: mitigating data movement bottlenecks” title showed that **62.7%** of the total system energy is spent on data movement.

##### Major trend:  hybrid main memory (traditional DRAM + PCM for example)
Main memory needs intelligent controllers. One can predictably induce errors in most DRAM memory chips (RowHammer).  If we don’t have an intelligent memory controller, increasing memory refresh rate can be a solution to RowHammer problem. However, actually we want to decrease this rate. Safari group’s solution for this problem was **“PARA: Probabilistic Adjacent Row Activation”**. Key idea is that after closing a row, they activate one of its neighbors with a low probability (p = 0.005).

<span style="color:red; font-size: 20px;">** What I understood generally in this presentation is that we have to try to substitute DRAM with other technology instead of complexing our architecture to adapt to using this subsystem in our computing systems.**</span>


 
#### [“Accelerating Genome Analysis: A Primer on an Ongoing Journey”](https://www.youtube.com/watch?v=hPnSmfwu2-A&list=PL5Q2soXY2Zi8D_5MGV6EnXEJHnV2YFBJl&index=9)
System design for bioinformatics is a critical problem because it has large scientific, medical, societal, personal implications. In genomic processing, DNA read mapping is the bottleneck. For sequencing we can sequence fast. Many bottlenecks exist in accessing and manipulating huge amounts of genomic data during analysis.

Bioinformatics dream in 2007 was to possess an embedded device, which can perform genomic analysis in real time within a minute.

- Which of DNAs does this DNA segment match with?
- What is the likely genetic disposition (behavior) of this patient to this drug?

Algorithmic acceleration
- Exploiting structure of the Genome
- Exploiting SIMD structure

Hardware Acceleration
- Specialized Architectures
- Processing in memory

##### Future opportunities: New sequencing technologies
DNA Sequencing: our goal in DNA sequencing is to find the complete sequence of A, C, G, and T’s in DNA.

**Challenge of DNA sequencing**: There is not machine that takes long DNA as an input, and gives the complete sequence as output. All sequencing machines chop DNA into pieces and identify relatively small pieces (but now how they fit together)

Development of high-throughput sequencing (HTS) technologies decreased the cost of sequencing so much. Today, with the help of this technology we can sequence more genomes than we can process. Some of high-throughput sequencing technologies: Illumina, Roche 54, Ion Torrent, SOLID …

In fact what goes on in this technology is that small DNA fragments are first amplified and then sequenced in parallel which results in:
- High Throughput
- High Speed
- Low Cost
- Short reads

Anyway, today we have tradeoffs about developing devices for sequencing genome and we can do it fast. However, our today bottleneck is DNA read mapping.

**Example question 1**: If I give you a bunch of sequences, tell me where they are the same and where they are different.

**Example question 2**: Given a bunch of short sequences, can you identify the approximate species cluster for gnomically unknown organisms (bacteria)?

**Answer**: If we want to answer these questions we need to construct the entire genome from many reads. However, this is where our bottleneck emerges. DNA read mapping is **150X** slower than read sequencing. Mapping short reads to reference genome is challenging (billions of 50-300 base pair reads).

#### Note on Learning
There are tons of valuable information on the slides and presentationa and lectures, go there and get more. These are just things that I enjoyed and learned a lot.

***