# Day 03 – Foundational Model vs Reasoning Model

## Topic
**Foundational Models vs Reasoning Models**

## Assignment

Compare a foundational model with a reasoning model using different problem-solving tasks and analyze the impact of reasoning effort on latency, token usage, and accuracy.

## Tasks Completed

### 1. Model Comparison

Compared:

- Foundational Model: `gpt-4o-mini`
- Reasoning Model: `o4-mini`

Tested the models on:

- Logic puzzle
- Math problem
- Planning task

### 2. Reasoning Effort Experiment

Tested the reasoning model using:

- Low
- Medium
- High

For the math problem, all three settings produced the correct answer.

| Reasoning Effort | Latency | Reasoning Tokens | Total Tokens | Correct |
|---|---:|---:|---:|---|
| Low | 2.12 sec | 192 | 444 | Yes |
| Medium | 2.64 sec | 320 | 566 | Yes |
| High | 3.27 sec | 384 | 628 | Yes |

### Observation

Increasing reasoning effort increased both reasoning-token usage and response latency. However, all three settings produced the correct answer for the tested math problem.

For this particular task, **low reasoning effort was sufficient** because it achieved the correct result with the lowest latency and token usage.

### 3. Design Choices

#### Scenario 1 – Healthcare

- **Model:** Reasoning Model
- **Deployment:** Edge / On-Prem

A reasoning model is suitable for analyzing medication combinations and identifying potential drug-interaction risks. Edge/On-Prem deployment provides better control over sensitive healthcare data and satisfies hospital data-governance requirements.

#### Scenario 2 – Government / Defense

- **Model:** Reasoning Model
- **Deployment:** Edge / On-Prem

A reasoning model is suitable for long case-file summarization and cross-referencing information. Edge/On-Prem deployment is required because the environment is air-gapped and cannot connect to public cloud services.

## Concepts Covered

- Foundational Models
- Reasoning Models
- Reasoning Effort
- Token Usage
- Latency
- Model Comparison
- Model Selection
- Cloud vs Edge/On-Prem Deployment
