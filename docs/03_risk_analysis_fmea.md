# Risk Analysis and Simplified FMEA

> **Simulation notice:** All device descriptions, risk estimates, failure modes, mitigations, and conclusions in this document are fictional and created for educational portfolio purposes only.

## Document Purpose

This document demonstrates a simplified Failure Modes and Effects Analysis (FMEA) for a simulated wearable heart-rate monitor. It identifies foreseeable failure modes associated with the device’s intended wellness use, estimates initial and residual risk, and identifies simulated risk controls.

This is an educational example only. It is not a complete risk-management file and does not claim conformance with ISO 14971 or any other standard.

## Risk Scoring Method

### Severity (S)

| Score | Description |
|---:|---|
| 1 | Negligible inconvenience; no expected harm |
| 2 | Temporary inconvenience or minor user confusion |
| 3 | Potential for incorrect wellness interpretation or delayed non-urgent follow-up |
| 4 | Potential for significant incorrect reliance or delayed medical attention |
| 5 | Potential for serious injury or life-threatening harm |

### Occurrence (O)

| Score | Description |
|---:|---|
| 1 | Remote |
| 2 | Uncommon |
| 3 | Occasional |
| 4 | Probable |
| 5 | Frequent |

### Detectability (D)

| Score | Description |
|---:|---|
| 1 | Failure is highly likely to be detected before affecting the user |
| 2 | Failure is likely to be detected |
| 3 | Failure may be detected |
| 4 | Failure is unlikely to be detected |
| 5 | Failure is difficult to detect before affecting the user |

### Risk Priority Number

\[
RPN = S \times O \times D
\]

For this simulated exercise:

| RPN range | Simulated action |
|---:|---|
| 1–15 | Accept with documented rationale |
| 16–30 | Review and implement risk controls where practical |
| 31–125 | Risk control required before simulated release |

## Simplified FMEA

| ID | Failure Mode | Potential Effect | Potential Cause | Initial S | Initial O | Initial D | Initial RPN | Simulated Risk Controls | Residual S | Residual O | Residual D | Residual RPN | Related Design Input(s) |
|---|---|---|---|---:|---:|---:|---:|---|---:|---:|---:|---:|---|
| FMEA-001 | Numerical heart-rate value shown when PPG signal quality is inadequate | User may rely on a misleading heart-rate estimate | Poor sensor contact, motion artifact, ambient-light interference, algorithm does not suppress output | 4 | 3 | 4 | 48 | Signal-quality threshold, 3-second persistence rule, suppress numerical display, show quality indicator | 4 | 2 | 2 | 16 | DI-004, DI-005, DI-012, DI-014 |
| FMEA-002 | Heart-rate estimate remains displayed after signal loss | User may interpret stale data as current | Software does not time out a previous estimate | 4 | 3 | 4 | 48 | Stale-value timeout of 10 seconds, quality-status indication, fault-condition test | 4 | 1 | 2 | 8 | DI-004, DI-012 |
| FMEA-003 | Displayed estimate exceeds simulated accuracy criterion | User may make an incorrect wellness interpretation | Sensor variability, signal-processing error, improper wear, algorithm limitations | 3 | 3 | 3 | 27 | Simulated accuracy verification, stated use limitations, quality indication, excluded-use instructions | 3 | 2 | 2 | 12 | DI-002, DI-009, DI-010 |
| FMEA-004 | Device fails to update after a stable change in simulated heart rate | User sees outdated information | Processing delay, software-state error, delayed display refresh | 3 | 2 | 3
