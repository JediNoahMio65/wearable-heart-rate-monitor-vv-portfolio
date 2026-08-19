# Requirements Traceability Matrix

> **Simulation notice:** All requirements, test cases, links, statuses, and results in this document are fictional and created for educational portfolio purposes only.

## Document Purpose

This traceability matrix links simulated user needs to design inputs and planned verification test cases. It demonstrates how a device-development team can maintain evidence that each user need is addressed by one or more measurable requirements and that each requirement is verified.

## Traceability Status Definitions

| Status | Meaning |
|---|---|
| Planned | Verification test is defined but not yet executed in this simulated portfolio workflow |
| Pass | Simulated verification evidence meets the acceptance criterion |
| Fail | Simulated verification evidence does not meet the acceptance criterion |
| Deferred | Verification is planned for a future simulated phase |

## Traceability Matrix

| User Need ID | Design Input ID | Verification Test ID | Verification Activity | Expected Result | Simulated Status |
|---|---|---|---|---|---|
| UN-001 | DI-001 | VT-001 | Display-range functional test | Device displays estimated heart rate from 40 to 180 bpm when acceptable simulated PPG signal is available | Pass |
| UN-001 | DI-002 | VT-002 | Accuracy test using simulated reference inputs | At least 90% of valid test points from 50 to 150 bpm are within ±5 bpm of the simulated reference | Pass |
| UN-001 | DI-013 | VT-003 | Active-measurement sampling-rate configuration inspection | Simulated PPG acquisition configuration is at least 25 Hz | Pass |
| UN-002 | DI-003 | VT-004 | Heart-rate response-time test | Display updates within ±5 bpm of a stable simulated step change within 5 seconds | Pass |
| UN-003 | DI-004 | VT-005 | Low-signal-quality fault-condition test | Numerical value is suppressed and quality indication is displayed after 3 consecutive seconds of inadequate signal quality | Pass |
| UN-003 | DI-005 | VT-006 | Signal-quality recovery test | Numerical display resumes within 5 seconds after acceptable quality is restored for 3 consecutive seconds | Pass |
| UN-004 | DI-006 | VT-007 | Battery-life analysis | Simulated intermittent-use battery life is at least 16 hours | Pass |
| UN-005 | DI-007 | VT-008 | Low-battery indication test | Low-battery indicator is displayed at or below 15% simulated remaining capacity | Pass |
| UN-006 | DI-008 | VT-009 | Wristband retention test | Wristband remains secured during a 30-minute low-motion wear simulation | Pass |
| UN-006 | DI-015 | VT-010 | Visual inspection | No sharp exposed edges or visibly damaged surfaces are present before or after simulated verification testing | Pass |
| UN-007 | DI-009 | VT-011 | Display and control inspection | Display presents estimated value, `bpm`, battery status, and quality status using readable indicators | Pass |
| UN-007 | DI-010 | VT-012 | User-instructions inspection | Instructions include intended use, limitations, charging, proper wear, quality-indicator meaning, and wellness disclaimer | Pass |
| UN-008 | DI-004 | VT-005 | Low-signal-quality fault-condition test | Numerical value is suppressed and quality indication is displayed after 3 consecutive seconds of inadequate signal quality | Pass |
| UN-008 | DI-012 | VT-013 | Stale-value fault-condition test | Device does not display an estimate older than 10 seconds during unacceptable signal quality | Pass |
| UN-009 | DI-010 | VT-012 | User-instructions inspection | Required intended-use, limitation, charging, proper-wear, quality, and disclaimer content is present | Pass |
| UN-010 | DI-014 | VT-014 | Inadequate-contact detection test | Device identifies inadequate simulated sensor contact after low PPG amplitude persists for 3 consecutive seconds | Pass |
| UN-010 | DI-004 | VT-005 | Low-signal-quality fault-condition test | Numerical display is suppressed and quality indication is presented during persistent inadequate signal quality | Pass |
| UN-010 | DI-005 | VT-006 | Signal-quality recovery test | Numerical display resumes only after acceptable signal quality is restored for the defined persistence period | Pass |

## Risk-Control Traceability

The following design inputs provide simulated controls for the higher-priority risks identified in `03_risk_analysis_fmea.md`.

| FMEA ID | Risk Control | Related Design Input(s) | Verification Test ID(s) | Simulated Status |
|---|---|---|---|---|
| FMEA-001 | Suppress numerical output during inadequate signal quality | DI-004, DI-005, DI-012, DI-014 | VT-005, VT-006, VT-013, VT-014 | Pass |
| FMEA-002 | Prevent stale heart-rate display after signal loss | DI-004, DI-012 | VT-005, VT-013 | Pass |
| FMEA-003 | Confirm estimated-value accuracy within simulated acceptance criterion | DI-002, DI-009, DI-010 | VT-002, VT-011, VT-012 | Pass |
| FMEA-004 | Confirm response to stable heart-rate changes | DI-003 | VT-004 | Pass |
| FMEA-005 | Indicate low-battery condition | DI-007 | VT-008 | Pass |
| FMEA-006 | Confirm simulated battery endurance and charging behavior | DI-006, DI-011 | VT-007, VT-015 | Pass |
| FMEA-007 | Confirm retention and enclosure inspection criteria | DI-008, DI-015 | VT-009, VT-010 | Pass |
| FMEA-008 | Provide clear user instructions and visual status indicators | DI-009, DI-010 | VT-011, VT-012 | Pass |
| FMEA-009 | Prevent numerical heart-rate display while charging | DI-011 | VT-015 | Pass |
| FMEA-010 | Confirm no sharp or damaged exposed surfaces | DI-015 | VT-010 | Pass |

## Verification Coverage Summary

| Item Type | Quantity |
|---|---:|
| User needs | 10 |
| Design inputs | 15 |
| Verification test cases | 15 |
| Higher-priority FMEA items with linked controls | 10 |

## Notes

- The `Pass` statuses in this traceability matrix are simulated placeholders. Supporting simulated test procedures and results will be documented in `05_verification_test_protocol.md` and `06_verification_test_report.md`.
- A real project would use controlled document versions, formal review/approval, test records, and objective evidence.
- This document demonstrates traceability structure only and does not establish regulatory compliance.
