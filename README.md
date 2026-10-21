# CSD Papers

A collection of papers and materials on Computational Storage Devices (CSDs). These devices push computation into the SSD (near-data processing / in-storage computing), so less data has to move between the host and storage.

## Surveys and Standards

| File | Paper | Venue | Summary |
| --- | --- | --- | --- |
| [Computational_Storage_BARBALACE_DOA14102020_VOR_CC_BY.pdf](Computational_Storage_BARBALACE_DOA14102020_VOR_CC_BY.pdf) | Computational Storage: Where Are We Today? | CIDR 2021 | Position paper. It argues that commercial CSDs still lack heterogeneous resource management, security, multi-user support, data consistency and usability, and discusses how well existing programming models and HW/SW interfaces could address these gaps. |
| [FMS-2023-Computational-Storage-Subsystem-Local-Memory.pdf](FMS-2023-Computational-Storage-Subsystem-Local-Memory.pdf) | NVMe Computational Storage (slides) | FMS 2023 | Overview of the NVMe computational storage specification: Compute and Memory Namespaces, Subsystem Local Memory (TP4131), Memory Copy, computational programs (PUID), Memory Range Sets and Reachability. |

## System Software Stacks and Programming Interfaces

| File | Paper | Venue | Summary |
| --- | --- | --- | --- |
| [fast23-yang-zhe.pdf](fast23-yang-zhe.pdf) | λ-IO: A Unified IO Stack for Computational Storage | FAST 2023 | A unified IO stack that manages compute and storage resources on both the host and the device. Its interface, runtime and scheduling designs decide whether each task runs on the host or the device. Up to 5.12× faster than Linux IO. |
| [fast25-park.pdf](fast25-park.pdf) | Selective On-Device Execution of Data-Dependent Read I/Os | FAST 2025 | Runs the data-dependent read I/Os of read-only on-disk data structure traversals (e.g., B+-trees) as on-device functions, working together with in-kernel storage functions. The prototype is built on NVMeVirt. |
| [2601.17633v1.pdf](2601.17633v1.pdf) | Conduit: Programmer-Transparent Near-Data Processing Using Multiple Compute-Capable Resources in SSDs | arXiv 2026 (ETH Zürich) | Automatically offloads computation across three kinds of compute resources inside the SSD (embedded cores for ISP, DRAM for PuD-SSD, NAND flash for IFP), with no programmer involvement. 1.8× faster than the best prior offloading policy, with 46% lower energy. |

## Research Platforms and Prototypes

| File | Paper | Venue | Summary |
| --- | --- | --- | --- |
| [3779212.3790137.pdf](3779212.3790137.pdf) | CEMU: Enabling Full-System Emulation of Computational Storage Beyond Hardware Limits | ASPLOS 2026 | A software-based full-system CSD emulation platform made of a device emulator and a CSD software stack. A VM-freezing mechanism models compute latency separately, so it can emulate CSDs with more compute power than the physical hardware has. Case studies cover LLM training and LevelDB. |
| [2112.00142v1.pdf](2112.00142v1.pdf) | ZCSD: a Computational Storage Device over Zoned Namespaces (ZNS) SSDs | arXiv 2021 (VU Amsterdam) | A CSD prototype built on ZNS SSDs that explores how programmable storage fits with the zoned interface. |

## Transparent Compression and Compression-Based CSDs

| File | Paper | Venue | Summary |
| --- | --- | --- | --- |
| [fast22-qiao.pdf](fast22-qiao.pdf) | Closing the B+-tree vs. LSM-tree Write Amplification Gap on Modern Storage Hardware with Built-in Transparent Compression | FAST 2022 | Uses storage hardware with built-in transparent compression (ScaleFlux CSD) and three simple techniques to cut B+-tree write amplification by over 10×, matching or beating RocksDB. |
| [2509.05365v1.pdf](2509.05365v1.pdf) | Waltz: Temperature-Aware Cooperative Compression for High-Performance Compression-Based CSDs | arXiv 2025 | Device-side hardware compression can overheat CSDs and trigger throttling, while host-side compression (e.g., F2FS) adds software-stack overhead. Waltz has the host and device compress cooperatively while tracking temperature. |
| [fast26-hu.pdf](fast26-hu.pdf) | PolarStore: High-Performance Data Compression for Large-Scale Cloud-Native Databases | FAST 2026 (Alibaba Cloud) | Compressed shared storage for PolarDB. It combines hardware compression in PolarCSD with lightweight software compression, plus database-oriented optimizations. Deployed on thousands of servers managing over 100 PB, it reaches a 3.55 compression ratio and cuts storage cost by about 60%. |
