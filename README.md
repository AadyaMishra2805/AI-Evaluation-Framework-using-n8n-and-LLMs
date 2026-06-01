# AI Evaluation Framework using n8n, OpenAI, and Google Sheets

## Overview

AI Evaluation Framework is an automated system designed to assess the performance of Large Language Models (LLMs) using benchmark datasets. The project evaluates model responses for factual accuracy, consistency, and reliability by comparing generated answers against expected answers and assigning automated scores.

The workflow is built using n8n for orchestration, OpenAI GPT-4o-mini for response generation and evaluation, and Google Sheets for dataset storage and result tracking.

---

## Problem Statement

Large Language Models can produce inaccurate, inconsistent, or hallucinated responses. Manual evaluation is time-consuming and difficult to scale. This project automates the evaluation process, allowing AI systems to be tested against a predefined benchmark dataset and scored objectively.

---

## Objectives

* Create a benchmark dataset for AI evaluation.
* Automatically generate responses using an LLM.
* Compare generated responses against expected answers.
* Score responses as correct or incorrect.
* Identify factual errors and failure cases.
* Support adversarial and red-team style testing.
* Generate structured evaluation results for analysis.

---

## Features

### Benchmark Dataset Evaluation

A collection of evaluation questions is stored in Google Sheets. Each question contains an expected answer used as the reference for evaluation.

### Automated Response Generation

Questions are automatically sent to an LLM through an n8n workflow. Generated responses are collected and stored for analysis.

### AI-Based Evaluation

A second evaluation model acts as a judge and compares expected answers with generated responses.

### Automated Scoring

Responses are assigned:

* 1 = Correct
* 0 = Incorrect

Scores are automatically written back to the dataset.

### Result Tracking

All generated responses and scores are stored in Google Sheets for easy review and analysis.

### Adversarial Testing Support

The framework can be extended to test:

* Prompt injection attacks
* Hallucination scenarios
* Contradictory statements
* Jailbreak attempts
* Bias-related prompts

---

## Workflow

```text
Google Sheets Dataset
          ↓
Read Questions (n8n)
          ↓
OpenAI GPT-4o-mini
          ↓
Generate Responses
          ↓
Store Responses
          ↓
AI Evaluator
          ↓
Compare with Expected Answers
          ↓
Generate Scores
          ↓
Store Results
          ↓
Analysis & Reporting
```

---

## Technology Stack

* n8n
* OpenAI GPT-4o-mini
* Google Sheets
* Prompt Engineering

---

## Dataset Structure

| Column          | Description          |
| --------------- | -------------------- |
| id              | Unique identifier    |
| category        | Question category    |
| question        | Benchmark question   |
| expected_answer | Reference answer     |
| model_response  | LLM generated answer |
| score           | Evaluation result    |

---

## Evaluation Methodology

### Response Generation

The model receives a benchmark question and generates an answer.

### Response Evaluation

The evaluator model compares:

* Expected Answer
* Model Response

The evaluator then determines whether the response is correct.

### Scoring

| Score | Meaning   |
| ----- | --------- |
| 1     | Correct   |
| 0     | Incorrect |

---

## Example

### Input Question

```text
What is the capital of France?
```

### Expected Answer

```text
Paris
```

### Model Response

```text
The capital of France is Paris.
```

### Evaluation Result

```text
1
```

---

## Future Improvements

* Multi-model comparison (GPT, Gemini, Claude, Llama)
* Hallucination detection metrics
* Consistency testing
* Adversarial prompt benchmark datasets
* Automated PDF report generation
* Interactive dashboards
* Performance analytics

---

## Learning Outcomes

Through this project, the following concepts were explored:

* AI Evaluation
* LLM Benchmarking
* Prompt Engineering
* Automated Scoring Systems
* Workflow Automation with n8n
* AI Safety and Red Teaming
* Failure Pattern Analysis
* Evaluation Pipeline Design

---

## Conclusion

This project demonstrates how workflow automation and LLMs can be combined to create a scalable AI evaluation system. The framework automates the process of benchmarking, scoring, and analyzing model responses, making it easier to measure the quality and reliability of AI systems.
