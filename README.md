## Hi there, I'm Nicola 👋🏻

I am a physicist (and many other things) based in Rome. I hold a Ph.D. in Physics, specifically centered in reservoir computing and the modelling of complex spatio-temporal systems: echo state networks, computational neuroscience, whole-brain mean-field models, and climate forecasting. I now work at the intersection of that dynamical-systems background and applied machine learning, with a particular focus on generative AI, retrieval-augmented systems, and the question of whether the explanations we produce for large language models can actually be trusted.

The thread that connects most of what I build is *epistemic honesty in machine learning systems* — measuring what a method really tells us rather than what we hope it tells us, and refusing to let a confident-looking number stand in for evidence it does not support.

### Current focus

- **Explainable AI for large language models.** Faithfulness evaluation of feature attributions, with an emphasis on the identifiability problems that arise when perturbation-based explainers and perturbation-based evaluators are confounded by construction.
- **Generative AI in production.** End-to-end LLM and RAG pipelines, agentic architectures, and responsible-AI practice aligned with the European Union Artificial Intelligence Act.
- **Dynamical-systems methods for sequence models.** State-space and attractor-geometry perspectives on modern architectures, carried over from my reservoir-computing work.
---

## Selected projects

### Research and machine learning

**[operator-variance](https://github.com/nicoalbo0/operator-variance)** (Python). 
A research library that measures how much perturbation-based faithfulness scores (comprehensiveness, sufficiency, area under the deletion curve) depend on which perturbation operator you use: deletion, masking, neutral replacement, padding, or counterfactual. It reports cross-operator variance and Kendall-τ ranking disagreement, so the operator dependence of a faithfulness score becomes explicit and auditable instead of hidden behind a single number. It diagnoses instability, not the "correct" operator. Ships with five attributors (integrated gradients, LIME, gradient × input, attention rollout, occlusion), a reproducible benchmark runner that pins model and tokenizer revisions, and an offline, deterministic test suite.

**[cross-scale-reservoir-computing](https://github.com/nicoalbo0/cross-scale-reservoir-computing)** (Julia).
`CrossScaleRC`, a package for single- and multi-layer echo state networks with spatial blocking, for forecasting high-dimensional spatio-temporal systems such as the Kuramoto–Sivashinsky equation and sea surface temperature fields. Includes deep ESN and next-generation RC baselines and a full multi-resolution data pipeline. This is the code behind the peer-reviewed paper below.
> *Cross-scale reservoir computing for large spatio-temporal forecasting and modeling.* **Neurocomputing** (2026). [doi:10.1016/j.neucom.2026.133849](https://doi.org/10.1016/j.neucom.2026.133849)

### Developer and agentic tooling

**[never-again](https://github.com/nicoalbo0/never-again)** (Python).
A local-first failure memory for coding agents, exposed over the Model Context Protocol. When an agent hits an error, it can check whether that same failure was already solved in an earlier session instead of re-debugging it from scratch; solved fixes are written back with a compact prevention rule. Runs on a local SQLite file with no server and no data leaving the machine, blends keyword and optional semantic search with reciprocal rank fusion, and — importantly — abstains when the match is weak rather than returning a confident wrong answer.

**[proofledger](https://github.com/nicoalbo0/proofledger)** (TypeScript).
A local-first Claude Code plugin and CLI that gates writing product code on machine-verified real-world evidence rather than an LLM's opinion. A gating assumption opens the build gate only when confirmed by re-fetched artifacts at the level of real money (verified Stripe pre-authorisations), with hash-locked falsifiable thresholds that cannot be quietly moved to force a pass. The verdict logic is fully mechanical: no language model ever writes an assumption's status or opens the gate.

**[tabelog-concierge](https://github.com/nicoalbo0/tabelog-concierge)** (Python).
A terminal chatbot for planning restaurant meals in Japan, running entirely on a local Ollama model with no API key and no cloud. It searches Tabelog and returns a shortlist with ratings, budgets, and map links, respecting robots.txt at runtime and storing no scraped data. A small, self-contained study in building a useful tool-calling agent under strict local and ethical constraints.
