# What Every Programmer Should Know About Memory

- `Commodity hardware` - mass produced, inexpensive, standardized
- Mass storage and memory subsystems fell behind(slow improvement) in terms of performance as the other components improved - making it a bottleneck in performance
- Removing the main memory as a bottleneck pose a lot challenges and requires to change the hardware:
  - RAM (speed and parallelism)
  - Memory controller design
  - CPU caches
  - Direct Memory Access(DMA) for devices
- Personal computers and smaller servers standardized on chipset with two parts:
  - `Northbridge` (RAM)
  - `Southbridge` (PCI-E, SATA, USB)

## Northbridge

- Connected to the CPUs via **Front Side Bus (FSB)**

## Southbridge

- I/O bridge
-

## NUMA

- Non Uniform Memory Access
- A computer memory architecture used in multi processor systems
- The system is divided into nodes, each containing one or more CPUs and a dedicated local memory
- The memory access time depends on the location of the memory relative to the CPU:
  - **Local memory** (within the same node) -> fastest
  - **Remote memory** (in another node) -> slower access due to interconnect(data pathway that connects a node to other nodes) latency

<a href="https://people.freebsd.org/~lstewart/articles/cpumemory.pdf">Link of the article</a>
