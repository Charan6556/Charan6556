<p align="center">
  <img src="assets/hardware-debugger.png" width="320" alt="A chip mascot debugging digital waveforms with a magnifying glass"/>
</p>

<h1 align="center">Hi, I'm Charan Gundepinni</h1>

<p align="center">
  <strong>SoC &amp; ASIC Front-End · RTL Design &amp; Verification</strong><br/>
  SystemVerilog · UVM · AMBA AXI4/APB · RISC-V
</p>

<p align="center">
  M.S. Electrical Engineering · Colorado State University · Expected December 2026<br/>
  Seeking full-time roles in SoC/ASIC RTL design and design verification after graduation
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/charan-gundepinni">LinkedIn</a> ·
  <a href="https://github.com/Charan6556?tab=repositories">All Projects</a> ·
  <a href="#technical-skills">Technical Skills</a> ·
  <a href="#selected-projects">Selected Projects</a> ·
  <a href="#professional-experience">Professional Experience</a> ·
  <a href="#teaching-experience">Teaching Experience</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/SoC-0F766E?style=flat-square" alt="System-on-Chip"/>
  <img src="https://img.shields.io/badge/ASIC-9A3412?style=flat-square" alt="Application-Specific Integrated Circuit"/>
  <img src="https://img.shields.io/badge/SystemVerilog-155E75?style=flat-square" alt="SystemVerilog"/>
  <img src="https://img.shields.io/badge/UVM-1D4ED8?style=flat-square" alt="UVM"/>
  <img src="https://img.shields.io/badge/SVA-6D28D9?style=flat-square" alt="SystemVerilog Assertions"/>
  <img src="https://img.shields.io/badge/RISC--V-334155?style=flat-square" alt="RISC-V"/>
</p>

---

## About Me

I'm an electrical engineering graduate student focused on **SoC and ASIC front-end design and verification**. I develop **Verilog/SystemVerilog RTL** and **UVM testbenches**, using independent reference models, **SystemVerilog Assertions (SVA)**, functional coverage, and simulation evidence to check design behavior.

Alongside my graduate studies, I am an **ASIC Design Verification Trainee at Maven Silicon**.

My projects focus on **SoC building blocks**: AXI4 memory-mapped slaves, APB peripherals, synchronous FIFOs, packet-routing logic, and an RV32I processor. My packet-router project also demonstrates an **ASIC front-end flow: RTL lint → logic synthesis → SKY130 standard-cell mapping**.

As a **Graduate Teaching Assistant for ECE 252 at Colorado State University**, I lead three labs each week and help students take digital circuits from Boolean logic to FPGA implementation. I also work with Python and TensorFlow on signal-processing and machine-learning projects.

## Technical Skills

| Area | Skills demonstrated in my projects and teaching |
| --- | --- |
| **ASIC RTL & digital design** | Verilog, SystemVerilog, combinational and sequential logic, Mealy/Moore state machines, parameterized FIFOs, register interfaces, packet routing, processor design |
| **SoC interfaces & AMBA protocols** | AXI4 memory-mapped slaves, five-channel handshakes, INCR bursts, byte strobes, narrow and unaligned accesses; APB multi-slave peripherals, transfers, and wait states |
| **UVM & IP verification** | Transactions, sequences, sequencers, drivers, monitors, agents, environments, virtual sequencers, analysis ports, virtual interfaces, configuration |
| **Functional verification** | Directed and constrained-random stimulus, independent scoreboards, reference models, readback checks, boundary testing, error injection, checker validation |
| **Assertions & coverage** | SystemVerilog Assertions, bound FIFO/FSM properties, APB protocol checks, coverpoints, cross coverage |
| **ASIC lint & synthesis** | Verilator RTL lint, Yosys logic synthesis, SKY130 standard-cell mapping, synthesis netlists and cell-area reports |
| **Simulation & waveform debug** | Cadence Xcelium, SimVision, Synopsys VCS, waveform analysis |
| **Processor architecture** | RV32I single-cycle implementation, 8-bit nanoprocessor design; RV32I pipelining and hazard handling in progress |
| **FPGA implementation & debug** | Intel Quartus, DE10-Lite, simulation-to-hardware debugging, latch identification, state-transition analysis, nanoprocessor implementation |
| **Programming & ML** | Python, TensorFlow, 1D CNNs, signal preprocessing, class-imbalance handling, classification evaluation, ECG trace extraction |

### Additional technical background & tools

| Area | Background |
| --- | --- |
| **Languages** | VHDL, C, C++, Perl |
| **Interfaces & protocols** | AXI4-Lite, AHB, PCIe, UART, SPI |
| **EDA tools** | Design Compiler, SpyGlass, Verdi, ModelSim, QuestaSim, Cadence Virtuoso, AMD Vivado |
| **ASIC & FPGA concepts** | ASIC/FPGA design flows, static timing analysis (STA), lint, design for test (DFT), processor architecture |
| **Additional FPGA platforms** | Intel/Altera Cyclone V, AMD Kintex-7 |
| **Development environment** | Linux, Git, Make |

## Selected Projects

### [AXI4 Memory Slave — RTL & UVM Verification](https://github.com/Charan6556/axi4-memory-slave-uvm)

A 16 KB AXI4 memory-mapped slave with five independent channels, 32-bit data, INCR bursts of up to 256 beats, and one outstanding burst per read/write direction.

- Built a UVM master agent with separate read/write sequencers and drivers, a handshake monitor, and a byte-addressed reference-memory scoreboard checking IDs, data, responses, and final-beat behavior.
- Verified byte strobes, narrow and unaligned accesses, memory and 4 KB page boundaries, error responses, and constrained-random traffic.
- **Recorded Xcelium full-test run:** 178 writes, 151 reads, zero skipped bytes, **100% of the defined command, write-data, and response functional coverage bins**, and zero UVM warnings, errors, or fatals.

[Full-test evidence](https://github.com/Charan6556/axi4-memory-slave-uvm/blob/main/docs/images/axi_full_seed1.png) · [Verification flow](https://github.com/Charan6556/axi4-memory-slave-uvm/blob/main/docs/images/axi_uvm_flow.png) · [Tests & current scope](https://github.com/Charan6556/axi4-memory-slave-uvm#tests)

### [1×3 Packet Router — RTL & UVM Verification](https://github.com/Charan6556/router-1x3-uvm)

An 8-bit packet router with one input and three output FIFOs, verified with coordinated UVM agents, packet scoreboarding, directed boundary cases, constrained-random traffic, parity-error injection, and bound FIFO/FSM assertions.

- **Recorded Xcelium regression:** 5,024 matched packets, zero mismatches, and **100% of the defined functional coverage model**.
- **Checker validation:** a separate recorded mutation test detected 74 mismatched packets after intentional output corruption.
- **ASIC front-end flow:** Verilator lint, Yosys synthesis, and SKY130 standard-cell mapping, with preserved netlists and a reported mapped cell area of **23,804.08 µm²**.

[Regression evidence](https://github.com/Charan6556/router-1x3-uvm/blob/main/reports/xcelium_sva_regression.txt) · [Mutation-test evidence](https://github.com/Charan6556/router-1x3-uvm/blob/main/reports/mutation_test.txt) · [Synthesis evidence](https://github.com/Charan6556/router-1x3-uvm/blob/main/reports/synthesis_summary.txt) · [Architecture & testbench guide](https://github.com/Charan6556/router-1x3-uvm/blob/main/docs/testbench_guide.md)

### [APB Multi-Slave — Protocol & UVM Verification](https://github.com/Charan6556/APB-Multi-Slave-UVM-Verification)

An APB subsystem with two memory-mapped slaves, including zero-wait and two-wait-state responses.

- Built requester-side stimulus, a completed-transfer monitor, per-slave reference memories, and readback checking.
- Added assertions for protocol sequencing, slave selection, and signal stability during wait states.
- **Recorded run:** 20 monitored transfers, **100% of the defined functional coverage model**, and zero UVM warnings, errors, or fatals.

### [Synchronous FIFO — RTL & UVM Verification](https://github.com/Charan6556/Synchronous-FIFO-UVM-Verification)

A parameterized FIFO with an independent queue-based scoreboard and assertions for reset, occupancy, and pointer behavior.

- Checked full/empty boundaries, data ordering, and blocked overflow/underflow attempts with directed fill-and-drain sequences.
- **Recorded run:** 16 accepted writes, 16 accepted reads, no remaining reference entries, and zero UVM warnings, errors, or fatals.

### [RV32I Processor — Ongoing Development](https://github.com/Charan6556/RISCV-32I)

A SystemVerilog processor project progressing from a single-cycle implementation toward a pipelined architecture.

- **Completed milestone:** single-cycle processor.
- **In progress:** pipelining and hazard handling.
- **Roadmap:** AXI4-Lite integration and UVM verification.

<details>
<summary><strong>More projects: SystemVerilog foundations & machine learning</strong></summary>

<br/>

- **[SystemVerilog Class-Based Verification](https://github.com/Charan6556/SystemVerilog-Class_Based_Verification):** Modular environments for a mux, full adder, and synchronous counter using transactions, mailboxes, virtual interfaces, and self-checking scoreboards.
- **[ECG Arrhythmia Classification](https://github.com/Charan6556/ECG-Arrhythmia-Classification):** An educational five-class heartbeat classifier using Python, TensorFlow, a 1D CNN, signal preprocessing, and an experimental ECG trace-extraction pipeline. The repository documents recorded results and evaluation limitations.

</details>

## Professional Experience

### ASIC Design Verification Trainee · Maven Silicon

**January 2026 – Present**

## Teaching Experience

### Graduate Teaching Assistant · Colorado State University

**ECE 252 — Introduction to Digital Circuits · Fall 2026**  
Working with **Prof. Anura Jayasumana**

- Lead **three laboratory sessions each week**, guiding students from truth tables and Karnaugh maps through Quartus, RTL design, simulation, and FPGA implementation on the **DE10-Lite**.
- Hold office hours on Boolean algebra, flip-flops, and Mealy and Moore finite-state machines.
- Help students identify unintended latches, trace incorrect state transitions, and debug differences between simulation and FPGA behavior.
- Evaluate lab reports and help students explain how logic, timing, and state transitions affect their results.

#### Hardware Build: 8-Bit Nanoprocessor

For the lab interview, I designed an **8-bit nanoprocessor from scratch in Quartus** and demonstrated it on the **DE10-Lite FPGA platform**. The design included a gate-level adder/subtractor, a **4×4 array multiplier**, a control ROM, and a register bank.

Teaching these fundamentals strengthens how I reason about RTL, debug hardware, and explain design decisions.

## How I Approach Verification

- **Model expected behavior independently** so DUT status signals cannot hide their own bugs.
- **Start with boundaries and corner cases:** reset, full/empty transitions, protocol wait states, and malformed traffic.
- **Check the checker** by confirming that intentional corruption produces failures.
- **Connect claims to evidence:** retain scoreboards, coverage summaries, waveforms, and the scope of each recorded run.

## Education

**Colorado State University**  
M.S. in Electrical Engineering · Expected December 2026

---

<p align="center">
  Interested in SoC/ASIC RTL design and design verification opportunities.<br/>
  <a href="https://www.linkedin.com/in/charan-gundepinni"><strong>Let's connect on LinkedIn</strong></a>
</p>
