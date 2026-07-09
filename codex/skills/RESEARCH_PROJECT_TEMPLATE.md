# Project AGENTS.md — Research Project Guidance

## Project Purpose

This repository supports research and development for medical AI, LLM agents, healthcare workflow automation, multimodal clinical data analysis, or related academic/administrative research work.

The goal is to produce reproducible code, interpretable analysis, and outputs that can be used in papers, reports, presentations, or internal research documents.

---

## Repository Expectations

Before making changes, understand:

1. What research question or operational problem this repository addresses.
2. What data is used.
3. What model, pipeline, or document output is affected.
4. How the result will be evaluated.
5. Whether privacy, security, or medical data governance issues are involved.

Do not make large structural changes without explaining why.

---

## Preferred Workflow

For each task:

1. Inspect the relevant files.
2. Summarize the current structure.
3. Identify the minimal necessary change.
4. Implement the change.
5. Add or update tests when possible.
6. Run available checks.
7. Summarize what changed and how to verify it.

---

## Code Style

Use clear, research-friendly Python.

Prefer:

* readable function names
* explicit config values
* type hints when useful
* small functions
* meaningful logging
* reproducible random seeds
* clear input/output paths
* saved intermediate and final results

Avoid:

* hidden hardcoding
* silent failure
* unclear global variables
* changing data in place without explanation
* mixing preprocessing, training, and evaluation in one large block

---

## Research Reproducibility

When implementing experiments, include or preserve:

* seed setting
* config file
* dataset version or path
* preprocessing logic
* split logic
* model parameters
* metric definitions
* result saving
* logs
* plots or tables when appropriate

Experiment outputs should be saved in a clear directory such as:

* `outputs/`
* `results/`
* `checkpoints/`
* `figures/`
* `logs/`

Do not overwrite important results without making the behavior explicit.

---

## Data Handling

For medical or sensitive data:

* Never expose raw patient identifiers.
* Avoid storing PHI/PII in logs.
* Mask or remove names, registration numbers, phone numbers, addresses, and other identifiers.
* Prefer patient-level split when multiple records can belong to the same patient.
* Check for leakage between train, validation, and test sets.
* Explain assumptions about de-identification.

When reading datasets, print or log:

* number of rows
* number of columns
* column names
* missing values
* label distribution
* split distribution

---

## Modeling and Evaluation

For classification tasks, consider:

* AUROC
* AUPRC
* sensitivity
* specificity
* F1-score
* confusion matrix
* calibration
* subgroup performance

For regression tasks, consider:

* MAE
* RMSE
* R²
* residual plots
* confidence intervals when appropriate

For LLM or agent tasks, consider:

* task success rate
* exact match
* factual consistency
* hallucination rate
* human review agreement
* latency
* cost
* safety failure cases

Always explain why the selected metric fits the research goal.

---

## LLM Agent Projects

When modifying agent logic, document:

* agent role
* system prompt
* input schema
* output schema
* tools
* retrieval source
* validation step
* fallback behavior
* human review point
* logging behavior
* security limitations

Do not allow the agent to make final clinical, legal, financial, or administrative decisions without human review unless the project explicitly defines such authority.

---

## Testing and Verification

When possible, run the relevant checks before finishing.

Use the project’s existing commands if available, such as:

* `python -m pytest`
* `pytest`
* `ruff check .`
* `black --check .`
* `mypy .`
* `npm test`
* `npm run lint`
* `pnpm test`

If no tests exist, provide a minimal manual verification plan.

At the end of each task, report:

## 변경 사항

What changed.

## 검증 방법

What was run or how to test it.

## 남은 리스크

What still needs checking.

---

## Documentation

Update documentation when behavior changes.

Relevant files may include:

* `README.md`
* `docs/`
* `configs/`
* `examples/`
* `notebooks/`
* `CHANGELOG.md`

Documentation should explain:

* purpose
* setup
* input format
* execution command
* output format
* expected result
* limitations

---

## Output Standard

Every completed task should end with:

## 요약

A short summary of the work.

## 실행/검증

Commands run or recommended verification steps.

## 연구적 의미

How this affects the research, analysis, model, or workflow.

## 다음 작업

The next practical step.

