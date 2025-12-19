# vsd-riscv2-Task1
# Task-1: Environment Setup & RISC-V Reference Bring-Up

This repository documents the successful completion of **Task-1: Environment Setup & RISC-V Reference Bring-Up** using the official **vsd-riscv2 GitHub Codespaces environment**.

All tasks were completed using **RISC-V simulation (Spike)**.  
No FPGA hardware was required or used, as specified in Task-1.

Screenshots of successful execution are included.

---

## Environment Used

- GitHub Codespaces (Ubuntu Dev Container)
- Tools:
  - riscv64-unknown-elf-gcc
  - spike
  - proxy kernel (pk)
  - iverilog
  - noVNC desktop

---

## Task Completion Summary

- GitHub Codespace environment initialized successfully
- RISC-V toolchain verified
- Sample RISC-V program compiled using RISC-V GCC
- Program executed successfully using Spike simulator
- VSDFPGA labs cloned and basic non-FPGA labs executed
- Execution results documented with screenshots

FPGA tools and hardware were **not used**, as instructed in Task-1.

---

## RISC-V Program Execution

### Program Location
- Repository: `vsd-riscv2`
- Directory: `samples`
- File used: `sum1ton.c`

### Commands Used
```bash
riscv64-unknown-elf-gcc -o sum1ton.o sum1ton.c
spike pk sum1ton.o





## Understanding Check


### 1. Where is the RISC-V program located in the repository?

The RISC-V programs are located in the `samples` directory of the `vsd-riscv2` repository.

Example program used:
- `sum1ton.c`

---

### 2. How is the program compiled and loaded into memory?
<img width="1869" height="861" alt="Screenshot 2025-12-19 213720" src="https://github.com/user-attachments/assets/32a34bc4-fa4b-4363-97af-8942a22fcb65" />
<img width="1707" height="829" alt="Screenshot 2025-12-19 213347" src="https://github.com/user-attachments/assets/a8469fdb-21a7-42fd-9271-22288621a753" />
<img width="1909" height="958" alt="Screenshot 2025-12-19 204232" src="https://github.com/user-attachments/assets/fc4d0370-37f8-45c7-ad1f-30229ba615c7" />
<img width="1878" height="819" alt="Screenshot 2025-12-19 203714" src="https://github.com/user-attachments/assets/81a2757e-dfac-413d-99e2-5a6d97792772" />
<img width="1496" height="430" alt="Screenshot 2025-12-19 224343" src="https://github.com/user-attachments/assets/6add3ccf-48b2-4df0-9491-d7f156ba484a" />
<img width="1203" height="494" alt="Screenshot 2025-12-19 214035" src="https://github.com/user-attachments/assets/854115ee-4fe5-4638-b3fb-3c0920a1545b" />
<img width="1782" height="761" alt="Screenshot 2025-12-19 225131" src="https://github.com/user-attachments/assets/7b51545c-9a14-48cd-a198-e8455a4ce764" />
<img width="1782" height="761" alt="Screenshot 2025-12-19 225131" src="https://github.com/user-attachments/assets/182a6c60-4989-4740-b1a7-ae5e779cb48c" />

The program is compiled using the RISC-V cross compiler `riscv64-unknown-elf-gcc`.  
The generated executable is loaded into simulated memory by the proxy kernel (`pk`), which then transfers control to the `main()` function when executed using the Spike simulator.

---

### 3. How does the RISC-V core access memory and memory-mapped I/O?

The RISC-V core uses a **memory-mapped architecture** where:
- Instructions, data memory, and peripherals share the same address space
- Memory-mapped I/O devices are accessed using standard load and store instructions
- In simulation, Spike emulates memory and peripheral behavior
- In hardware, peripherals are accessed through fixed memory address ranges

---

### 4. Where would a new FPGA IP block logically integrate in this system?

A new FPGA IP block would integrate as a **memory-mapped peripheral** connected to the system bus through an address decoder.  
The RISC-V core would interact with the IP using load and store instructions mapped to the assigned address range.

---

## FPGA Status

- FPGA hardware: **Not required for Task-1**
- FPGA tools: **Not installed**
- FPGA flashing and serial terminal: **Not performed**
- Task verified using **simulation-based execution (Spike)**

---

## Conclusion

**Task-1: Environment Setup & RISC-V Reference Bring-Up** was successfully completed using GitHub Codespaces and the Spike ISA simulator.  
The RISC-V toolchain and reference execution flow were validated without requiring FPGA hardware.  
The environment is confirmed to be ready for upcoming RTL, IP integration, and FPGA-based tasks.
