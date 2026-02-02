**Identity-Geometry:**

**Core components:**

1. **FisherInfo (diagonal trace)** — Estimates the expected squared gradient of the log-likelihood w.r.t. model parameters:
   [
   F_\theta \approx \mathbb{E}*{x \sim D} \left[ \left( \frac{\partial \log p*\theta(x)}{\partial \theta} \right)^2 \right]
   ]
2. **KLDivergence** — Computes KL divergence between model softmax outputs and uniform (or future empirical) priors:
   [
   \mathrm{KL}(p \parallel u) = \sum_i p_i \log \frac{p_i}{u_i}
   ]
3. **NoveltyFunctional** — Computes a heuristic novelty score for a given input `x`:
   [
   \text{Novelty}(x) = \frac{\mathrm{KL}(\text{softmax}(logits_x) \parallel \text{uniform})}{n_\text{tokens}/\text{normalizer} + \epsilon}
   ]
   This score is **length-normalized** and optionally extensible with Fisher trace weighting.

**Design principles:**

* **Scientific rigor**: explicit equations, numerically stable, reproducible, and device-aware.
* **Minimalism**: only core algorithms are implemented; no heuristics or extraneous tooling.
* **Modularity**: structured via dataclasses for configuration (`FisherConfig`, `KLConfig`, `NoveltyConfig`).
* **Pip-installable**: fully functional minimal package compatible with PyTorch 2.0+ and HuggingFace Transformers 4.40+.

**Intended use:**
For research experiments evaluating **novelty, information density, or rational attention cost** in LLM generations or prompts. Serves as a reproducible baseline for **information-theoretic analysis** of language models.

**License:** Apache 2.0



Do you want me to do that?
