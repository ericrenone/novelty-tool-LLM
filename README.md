# Novelty Functional for LLM Outputs

## Overview

This repository implements a **real-time, research-grade novelty functional** for Large Language Models (LLMs).  

The functional combines:

1. **KL Divergence vs Uniform** – measures the model's prediction confidence.  
2. **Diagonal Fisher Trace** – measures parameter sensitivity to input.  
3. **Length Normalization** – penalizes long or repetitive inputs.  

**Novelty Score**:  

\[
\text{Novelty}(x) = \frac{\text{KL}(p_\theta \| U) \cdot \text{FisherTrace}(x)}{L(x)}
\]

High novelty implies: confident, informative, and parameter-sensitive input.  
Low novelty implies generic, memorized, or low-information content.

---

## Features

- **Single-file implementation** – no external submodules.  
- **Real-time dynamic simulation** with live visualization.  
- **Seeded, reproducible experiments** for deterministic results.  
- **Console + popout visualization** for KL, Fisher, and Novelty.  
- **Compatible with any **HuggingFace causal LM**.  

