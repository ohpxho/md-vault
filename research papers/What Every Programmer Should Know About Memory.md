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
    -

## Southbridge

<a href="https://people.freebsd.org/~lstewart/articles/cpumemory.pdf">Link of the article</a>
