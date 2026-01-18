# DAG-SRT Optimal Scheduler

**Reproduction and refinement of a soft-real-time optimal scheduler for DAG tasks with node-level self-dependencies**

---

## Project Abstract

This repository contains a complete reproduction and extension of the paper:

> **“A Soft-Real-Time Optimal Scheduler for DAG Tasks with Node-Level Self Dependencies”**

The goal of the original work is to design a scheduling algorithm that guarantees **soft real-time** deadlines for tasks represented as directed acyclic graphs (DAGs), while supporting **node-level restricted parallelism** (self-dependencies). The original paper proposes a **priority-boosting global scheduler** and provides **tight response-time analysis bounds**.

This repository provides:

- A faithful reconstruction of the original scheduler and analysis
- A refined response-time analysis with reduced pessimism
- Full experimental reproduction of Fig. 8(a)–(c)
- A brute-force validation harness for small DAGs (≤6 nodes)
- A reproducible Google Colab notebook and modular Python code

---

## My Contribution

This project is designed to be a **fully reproducible artifact** for the original paper and extends it in two major ways:

1. **Refined Response-Time Analysis**
   - Introduces tighter bounds by pruning infeasible generalized paths.
   - Provides stronger guarantees while preserving soft real-time optimality.

2. **Artifact-Grade Reproduction**
   - Implements the original and refined analyses in a modular Python framework.
   - Includes validation using an exact brute-force scheduler for small DAGs.
   - Reproduces the main experimental figures (Fig. 8(a)–(c).

---

## Methodology (Illustration)

<img width="1968" height="2209" alt="gugu" src="https://github.com/user-attachments/assets/8fa6a54a-4cc7-49b5-831b-0c846e8f4f4b" />


The figure above shows the workflow:

1. Generate DAGs with random topology and parameters  
2. Compute response-time bounds (original and refined)  
3. Validate with brute-force scheduling for small DAGs  
4. Produce experimental results and figures  

---

## Experimental Results (Reproduced Figures)

### Figure 8(a): Response-time bound vs. Normalized Utilization

<img width="2100" height="1638" alt="figure_8a_utilization_sweep" src="https://github.com/user-attachments/assets/64f9a40e-c0b4-4fc8-9490-5978916475fd" />


### Figure 8(b): Response-time bound vs. Processor Count

<img width="2074" height="1638" alt="figure_8b_processor_sweep" src="https://github.com/user-attachments/assets/b445687c-82ca-472c-92b8-a09b597e8aed" />


### Figure 8(c): Response-time bound vs. Edge Probability
<img width="2074" height="1638" alt="figure_8c_edge_probability_sweep" src="https://github.com/user-attachments/assets/87814630-2c0f-49bc-9151-ebbb9910f623" />



---

## Main Equations (Core Concepts)

### 1. DAG Task Model
<img width="673" height="228" alt="Screenshot 2026-01-18 at 2 06 42 PM" src="https://github.com/user-attachments/assets/ad9d6142-705d-410e-9830-6a43939d2e41" />



---

### 2. Utilization

<img width="464" height="195" alt="Screenshot 2026-01-18 at 2 06 01 PM" src="https://github.com/user-attachments/assets/eb79e5ce-8e8e-48dc-ae85-e281d2ac4739" />



---

### 3. Response-Time Bound (Original)
<img width="516" height="178" alt="Screenshot 2026-01-18 at 2 03 32 PM" src="https://github.com/user-attachments/assets/ad40e769-25d6-4853-a6c0-5f44ab5e591f" />



---

### 4. Refined Bound (Pruned Paths)

<img width="632" height="144" alt="Screenshot 2026-01-18 at 2 04 56 PM" src="https://github.com/user-attachments/assets/48981577-fef0-4674-b6ca-01307d68b134" />

---

## How to Run

### Option 1: Google Colab (Recommended)

Open and run:


