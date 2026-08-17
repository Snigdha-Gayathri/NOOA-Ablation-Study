# NOOA Ablation Study

## Controlled Evaluation of Agent Harness Components

**NOOA** is an experimental study investigating how individual **agent-harness components** affect the reliability, efficiency, and execution behavior of tool-using AI agents.

Modern agent systems often combine mechanisms such as typed interfaces, validation, retries, persistent state, dynamic context, structured logging, termination controls, and multi-agent contracts. When these components are introduced simultaneously, it becomes difficult to determine which mechanisms actually contribute to better agent behavior.

This study addresses that problem through **controlled ablation experiments**, isolating the contribution of individual harness capabilities while keeping the experimental environment consistent.

---

## Research Question

> **Which components of an agent harness actually improve agent performance, reliability, and execution behavior, and what costs do they introduce?**

The study evaluates this through controlled configurations and analyzes not only aggregate performance, but also the underlying failure behavior of each configuration.

---

## What Is Being Studied?

The ablation study investigates the contribution of the following agent-harness mechanisms:

| Component                    | Role                                                     |
| ---------------------------- | -------------------------------------------------------- |
| **CodeAct**                  | Enables executable actions through generated code        |
| **Typed I/O**                | Enforces structured interfaces between components        |
| **Validation + Retry**       | Detects invalid outputs and attempts controlled recovery |
| **Pass-by-Reference**        | Reduces unnecessary data movement and duplication        |
| **Persistent State**         | Preserves information across execution steps             |
| **Structured Event Logging** | Provides machine-readable execution traces               |
| **Static Context**           | Provides fixed contextual information                    |
| **Dynamic Context**          | Allows context to evolve during execution                |
| **Validated Termination**    | Prevents premature or invalid task termination           |
| **Multi-Agent Contracts**    | Enforces structured communication between agents         |
| **Failure Recovery**         | Enables controlled recovery from execution errors        |

The configurations progressively introduce these mechanisms to measure their individual and combined effects.

---

## Experimental Configurations

The study evaluates four primary configurations, **A through D**, representing progressively capable agent-harness designs.

| Configuration | Purpose                                                         |
| ------------- | --------------------------------------------------------------- |
| **A**         | Establishes baseline behavior with minimal harness capabilities |
| **B**         | Introduces core reliability and structured-execution mechanisms |
| **C**         | Adds state, context, and execution-oriented mechanisms          |
| **D**         | Evaluates the complete harness configuration                    |

The experimental notebook contains the exact configuration definitions and execution logic.

---

## Evaluation Methodology

The study evaluates each configuration across multiple dimensions rather than reducing agent behavior to a single score.

### Reliability

* Task completion
* Execution success
* Failure frequency
* Recovery behavior

### Efficiency

* Execution overhead
* Data movement
* Additional orchestration cost
* Effect of state and context mechanisms

### Behavioral Analysis

Each unsuccessful execution is analyzed according to its underlying failure mode.

This makes it possible to distinguish between:

* invalid outputs
* tool execution failures
* validation failures
* state-related failures
* context-related failures
* contract violations
* termination failures
* recovery failures
* serialization and data-transfer overhead

This failure-level analysis is important because two configurations can achieve similar aggregate results while exhibiting very different failure patterns.

---

## Statistical Analysis

The study uses controlled, paired comparisons to evaluate differences between configurations under comparable experimental conditions.

The analysis includes:

* paired comparisons
* significance testing
* effect-size analysis
* failure-rate comparisons
* interpretation of practical significance

Statistical results are considered alongside observed behavioral differences rather than treating statistical significance alone as evidence of architectural superiority.

---

## Reproducibility

The complete experiment is contained in the accompanying Jupyter notebook.

### Run the Experiment

Open:

`nooa_ablation_study.ipynb`

The notebook contains the experimental implementation, configuration definitions, execution procedure, metric computation, statistical analysis, and failure analysis.

The study can be executed in **Google Colab** or a compatible Jupyter environment.

---

## Repository Structure

```text
NOOA-Ablation-Study/
│
├── images/
│
├── results/
│
├── nooa_ablation_study.ipynb
│
└── README.md
```

### `images/`

Contains visualizations and figures generated for the study.

### `results/`

Contains the experimental outputs and analysis results.

### `nooa_ablation_study.ipynb`

The primary research artifact containing the complete experimental implementation and analysis.

---

## Experimental Controls

The study is designed to isolate the effect of the agent harness rather than unrelated changes in the experimental environment.

Where applicable, the following are kept consistent across configurations:

* underlying model behavior
* task distribution
* evaluation procedure
* scoring methodology
* execution constraints
* experimental protocol

This controlled setup reduces confounding factors when comparing configurations.

---

## Key Design Principle

The central premise of NOOA is simple:

> **Agent architecture should be evaluated component by component, not only as a complete system.**

A sophisticated agent harness may contain many useful mechanisms, but complexity alone does not establish that each mechanism provides value.

A component should ideally demonstrate one or more of the following:

1. improved reliability,
2. reduced failure frequency,
3. improved execution efficiency,
4. improved recovery behavior, or
5. meaningful observability.

The ablation methodology provides a way to measure these effects independently.

---

## Limitations

The results should be interpreted within the scope of the experimental environment.

### Controlled Task Environment

The experiments use controlled tasks and therefore may not fully represent the complexity of production agent workloads.

### Model Behavior

The experimental setup includes controlled or simulated model behavior. Results should therefore not be interpreted as direct measurements of frontier LLM performance.

### CodeAct Environment

The CodeAct component is evaluated within the study's controlled execution environment and does not capture every property of a production-grade sandbox.

### Generalization

Results are specific to the evaluated configurations, tasks, and implementation. Broader conclusions require replication across different models, workloads, and execution environments.

### Component Interactions

Individual ablations do not completely characterize all higher-order interactions between every possible combination of harness components.

---

## Why This Matters

As agentic systems become more complex, it becomes increasingly easy to add another layer of memory, validation, orchestration, context management, or recovery without knowing whether that layer meaningfully improves the system.

NOOA takes a systems-oriented approach:

**Isolate → Execute → Measure → Analyze → Attribute**

The objective is not to claim that one agent architecture is universally optimal.

The objective is to establish a more rigorous way to reason about **which engineering mechanisms actually contribute to agent reliability and performance**.

---

## Research Artifact

This repository contains the complete experimental artifact for the NOOA ablation study, including:

* experimental implementation
* ablation configurations
* evaluation logic
* generated results
* statistical analysis
* failure analysis
* visualizations

The notebook and accompanying outputs are intended to make the experimental process transparent and reproducible.

---

## Author

**Snigdha Gayathri**

CSE - Artificial Intelligence & Machine Learning

GitHub: [Snigdha-Gayathri](https://github.com/Snigdha-Gayathri)

---

## Citation

If you reference or build upon this work, please cite:

```bibtex
@misc{gayathri2026nooa,
  title  = {NOOA Ablation Study: Controlled Evaluation of Agent Harness Components},
  author = {Snigdha Gayathri},
  year   = {2026},
  url    = {https://github.com/Snigdha-Gayathri/NOOA-Ablation-Study}
}
```
