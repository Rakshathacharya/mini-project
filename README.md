# Miniproject
## comparitive analysis of synchronous and asynchronous fifo
### 1. ABSTRACT
Because of flexibility of application and highest performance, thrills and middle end For a obtained extensive market. As a fundamental memory structure. The FIFO is widely used in FPGA based projects. But limited by the resources in chip and imperfections of development tools, the problem of insufficient memory while the overall capacity is often enough occurs in implementation of multi-channel FIFO. This project surveys various occasion applications of FIFO and puts forward the implementation of FIFO Memory Using Shift registers.
### 2. INTRODUCTION
Data can be transferred through various communication channels, including copper wires, optical fibers, wireless channels, storage media, and computer buses. High-speed data transfer was achieved through parallel/serial transmission. Parallel transmission groups binary data and transmits them in frames/streaming using n wires. Serial transmission involves transmitting one bit at a time, requiring only one communication channel, which reduces transmission costs. However, conversion devices are required at the interface between the sender and the line and between the line and the receiver. Serial transmission can be asynchronous or synchronous.
FPGA tech is widely used due to its low cost, high performance, maturity, and short design cycle. FIFO is a fundamental storage structure used as a data buffer for signal processing systems, communication bridges between networks of different data rates, and communication interfaces between modules in different clock domains. Multi-channel FIFO combines FIFOs into four categories: SISO FIFO, SIPO FIFO, PISO FIFO, and PIPO FIFO. SISOFIFO channels are independent, while SIPO FIFO is written channel by channel but read out simultaneously. PISO FIFO is written in parallel but read channel by channel, and PIPOFIFO is written and read simultaneously in parallel.
### 3. LITERATURE SURVEY
Dr. Ashok Kumar K et.al.,[1] published paper on “Advanced FIFO Structure for Router in Bi-NoC”.In this paper, the author proposes an advanced FIFO-based memory unit in NoC router to reduce the burden on the router and improve FIFO internal structure, thus improving the performance of Bi-NoC. The proposed work shows a 28% improvement in delay and 17% resource utilization compared to previous work. Power consumption increases through virtual channels at an advanced FIFO structure, so router components need improvement to enhance NoC performance.

Ashish Sharma et.al.,[2] proposed a paper “Reducing FIFO Buffer Power Using Architectural Alternatives at RTL”.To design a low power consumption architecture for NoC, designers can reduce buffer power consumption. Existing techniques optimize virtual channel buffer power with buffer sharing, power gating, and Dynamic Voltage Frequency Scaling. This paper proposes two clock gating techniques, enabling clock gating at input channel buffers and applying clock gating on FPGA slices. The approach significantly improves FIFO buffer power in 2D NoC by 10.70% and reduces power consumption by approximately 39% when Xilinx intelligent clock gating is applied in the NoC.

Ann Gordon-Ross et.al.,[3] published a paper “A One-Cycle FIFO Buffer for Memory Management Units in Manycore Systems ”. As microprocessors increase PEs on a single die, bottlenecks arise for data passing and memory bandwidth. FIFO architectures require many registers, increasing power consumption and area overhead. The proposed design leverages two-phase clocks, a two-ported SRAM memory 8T-Cell, and simplified flag circuitry to provide high-speed operation and large storage capacity. Future work will adapt the design for asynchronous behavior.

Jinfu Xuet.al.,[4] proposed a paper “An Unified Online Fault-tolerant Mechanism for FIFO Faults in Network-on-Chip Router” . As multi-core network-on-chip (NoC) designs become more complex, router failures caused by production defects, process deviation, material radiation, and aging are becoming more serious. This paper proposes an online fault-tolerant mechanism for FIFO in NoC routers, which includes a fault detection algorithm and reliable circuit architecture. The proposed mechanism improves throughput and latency with injected faults, and the area overhead is increased by 12%.

Bibhas Ghoshal et.al.,[5] proposed a paper “In-Field Test for Permanent Faults in FIFO Buffers of NoC Routers”.This brief proposes an on-line transparent test technique for detecting latent hard faults in NoC routers' first input first output buffers. The proposed 
technique involves repeating tests periodically to prevent the accumulation of faults. A prototype implementation of the proposed test algorithm has been integrated into the router channel interface and has been tested with synthetic self-similar data traffic. An additional on-line test technique for the routing logic has also been proposed, which considers utilizing the header flits of data traffic movement in transporting the test pattern.

Haytham Ashour et.al.,[6] proposed a paper “Design, Simulation and Realization of a Parametrizable, Configurable and Modular Asynchronous FIFO ''. This paper presents the design and simulation of an asynchronous FIFO that is parameterizable in data interface width and memory depth. The FIFO flag thresholds are re-configurable at run time and are using a modular design approach in its implementation and in interfacing with other system components. The design approach followed is modular in its architecture which means each module in the architecture is implementing an isolated and self contained set of functions that can be reused in any other system. This approach resulted in the asynchronous FIFO itself becoming a modular design offering a modular interface to the other system level components. The reconfigurability of the FIFO at run time finds its applications in applications like rate matching, re-configurable hardware and data streaming applications. 

Saleh Abdel-Hafeez et.al.,[7] published a paper " A One Cycle Asynchronous FIFO Queue Buffer Circuit".The paper describes an energy-efficient asynchronous (clockless) FIFO memory design that operates on the handshake signaling that is Request and Acknowledge signals. The design generates the Acknowledge signal based on the received Request signal using a new asynchronous circuit that controls the operation of the FIFO. Thus, the design can be considered as a potential technology of choice for low-power applications such as IoT communication solutions.  The design can operate 5X faster at the same supply voltage compared to prior work. The design’s total power consumption is 2 mW with a total transistor count of 34,470 at 65 nm and 1 V power supply.

Shruthi Sharma [8] published the paper to analyze the performance evaluation of the asynchronous and synchronous design topologies of FIFO being constructed based on a scheme where data movement is avoided in the FIFO.Pipelining is a practical technique for high-performance digital system design that is used to maintain parallelism and increase system throughput. The principles of synchronous and asynchronous logics are based on strict protocols, which are timed-driven and demand-driven. To cope with variations in process, voltage, and temperature, most works use a handshaking process that specifies a token of request or acknowledgement. Transparent latches in the pipeline allow the next data item to enter, and asynchronous design is integrated to avoid critical delays, clock skew, and power consumption control. The four-phase handshake protocol is used to achieve an 
asynchronous FIFO environment, and the early acknowledgement protocol is an improvement above the normal four-phase protocol. Asynchronous communication protocols for control and synchronization in integrated circuits are a clear requisite for the semiconductor industry, and the design approach based on globally asynchronous locally synchronous (GALS) in integrated circuits is being emphasized. The presented method for designing asynchronous pipelines avoids predictable syntax directed translation tactics, and a data-driven design style is used to synthesize an asynchronous control system that can easily integrate into conventional synchronous design styles.

Gengting Liu et.al.,[9] the paper discusses the use of packet switched NoC architectures and GALS networks to integrate design blocks in different clock domains. It proposes a new asynchronous interface FIFO design optimized for FPGA implementation, which utilizes D-type flip flops for fast NRZ synchronization and Johnson-encoded asynchronous pointers to improve performance. The design is immune to layout delays and skew and is designed as macros for easy implementation and improved portability. The proposed asynchronous FIFO can be applied to other m-of-n protocols and an extended ASIC version can be developed for ASIC GALS systems.
Ameer M.S. qbdelhadi et.al.,[10] proposed “Synthesizable Synchronization FIFOs Utilizing the Asynchronous Pulse-Based Handshake Protocol” in this paper Modern chip designs with billions of transistors require organizing into independent timing domains due to clock 
### 4. METHODOLOGY
FIFO (First-In-First-Out) is a commonly used data structure that buffers data between two components. There are two types of FIFOs: synchronous and asynchronous.
Synchronous FIFOs use a clock signal to synchronize the read and write operations. They are commonly used in high-speed digital systems where precise timing is crucial.Asynchronous FIFOs transfer data without using a clock signal. They are commonly used in low-speed digital systems where timing is less critical.
The design methodology for synchronous and asynchronous FIFOs is different due to their different operating characteristics. Synchronous FIFOs typically use flip-flops and counters to store and track the data, while asynchronous FIFOs use dual-port RAM and control logic. The designer must carefully consider timing constraints and signal protocols to ensure reliable and efficient data transfer between components. synchronous and asynchronous FIFOs have different operating characteristics and require different design methodologies. Synchronous FIFOs use a clock signal and are used in high-speed systems, while asynchronous FIFOs transfer data without a clock signal and are used in low-speed systems. The designer must carefully consider timing constraints and signal protocols to ensure reliable and efficient data transfer between components.
![image](https://github.com/Rakshathacharya/mini-project/assets/93918733/77da5b28-146d-419f-b23f-601b017ca306)

![image](https://github.com/Rakshathacharya/mini-project/assets/93918733/f37ab4f3-c3a1-4f16-afe6-2ae918d1b11e)
![image](https://github.com/Rakshathacharya/mini-project/assets/93918733/753edc14-3314-4e10-a37a-0519b8bcfa8e)
### 5. TIME SCHEDULE
|TIME ALLOCATED|WORK PLANNED|
| :-: | :-: |
|1/4/2023 to 15/4/2023|Advanced study on cadence tools and techniques|
|16/4/2023 to 30/4/2023|Literature Survey|
|1/5/2023 to 30/5/2023|Studying and designing of synchronous and asynchronous FIFOs|
|31/5/2023 to 20/6/2023|Comparative analysis about synchronous and asynchronous FIFOs|
### REFERENCE
[1] Kumar, Ashok, and V. Karunakar Reddy. "Advanced FIFO Structure for Router in Bi-NoC." 2021 5th International Conference on Intelligent Computing and Control Systems (ICICCS). IEEE, 2021.

[2] Sharma, Ashish, et al. "Reducing fifo buffer power using architectural alternatives at rtl." 2016 20th International Symposium on VLSI Design and Test (VDAT). IEEE, 2016.

[3] Gordon-Ross, Ann, Saleh Abdel-Hafeez, and Mohamad Hammam Alsafrjalni. "A One-Cycle FIFO Buffer for Memory Management Units in Manycore Systems." 2019 IEEE Computer Society Annual Symposium on VLSI (ISVLSI). IEEE, 2019.

[4] Xu, Jinfu, et al. "An unified online fault-tolerant mechanism for FIFO faults in network-on-chip router." 2016 13th IEEE International Conference on Solid-State and Integrated Circuit Technology (ICSICT). IEEE, 2016.

[5] Ghoshal, Bibhas, et al. "In-field test for permanent faults in FIFO buffers of NoC routers." IEEE Transactions on Very Large Scale Integration (VLSI) Systems 24.1 (2015): 393-397.

[6] Ashour, Haytham. "Design, simulation and realization of a parameterizable, configurable and modular asynchronous FIFO." 2015 Science and Information Conference (SAI). IEEE, 2015.

[7] Abdel-Hafeez, Saleh, and Muhannad Quwaider. "A one-cycle asynchronous FIFO queue buffer circuit." 2020 11th International Conference on Information and Communication Systems (ICICS). IEEE, 2020.

[8] Sharmaa, Shruti. "Implementation of an RTL synthesizable asynchronous FIFO for conveying data by avoiding actual data movement via FIFO." 2015 6th International Conference on Computing, Communication and Networking Technologies (ICCCNT). IEEE, 2015.

[9] Liu, Gengting, et al. " Asynchronous interface FIFO design on FPGA for high-throughput NRZ synchronization."  2017 27th International Conference on Field Programmable Logic and Applications (FPL). IEEE, 2017.

[10] Abdelhadi, Ameer MS. "Synthesizable synchronization FIFOs utilizing the asynchronous pulse-based handshake protocol." 2020 IEEE Nordic Circuits and Systems Conference (NorCAS). IEEE, 2020






