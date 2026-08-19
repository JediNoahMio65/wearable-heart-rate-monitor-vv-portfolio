Define simulated measurable design inputs
# Design Inputs

> **Simulation notice:** All device descriptions, requirements, acceptance criteria, and references in this document are fictional and created for educational portfolio purposes only.

## Document Purpose

This document converts simulated user needs into measurable design inputs for the wearable heart-rate monitor. Each design input is written to support objective verification through inspection, analysis, or simulated testing.

## Design Input Requirements

| ID | Related User Need(s) | Design Input Requirement | Verification Method |
|---|---|---|---|
| DI-001 | UN-001 | During stationary, low-motion simulated testing, the device shall display an estimated heart-rate value from 40 to 180 beats per minute (bpm) when an acceptable PPG signal is available. | Functional test |
| DI-002 | UN-001, UN-008 | When compared with a simulated reference heart-rate input from 50 to 150 bpm, the displayed estimate shall be within ±5 bpm for at least 90% of valid test points. | Accuracy test |
| DI-003 | UN-002 | Following a simulated stable step change in reference heart rate, the display shall update to within ±5 bpm of the new reference value within 5 seconds. | Response-time test |
| DI-004 | UN-003, UN-008, UN-010 | When the simulated PPG signal-quality index is below the defined acceptance threshold for 3 consecutive seconds, the device shall suppress the numerical heart-rate display and present a measurement-quality indication within 2 seconds. | Fault-condition test |
| DI-005 | UN-003, UN-010 | When acceptable simulated PPG signal quality is restored for 3 consecutive seconds, the device shall resume numerical heart-rate display within 5 seconds. | Recovery test |
| DI-006 | UN-004 | Under a simulated intermittent wellness-use profile, the device shall operate for at least 16 hours between full charges. | Battery-life analysis |
| DI-007 | UN-005 | When simulated remaining battery capacity is at or below 15%, the device shall display a low-battery indication. | Functional test |
| DI-008 | UN-006 | The simulated wristband retention feature shall remain secured during a 30-minute low-motion wear simulation without unintentional release. | Retention test |
| DI-009 | UN-007, UN-009 | The display shall present heart-rate value, unit label `bpm`, battery status, and measurement-quality status using user-readable visual indicators. | Inspection |
| DI-010 | UN-007 | The simulated user instructions shall include intended use, excluded uses, charging instructions, proper wear instructions, measurement-quality indication meaning, and a general-wellness disclaimer. | Documentation inspection |
| DI-011 | UN-009 | The simulated charging interface shall prevent numerical heart-rate display while charging and shall show a charging-status indication. | Functional test |
| DI-012 | UN-008 | The device shall not retain and display a heart-rate estimate older than 10 seconds when current signal quality is unacceptable. | Fault-condition test |
| DI-013 | UN-001, UN-002 | The device shall sample or receive simulated PPG data at a nominal rate of at least 25 Hz during active measurement mode. | Software configuration inspection |
| DI-014 | UN-003, UN-010 | The device shall identify inadequate sensor contact when the simulated PPG amplitude remains below the defined minimum signal threshold for 3 consecutive seconds. | Fault-condition test |
| DI-015 | UN-006 | The simulated device enclosure shall have no sharp exposed edges or visibly damaged surfaces during visual inspection before and after simulated verification testing. | Visual inspection |

## Acceptance-Criteria Rationale

- The 40–180 bpm display range reflects the limited simulated wellness-use scope.
- Accuracy, response-time, signal-quality, and stale-data requirements are prioritized because they address the risk of presenting a misleading numerical value.
- Battery, charging, retention, display, and instructional requirements support reliable and understandable intended use.
- This project uses simulated requirements and simulated evidence only. The values are portfolio assumptions, not clinical or regulatory claims.

## Traceability

Each design input will be linked to one or more verification test cases in `04_traceability_matrix.md`. Test procedures and simulated results will be documented in `05_verification_test_protocol.md` and `06_verification_test_report.md`.

## Limitations

These design inputs are not derived from a real product specification, clinical study, risk-benefit analysis, standards assessment, or regulatory submission. They are examples of measurable engineering requirements for educational portfolio use.
