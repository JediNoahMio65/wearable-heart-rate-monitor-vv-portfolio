# Wearable Heart-Rate Monitor: Simulated V&V Documentation Portfolio

A documentation-focused biomedical engineering portfolio project demonstrating a simulated verification and validation workflow for a wearable heart-rate monitor.

> **Simulation notice:** This repository is a fictional educational portfolio project. The device concept, requirements, test data, results, risks, failures, corrective actions, and documentation are simulated. This work does not describe a manufactured, clinically validated, FDA-cleared, or commercially available device.

## Purpose

Demonstrate an organized medical-device development workflow from intended use and user needs through design inputs, risk analysis, traceability, verification testing, engineering change control, and corrective and preventive action.

## Simulated Device Concept

The simulated device is a wrist-worn optical heart-rate monitor intended to display an adult user's estimated heart rate during stationary, low-motion wellness use.

The device is not intended for diagnosis, treatment, emergency monitoring, arrhythmia detection, pediatric use, high-motion exercise use, or clinical decision-making.

## Planned Documentation

- Intended use and user needs
- Measurable design inputs
- Risk analysis and simplified FMEA
- Requirements-to-test traceability matrix
- Verification test protocol
- Verification test report with simulated results
- Mock engineering change order (ECO)
- Mock CAPA and root-cause analysis

## Repository Structure

```text
docs/       Simulated design-control and quality documentation
data/       Simulated verification-test data
reports/    Simulated verification summaries and supporting artifacts
```
## Documentation Highlights

| Document | What It Demonstrates |
|---|---|
| Intended Use and User Needs | Defined wellness-only scope, intended users, excluded uses, and 10 user needs |
| Design Inputs | Created 15 measurable design inputs linked to verification methods |
| Simplified FMEA | Identified 10 failure modes, simulated risk controls, and residual-risk rationale |
| Traceability Matrix | Linked user needs → design inputs → verification tests → risk controls |
| Verification Protocol | Defined 15 verification test cases and pass/fail acceptance criteria |
| Verification Report | Recorded simulated results, including one response-time failure and successful re-test |
| Mock ECO | Documented firmware smoothing-window change and regression-test impact assessment |
| Mock CAPA | Documented root-cause analysis, corrective/preventive actions, and effectiveness check |

## Simulated Verification Summary

| Metric | Simulated Result |
|---|---|
| Design inputs | 15 |
| Verification tests | 15 |
| Initial verification passes | 14 |
| Initial verification failures | 1 |
| Re-test passes after corrective action | 1 |
| Open simulated verification failures | 0 |

The simulated response-time deviation was traced to an eight-second smoothing-window configuration. A mock engineering change reduced the window to five seconds, and the re-test met the five-second response-time acceptance criterion without simulated regression failures in related signal-quality controls.
## Scope and Limitations

- All content is simulated for educational and portfolio purposes.
- No hardware was built or tested.
- No human-subject data, patient data, or protected health information are used.
- No regulatory, clinical, safety, or performance claims are made.
- This project demonstrates documentation structure and engineering reasoning only.

## Disclaimer

This repository is not a medical device record, a Design History File, a regulatory submission, or evidence of compliance with FDA, ISO, IEC, or any other standard.
