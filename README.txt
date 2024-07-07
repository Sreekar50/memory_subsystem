The project aims to optimize energy consumption in a memory subsystem consisting of an L1D cache and main memory. The focus is on reducing data transfer between these layers by implementing a compression scheme and efficient data exchange protocols.

Components of the Memory Subsystem

L1D Cache Specifications
Size: 2 KB
Associativity: 4-way set associative
Cache Line Size: 32 bytes
Processor Word Size: 4 bytes

Main Memory
Size: 8 KB
Word Size: 4 bytes per location

Data Transfer Protocol
Signals: CLK, VALID, READY, DATA
CLK: Global clock signal, sampled at rising edge for synchronization.
VALID: Asserted by L1D cache to initiate data transfer to main memory.
For load operation, sends address and waits for READY to send data.
For store operation, sends address and data sequentially after READY is asserted.
READY: Asserted by main memory to signal readiness to accept data.
For load operation, sends data back to L1D cache after receiving address.
For store operation, stores incoming data and modifies memory.
DATA: Bus for primary data transmission, used to pass address or data depending on the operation.

Compression Scheme: AxDeduplication
Aims to reduce data transfer size by compressing the stream of eight 4-byte numbers fetched during a cache miss.
Implementation focuses on reducing area consumption by optimizing data transfer efficiency.

Implementation Goals
Cache Miss Handling: When L1D cache misses, the entire cache line (32 bytes) is fetched from main memory.
Compression: Implement AxDeduplication scheme to compress the fetched data before sending it across the protocol.
Energy Efficiency: Reduce energy consumption by minimizing the amount of data transferred between L1D cache and main memory.

Conclusion
The project involves designing and implementing a memory subsystem in HDL (Verilog) that includes an L1D cache with a specified configuration, a main memory with a simplified protocol for data transfer, and integration of an AxDeduplication compression scheme to optimize data transmission efficiency. The primary goal is to achieve significant reductions in energy consumption associated with memory accesses in computing systems.
