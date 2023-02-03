![Open-ESP](esp-logo-small.png)

[![DOI](https://zenodo.org/badge/190284572.svg)](https://zenodo.org/badge/latestdoi/190284572)

The [ESP website](https://www.esp.cs.columbia.edu) contains the most
up-to-date information on the ESP project. The
[Documentation](https://www.esp.cs.columbia.edu/docs) page contains
detailed guides and video tutorials that will be released periodically
to help users get the most out of ESP.

ESP is an open-source platform for heterogeneous SoC design and
prototype on FPGA. It provides a flexible tile-based architecture
built on a multi-plane network-on-chip.

In addition to the architecture, ESP provides users with templates and
scripts to create new accelerators from SystemC, Chisel, and C/C++.
The ESP design methodology eases the process of integrating processors
and accelerators into an SoC by offering platform services, such as
DMA, distributed interrupt, and run-time coherence selection, that
hide the complexity of hardware and software integration from the
accelerator designer.

Currently, ESP supports the integration of multi-core
[LEON3](https://www.gaisler.com/index.php/downloads/leongrlib)
processor from GRLIB and single-core
[Ariane](https://github.com/pulp-platform/ariane) processors from the
Pulp Platform. LEON3 implements the SPARC V8 32-bits ISA, while Ariane
implements the RISC-V 64-bits ISA.

In addition to processor cores, ESP embeds accelerator design examples
created with Stratus HLS in SystemC, Vivado HLS in C/C++ and Chisel.

Furthermore, ESP can serve as a platform to integrate third-party IP
blocks.  For example, ESP integrates the NVIDIA Deep Learning
Accelerator [NVDLA](http://nvdla.org/), which can be placed on any ESP
accelerator tile.

## Publications

Overview paper:

> Paolo Mantovani, Davide Giri, Giuseppe Di Guglielmo, Luca
> Piccolboni, Joseph Zuckerman, Emilio G. Cota, Michele Petracca,
> Christian Pilato, Luca P. Carloni. _"Agile SoC Development with Open
> ESP."_ IEEE/ACM International Conference On Computer Aided Design
> (ICCAD), 2020.

The [Publications](https://www.esp.cs.columbia.edu/pubs) page of the
ESP website contains the complete list of publications related to ESP.

## Repository organization

Here is a brief description of the main directories in the repository,
please refer to the READMEs inside each of them for more information.

* `accelerators` contains multiple accelerator design and integration
  flows, as well as many example accelerators.

* `constraints` contains the constraints and attributes for each
  supported FPGA board (or ASIC technology).

* `socs` contains the working folders for launching all Make targets.
  There is one working folder for each supported FPGA board (or ASIC
  technology).

* `rtl` contains the whole RTL code base, excluding the accelerators
  RTL and the RTL generated in the working folder by the SoCGen and
  SocketGen tools.

* `soft` contains bootloader, Linux kernel and root file system, and
  bare-metal library for each of the available processor cores. It
  also contains bare-metal, user space and kernel space libraries for
  invoking and managing accelerators.

* `tech` is the destination of the RTL generated by the HLS-based and
  Chisel-based accelerator design flows. It is also the destination of
  the RTL generated with HLS for the SystemC implementation of the
  cache hierarchy. The generated RTL is organized based on the target
  FPGA (or ASIC) technology.

* `tools` contains tools for design automation and for communicating
  with an ESP SoC from a host machine.

* `utils` contains various scripts and utilities, including the main
  Makefiles, the RTL file lists, and the software toolchains
  installation scripts.

* `.cache` caches some compiled libraries so they only need to be
  compiled once (e.g. Xilinx simulation libraries).

## Stay tuned for the new features under development:

   - Dynamic partial reconfiguration SoC flow
   - New machine learning and cryptography accelerators
   - Expanded support for ASIC design
