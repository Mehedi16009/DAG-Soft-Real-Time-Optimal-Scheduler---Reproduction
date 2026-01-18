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

![Methodology Figure](./results/methodology.png)

The figure above shows the workflow:

1. Generate DAGs with random topology and parameters  
2. Compute response-time bounds (original and refined)  
3. Validate with brute-force scheduling for small DAGs  
4. Produce experimental results and figures  

---

## Experimental Results (Reproduced Figures)

### Figure 8(a): Response-time bound vs. Normalized Utilization

![Fig 8(a)](./results/fig8a.png)

### Figure 8(b): Response-time bound vs. Processor Count

![Fig 8(b)](./results/fig8b.png)

### Figure 8(c): Response-time bound vs. Edge Probability

![Fig 8(c)](./results/fig8c.png)

---

## Main Equations (Core Concepts)

### 1. DAG Task Model

A DAG task is defined as:

- \( G = (V, E) \)  
- Nodes \( v \in V \) represent subtasks
- Edges \( (u, v) \in E \) represent precedence constraints

Each node has:

- Worst-case execution time \( C_v \)
- Parallelism cap \( P_v \)

### 2. Utilization

Total utilization:

\[
U = \frac{\sum_{v \in V} C_v}{T}
\]

Node-level utilization:

\[
u_v = \frac{C_v}{T}
\]

### 3. Response-Time Bound (Original)

\[
R \le \max_{\ell} \left\{ L(\ell) + \frac{W - L(\ell)}{m} \right\}
\]

Where:

- \( L(\ell) \) is the length of a transformed path in \( G(\ell) \)
- \( W = \sum_{v \in V} C_v \)

### 4. Refined Bound (Pruned Paths)

\[
R \le \max_{\ell} \left\{ L_f(\ell) + \frac{W - L_f(\ell)}{m} \right\}
\]

Where \( L_f(\ell) \) is the length of a **feasible** generalized path in a pruned transformed DAG.

---

## How to Run

### Option 1: Google Colab (Recommended)

Open and run:


