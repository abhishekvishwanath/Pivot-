# Pivot — Adaptive Strategy Generator and Evaluator for Chaotic Events

> **Pivot** is an AI-driven decision-support framework that generates, simulates, and objectively evaluates strategies for complex and rapidly changing events.

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![AI](https://img.shields.io/badge/AI-Strategy%20Generation-purple)
![Simulation](https://img.shields.io/badge/Simulation-Deterministic-orange)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow)

---

## Overview

Modern disasters and large-scale disruptions such as wildfires, tsunamis, floods, inflationary crises, wars, and supply-chain disruptions involve rapidly changing conditions, limited resources, and multiple interdependent factors.

Traditional decision-support systems often focus on a specific task such as prediction, evacuation routing, risk assessment, or resource allocation. AI systems can generate recommendations, but generating a plausible recommendation does not necessarily establish whether that strategy is feasible, effective, or robust.

**Pivot** addresses this gap by combining:

1. **AI-based strategy generation**
2. **Structured strategy representation**
3. **Mathematical / simulation-based environment modelling**
4. **Deterministic strategy execution**
5. **Quantitative strategy evaluation**
6. **Continuous adaptation when the environment changes**

The core idea is to create a controlled **"what-if laboratory"** where multiple strategies can be generated and tested under simulated conditions before they are considered by human decision-makers.

---

## Problem Statement

Complex and unforeseen events require rapid and adaptive decision-making. However, developing effective strategies is difficult because the environment is:

* Dynamic
* Uncertain
* Resource-constrained
* Influenced by multiple interacting variables
* Subject to changing conditions

Existing AI systems can generate recommendations, but a generated strategy alone does not demonstrate that it will produce desirable outcomes.

Pivot therefore aims to develop a framework that can:

> **Generate → Simulate → Evaluate → Adapt**

strategies for complex disruptive events.

---

## Objectives

The major objectives of Pivot are:

### 1. AI Strategy Generation

Develop an AI-based strategy-making agent capable of generating structured and actionable strategies in response to complex events.

### 2. Environment Modelling

Develop mathematical, rule-based, or simulation-based models representing the behaviour and dynamics of selected domains.

### 3. Strategy Evaluation

Execute generated strategies within the corresponding environment and evaluate their outcomes using predefined metrics and constraints.

### 4. Robustness Analysis

Test strategies under different environmental conditions and event severities to understand their robustness.

### 5. Extensibility

Design a modular architecture that allows additional event types, environment models, AI models, and evaluation criteria to be incorporated.

---

# System Architecture

Pivot follows a modular architecture consisting of the following major components:

```text
                    ┌───────────────────────┐
                    │   Event / Conditions  │
                    │                       │
                    │ • Current State       │
                    │ • Resources           │
                    │ • Constraints         │
                    │ • Objectives          │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ AI Strategy Generator │
                    │                       │
                    │ Generates one or more │
                    │ possible strategies   │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Structured Strategy   │
                    │                       │
                    │ • Actions             │
                    │ • Priorities          │
                    │ • Resources           │
                    │ • Timing              │
                    │ • Conditions          │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Environment Simulator │
                    │                       │
                    │ Executes strategy     │
                    │ under simulated       │
                    │ conditions             │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │    Outcome Engine     │
                    │                       │
                    │ • Response Time       │
                    │ • Resource Usage      │
                    │ • Damage              │
                    │ • Evacuation          │
                    │ • Infrastructure      │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Evaluation Engine     │
                    │                       │
                    │ Deterministic Metrics │
                    │ & Constraint Checks   │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Strategy Analysis     │
                    │                       │
                    │ • Score               │
                    │ • Trade-offs          │
                    │ • Risks               │
                    │ • Strengths           │
                    └───────────┬───────────┘
                                │
                                ▼
                    ┌───────────────────────┐
                    │ Human Decision Maker  │
                    └───────────────────────┘

          Environment changes ───────► Re-generation
```

The architecture deliberately separates **strategy generation** from **strategy evaluation**. The AI generates possible strategies, while the simulation and evaluation components independently determine the measurable outcomes.

---

# Core Workflow

Pivot operates through the following workflow:

### Step 1 — Observe

The system receives the current state of the environment.

Possible inputs include:

* Event severity
* Location information
* Population information
* Available resources
* Infrastructure status
* Road availability
* Hospital capacity
* Environmental conditions
* Operational constraints

---

### Step 2 — Generate

The AI strategy generator receives:

* Current environmental state
* Objectives
* Available resources
* Constraints

It generates one or more candidate strategies.

Example:

```json
{
    "strategy_id": "strategy_001",
    "objective": "minimize_casualties",
    "actions": [
        {
            "action": "evacuate_zone",
            "zone": "A",
            "priority": 1
        },
        {
            "action": "allocate_ambulances",
            "count": 5,
            "priority": 2
        }
    ],
    "resources": {
        "ambulances": 5,
        "rescue_teams": 3
    }
}
```

---

### Step 3 — Structure

The generated strategy is converted into a structured representation that can be interpreted by the simulation environment.

The structured strategy may contain:

* Actions
* Priorities
* Resource allocation
* Timing
* Conditions
* Triggers
* Constraints

This provides a common interface between the AI component and the environment simulator.

---

### Step 4 — Simulate

The structured strategy is executed inside a mathematical or simulation-based environment.

The simulator can model factors such as:

* Hazard propagation
* Population movement
* Road availability
* Resource consumption
* Hospital capacity
* Infrastructure damage
* Evacuation progress
* Recovery time

The environment evolves over multiple time steps.

---

### Step 5 — Generate Outcomes

The simulation produces measurable outcomes.

Examples include:

| Outcome               | Description                                    |
| --------------------- | ---------------------------------------------- |
| Response Time         | Time required to achieve the intended response |
| Resource Usage        | Amount of resources consumed                   |
| Casualties            | Number of affected or lost individuals         |
| Protected Population  | Population successfully protected              |
| Infrastructure Damage | Simulated damage to infrastructure             |
| Evacuation Progress   | Percentage of population evacuated             |
| Recovery Time         | Time required to recover from the event        |
| Constraint Violations | Violations of operational/resource constraints |

---

### Step 6 — Evaluate

The evaluation engine calculates predefined metrics.

Importantly, the evaluation engine is designed to be **deterministic and independent of the AI strategy generator**.

The system can evaluate:

* Effectiveness
* Resource efficiency
* Response time
* Damage reduction
* Constraint satisfaction
* Robustness
* Overall strategy score

---

### Step 7 — Analyze

The resulting metrics can be used to understand:

* Strategy strengths
* Strategy limitations
* Resource trade-offs
* Risks
* Constraint violations
* Performance under different conditions

The system can then regenerate strategies when the environment changes.

---

# Continuous Adaptation

One of the key concepts of Pivot is that the system does not depend on a single fixed strategy.

```text
          ┌──────────────┐
          │    Observe   │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │   Generate   │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │   Simulate   │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │   Evaluate   │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │    Adapt     │
          └──────┬───────┘
                 │
                 └──────────────► Environment changes
```

When significant changes occur in the environment, Pivot can return to the strategy generation stage and produce updated strategies.

---

# Evaluation Metrics

Pivot uses measurable metrics rather than relying on the AI model itself to judge whether a strategy is successful.

## Effectiveness

Measures how successfully the strategy achieves the defined objective.

## Resource Efficiency

Measures the amount and utilization of available resources.

## Response Time

Measures the time required to achieve the desired outcome.

## Impact / Damage Reduction

Measures reduction in negative outcomes such as:

* Casualties
* Losses
* Affected population
* Infrastructure damage
* Other scenario-specific impacts

## Constraint Satisfaction

Checks whether the strategy respects:

* Resource limits
* Operational constraints
* Environmental constraints
* Other predefined requirements

## Robustness

Tests strategy performance under changes in:

* Event severity
* Initial conditions
* Resource availability
* Environmental conditions

## Overall Strategy Score

A configurable weighted combination of relevant performance metrics.

---

# Initial Application Scenarios

The framework is designed to support multiple disruptive-event domains.

The initial project scope includes:

### Natural Disaster Scenarios

* Wildfires
* Tsunamis
* Floods
* Other selected disaster scenarios

### Macro-economic / Geopolitical Scenarios

* Inflationary disruptions
* War-related disruptions
* Supply-chain disruptions

The architecture is designed so that additional scenarios can be added later without redesigning the entire framework.

---

# Example Use Case

Consider a simulated wildfire scenario.

### Initial Conditions

```text
Event:
Wildfire

Population:
50,000

Available Ambulances:
10

Rescue Teams:
5

Available Shelters:
8

Road Status:
70% available

Event Severity:
High
```

The AI strategy generator may generate multiple candidate strategies:

```text
Strategy A
→ Prioritize evacuation of Zone A

Strategy B
→ Prioritize hospital/resource allocation

Strategy C
→ Evacuate high-risk zones based on road availability
```

Each strategy is then independently simulated.

The evaluation engine can produce results such as:

```text
                 Strategy A   Strategy B   Strategy C
-------------------------------------------------------
Casualties          ...           ...           ...
Response Time       ...           ...           ...
Resources Used      ...           ...           ...
Evacuated           ...           ...           ...
Infrastructure     ...           ...           ...
Constraint Errors   ...           ...           ...
Overall Score       ...           ...           ...
```

The system presents the measured outcomes so that a human decision-maker can examine the alternatives.

---

# Project Structure

A suggested modular repository structure is:

```text
pivot/
│
├── README.md
├── requirements.txt
├── .gitignore
├── LICENSE
│
├── src/
│   │
│   ├── strategy/
│   │   ├── __init__.py
│   │   ├── generator.py
│   │   ├── schema.py
│   │   └── prompts.py
│   │
│   ├── simulation/
│   │   ├── __init__.py
│   │   ├── environment.py
│   │   ├── wildfire.py
│   │   ├── tsunami.py
│   │   └── dynamics.py
│   │
│   ├── evaluation/
│   │   ├── __init__.py
│   │   ├── evaluator.py
│   │   ├── metrics.py
│   │   └── constraints.py
│   │
│   ├── data/
│   │   ├── __init__.py
│   │   └── loader.py
│   │
│   ├── visualization/
│   │   ├── __init__.py
│   │   └── dashboard.py
│   │
│   └── config/
│       └── settings.py
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── synthetic/
│
├── experiments/
│   ├── wildfire/
│   └── tsunami/
│
├── tests/
│   ├── test_strategy.py
│   ├── test_simulation.py
│   └── test_evaluation.py
│
└── notebooks/
    └── experiments.ipynb
```

> The exact folder structure may evolve as implementation progresses.

---

# Technology Stack

The project is designed primarily around Python and open-source technologies.

### Core

* Python
* NumPy
* Pandas
* Pydantic

### AI / LLM

The strategy-generation layer can be connected to:

* Large Language Models
* Open-source language models
* LLM APIs

The exact model/provider can be configured independently of the simulation and evaluation modules.

### Simulation

Depending on the selected scenario, the environment can use:

* Python-based mathematical models
* Rule-based simulation
* Agent-based simulation
* Custom domain-specific simulation models

### Visualization

Results can be presented using Python visualization libraries and/or a dashboard layer.

---

# Installation

## 1. Clone the repository

```bash
git clone https://github.com/<your-username>/pivot.git
cd pivot
```

Replace `<your-username>` with your GitHub username.

---

## 2. Create a virtual environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

# Configuration

If the strategy-generation component uses an external LLM API, store credentials in environment variables rather than directly inside source code.

Example:

```env
LLM_API_KEY=your_api_key_here
```

Do **not** commit API keys or other credentials to GitHub.

Add the following to `.gitignore`:

```text
.env
venv/
__pycache__/
*.pyc
.ipynb_checkpoints/
```

---

# Running the Project

The exact execution command depends on the final implementation.

For a Python entry point, an example structure could be:

```bash
python main.py
```

or:

```bash
python -m src.main
```

For a dashboard-based implementation, the command may be:

```bash
streamlit run app.py
```

Use the command corresponding to the entry point implemented in the repository.

---

# Design Principles

## 1. Separation of Responsibilities

Pivot separates:

```text
AI Strategy Generation
          ↓
Strategy Representation
          ↓
Environment Simulation
          ↓
Outcome Generation
          ↓
Deterministic Evaluation
```

This prevents the AI model from directly determining whether its own strategy was successful.

---

## 2. Deterministic Evaluation

Whenever possible, the same strategy and simulation conditions should produce reproducible evaluation results.

This enables controlled comparison and experimentation.

---

## 3. Modular Architecture

The framework should allow:

```text
New AI Model
     ↓
Same Strategy Interface
     ↓
Same Simulator
     ↓
Same Evaluation Engine
```

Similarly, a new environment can be added without changing the complete system.

---

## 4. Human-in-the-Loop

Pivot is designed as a **decision-support and strategy-testing system**, not as a replacement for human decision-makers.

The final decision remains with the human user.

---

## 5. What-If Experimentation

The framework enables controlled experimentation with questions such as:

* What happens if available resources are reduced?
* What happens if the event severity increases?
* What happens if a major road becomes unavailable?
* How does a strategy perform under different initial conditions?
* Which constraints are violated?
* How does strategy performance change over time?

---

# Limitations

Pivot is a simulation and decision-support framework and does not attempt to model reality perfectly.

The project does **not** aim to:

* Directly deploy generated strategies in real-world disasters or economic situations.
* Replace government authorities, emergency-response teams, domain experts, or professional decision-makers.
* Guarantee prediction of real-world events.
* Guarantee exact real-world outcomes.
* Model every factor involved in natural disasters or macro-economic systems.
* Provide one universal environment model for every possible disruptive event.

These limitations are important because simulation outcomes depend on the assumptions, parameters, data, and models used by the environment.

---

# Dataset

Depending on the selected scenario, Pivot may use:

* Publicly available datasets
* Synthetic datasets
* Simulated data
* Scenario-specific parameters

Synthetic and simulated data can be useful for controlled experiments where real-world data is unavailable or insufficient.

---

# Research Foundation

The project builds upon research in areas including:

* Artificial Intelligence
* Disaster Management
* Decision Support Systems
* Simulation
* Evacuation Planning
* Resource Allocation
* Digital Twins
* Multi-Agent Systems
* Machine Learning
* Spatial Decision Support

The project synopsis includes research covering wildfire management, evacuation modelling, digital twins, disaster management, spatial decision support, and AI-based disaster response.

The proposed contribution is the integration of:

```text
AI Strategy Generation
          +
Deterministic Simulation
          +
Independent Quantitative Evaluation
```

into a unified framework.

---

# Expected Deliverables

The project aims to produce:

* AI-based strategy generation agent
* Structured strategy representation
* Simulation environments for selected scenarios
* Strategy evaluation engine
* Quantitative evaluation reports
* Visualization/reporting component
* Modular framework for additional scenarios

These deliverables are aligned with the project synopsis.

---

# Future Scope

Potential future extensions include:

* Additional disaster environments
* Multi-agent strategy generation
* Real-time data integration
* GIS-based simulation
* Digital-twin environments
* Advanced evacuation modelling
* Supply-chain disruption simulation
* Economic scenario modelling
* Reinforcement-learning-based strategy generation
* Multi-objective optimization
* Interactive dashboards
* Larger-scale scenario experimentation

---

# Project Status

**Current Status:** 🚧 Under Development

The project is being developed as a modular research prototype.

Future releases will document:

* Implemented environments
* Supported AI models
* Evaluation metrics
* Experimental results
* Benchmark scenarios
* Reproducibility instructions

---

# Team

### Project

**Pivot — An Adaptive Strategy Generator and Evaluator for Chaotic Events**

### Department

Department of Artificial Intelligence & Machine Learning
Dayananda Sagar College of Engineering
Bengaluru, India

### Team Members

* **B. Nikhi Tej**
* **Abhishek V**
* **Madhan Kumar R**
* **Nenad Matada**

### Faculty Guide

**Dr. Reshma**
Associate Professor

### Industry Expert

**Irshad Ahmed Mohammed Safeer**
Senior Solutions Architect
Dubai Electric & Water Authority

---

# Disclaimer

Pivot is an academic research and software-prototyping project.

The strategies and outcomes generated by the system are based on simulated environments, assumptions, available data, and predefined evaluation criteria. They should not be interpreted as guaranteed real-world outcomes or as a replacement for qualified human decision-making.

---

# License

This project is currently intended for academic and research purposes.

A formal open-source license can be added when the project licensing terms are finalized.

