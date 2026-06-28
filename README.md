# 100 Days of VLSI — RTL Design Journey

> Building digital hardware from first principles — gates to a RISC-V CPU — one Verilog module at a time.

**Status:** 🔄 In Progress — Day 59 / 100  
**Tools:** Icarus Verilog · GTKWave  
**Language:** Verilog HDL  
**Goal:** Complete a working single-cycle RISC-V processor and document every step publicly.

---

## 📍 Progress Overview

| Phase | Days | Focus | Status |
|---|---|---|---|
| Foundation | 1–10 | Digital logic theory — gates, adders, FSMs, memory | ✅ Done |
| Verilog Basics | 11–20 | Half adder → Async FIFO — first working simulations | ✅ Done |
| Advanced Modules | 21–30 | UART, PWM, LFSR, Tiny CPU, FIFO | ✅ Done |
| CDC & Synchronisation | 31–40 | Clock domain crossing, handshake, glitch-free mux | ✅ Done |
| Verification | 41–45 | Pulse synchroniser, CRC-8, SPI slave, arbiter | ✅ Done |
| Clocking & Reset | 46–49 | Clock skew/jitter, async vs sync reset | ✅ Done |
| Milestone | 50 | RISC vs CISC — architecture theory | ✅ Done |
| RISC-V CPU | 51–59 | Single-cycle RISC-V processor — block by block | 🔄 Active |
| Pipelining | 60–70 | 5-stage pipeline, hazards, forwarding | ⏳ Upcoming |

---

## 🏗️ RISC-V Single-Cycle CPU — Block Status

Building a complete single-cycle RISC-V (RV32I subset) processor from scratch in Verilog.

| Day | Block | Description | Status |
|---|---|---|---|
| 51 | ALU | 32-bit RISC-V ALU — ADD, SUB, AND, OR, XOR, SLT | ✅ Simulated |
| 52 | Register File | 32×32 register file — x0 hardwired to zero | ✅ Simulated |
| 53 | PC + Instruction Memory | Program counter + ROM — PC increments by 4 | ✅ Simulated |
| 54 | Instruction Decode Unit | Decodes opcode, rs1, rs2, rd, funct3, funct7, imm | ✅ Simulated |
| 55 | Control Unit | Generates reg_write, alu_src, mem_read, branch signals | ✅ Simulated |
| 56 | ALU Control Unit | Maps funct3/funct7 + alu_op to 3-bit alu_sel | ✅ Simulated |
| 57 | Data Memory | Byte-addressable memory — load/store | ✅ Simulated |
| 58 | Single-Cycle Datapath | Full datapath theory + block diagram | ✅ Documented |
| 59 | CPU Integration | Top-level integration of all blocks | 🔄 Debugging |

---

## 📦 Key Modules Built (Days 1–50)

| Module | Category | Description |
|---|---|---|
| Half Adder / Full Adder | Combinational | Basic arithmetic building blocks |
| 4-bit Ripple Carry Adder | Combinational | Chained full adders |
| Multiplexer (2:1, 4:1) | Combinational | Datapath selection logic |
| Decoder / Encoder | Combinational | Binary to one-hot and reverse |
| D / JK / T Flip-Flops | Sequential | Core memory elements |
| 4-bit Ring / Johnson Counter | Sequential | Shift-register based counters |
| LFSR | Sequential | Linear Feedback Shift Register for pseudo-random sequences |
| Mealy FSM | Sequential | Output depends on state + input |
| Moore FSM | Sequential | Output depends only on state |
| PWM Generator | Sequential | Configurable duty cycle pulse-width modulator |
| UART TX / RX | Protocol | Serial transmitter and receiver |
| SPI Slave | Protocol | SPI protocol — slave mode |
| I2C (basic) | Protocol | Two-wire serial communication |
| Async FIFO | Memory | Dual-clock FIFO with Gray code pointers |
| Sync FIFO | Memory | Single-clock FIFO |
| CDC Synchroniser | CDC | 2-FF synchroniser for clock domain crossing |
| Handshake Protocol | CDC | Valid-ready handshake across domains |
| Glitch-Free Clock Mux | CDC | Safe clock switching circuit |
| Pulse Synchroniser | CDC | Single-pulse transfer across clock domains |
| Reset Synchroniser | Clocking | Async assert, sync deassert reset |
| CRC-8 | Verification | Cyclic redundancy check — error detection |
| Arbiter | Control | Priority-based bus arbiter |
| Tiny CPU (Day 25) | Architecture | Simple 8-bit CPU — fetch, decode, execute |

---

## 🛠️ Tools & Setup

```bash
# Simulate any module
iverilog -o output.vvp design.v testbench.v
vvp output.vvp

# View waveforms
gtkwave output.vcd
```

**Environment:** Icarus Verilog · GTKWave · VS Code

---

## 📁 Repository Structure

```
100-days-vlsi/
├── days-01-10/        # Digital logic theory & basics
├── days-11-20/        # Verilog fundamentals
├── days-21-30/        # Advanced modules
├── days-31-40/        # CDC & synchronisation
├── days-41-49/        # Verification & clocking
├── riscv-cpu/         # RISC-V single-cycle CPU (active)
│   ├── alu.v
│   ├── regfile.v
│   ├── imem.v
│   ├── control_unit.v
│   ├── alu_control.v
│   ├── data_memory.v
│   ├── riscv_cpu.v
│   └── tb_riscv_cpu.v
└── README.md
```

---

## 🔭 Roadmap

- [x] Digital logic foundation
- [x] Core Verilog modules (combinational + sequential)
- [x] Communication protocols (UART, SPI)
- [x] Clock domain crossing techniques
- [x] RISC-V ALU, Register File, Control blocks
- [ ] Single-cycle RISC-V CPU — integration complete
- [ ] 5-stage pipelined RISC-V CPU
- [ ] Hazard detection + data forwarding
- [ ] FPGA implementation

---

## 🔗 Links

- 📂 [Verilog Code Portfolio](https://jyoshnakarri.github.io/Verilog_Codes/) — 50+ modules with waveforms
- 🌐 [Portfolio Site](https://jyoshnakarri.github.io/Jyoshna-Karri/)
- 💼 [LinkedIn](https://www.linkedin.com/in/jyoshna-k-5b1626401/)

---

*Streak is not the goal. Understanding is.*
