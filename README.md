# Supplementary Material: Hard Real-Time Embedded Implementation of Closed-Loop Gastric Pacemaker

This repository contains supplementary data for our IEEE EMBS conference paper, specifically detailing the Worst-Case Execution Time (WCET) analysis performed without compiler optimizations.

## Baseline WCET Analysis (-O0 Compilation)

During the initial phases of this research, the static and measurement-based WCET analyses were performed with compiler optimizations disabled (`-O0`). This is a standard practice in strict static analysis to ensure the analyzed Control Flow Graph (CFG) perfectly matches the actual execution and maintains loop structure integrity. 

However, because unoptimized code is rarely used in real-world embedded deployments, the primary results in our paper reflect `-O1` optimization. Higher optimization levels (`-O2` and `-O3`) were incompatible with the Heptane static analysis tool due to assembler errors related to CFI directives. 

Below are the baseline results for the `-O0` compilation:

### FlexPRET Execution Cycles (-O0)
* **Static WCET (Heptane):** 3,996 cycles
* **Measured Worst-Case (HiL):** 3,543 cycles
* **Measured Best-Case (HiL):** 3,472 cycles
* **Pessimism Margin:** 453 cycles (11.3%)

### ARM Cortex-A9 Execution Cycles (-O0)
* **Measured Worst-Case (HiL):** 68,452 cycles
* **Measured Best-Case (HiL):** 3,371 cycles

**
