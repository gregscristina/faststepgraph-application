# faststepgraph-application


This repository contains experiments and applications of the Fast Step Graph algorithm for the discovery of high-dimensional Gaussian Graphical Models (GGMs)

These experiments are being developed as part of an academic research project by **Grecia C. G. Rivera**, **Prof. Juan G. Colonna**, and **Prof. Marcelo Ruiz**.

---

## About Fast Step Graph

Fast Step Graph is an optimized implementation in R of the stepwise approach for estimating the **precision matrix (Ω)** of high-dimensional Gaussian Graphical Models, especially in contexts where the number of features is much larger than the number of observations (*p >> n*), such as in genomics.

This implementation builds upon the original stepwise method and improves:

- **Computational efficiency**, enabling inference on larger graphs
- **Code structure**, by removing redundant operations and avoiding slow list manipulations
- **Memory handling**, though it still requires substantial memory due to storing a dense graph

You can find the algorithm source code at [FastStepGraph GitHub repository](https://github.com/juancolonna/FastStepGraph).
