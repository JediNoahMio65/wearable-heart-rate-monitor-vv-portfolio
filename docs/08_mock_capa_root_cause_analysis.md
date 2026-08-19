# Mock CAPA and Root-Cause Analysis

> **Simulation notice:** This CAPA record, including all problem descriptions, investigation methods, conclusions, actions, timelines, effectiveness checks, and closure decisions, is fictional and created for educational portfolio purposes only.

## CAPA Identification

| Field | Simulated Record |
|---|---|
| CAPA ID | CAPA-SIM-001 |
| Title | Corrective Action for Heart-Rate Response-Time Verification Failure |
| Source | DEV-001 identified during VT-004 verification testing |
| Related ECO | ECO-SIM-001 |
| Related design input | DI-003 |
| Related risk item | FMEA-004 |
| Affected configuration | WHRM-SIM-001, FW-SIM-0.2 |
| CAPA owner | Simulated design-quality engineer |
| Date opened | Simulated |
| Date closed | Simulated |
| Status | Closed after simulated effectiveness verification |

## Problem Statement

During simulated verification test VT-004, the wearable heart-rate monitor did not meet the response-time requirement defined by DI-003.

For a stable simulated reference step change from 70 bpm to 110 bpm, the device display required 5.8 seconds to reach within ±5 bpm of the new reference value. The acceptance criterion requires response within 5 seconds.

The 110 bpm to 80 bpm step change completed in 4.2 seconds. Although only one direction failed, the response-time requirement was not fully met and was treated as a simulated nonconformance.

## Initial Risk Assessment

| Factor | Assessment |
|---|---|
| Potential effect | User may view outdated estimated heart-rate information after a stable change. |
| Intended-use impact | Affects timely wellness display but does not alter the device’s wellness-only intended use. |
| Associated FMEA item | FMEA-004: delayed display response after stable heart-rate change |
| Initial risk priority | Moderate simulated risk requiring investigation and corrective action |
| Immediate containment | FW-SIM-0.2 was not considered acceptable for simulated release until the response-time issue was resolved. |

## Investigation Scope

The simulated investigation reviewed:

- VT-004 response-time test record
- Simulated firmware configuration for FW-SIM-0.2
- Simulated smoothing-window settings
- Signal-quality suppression and recovery logic
- Existing design input DI-003
- Related FMEA-004 risk-control assumptions

## Root-Cause Analysis Method

### Simulated Five Whys

| Question | Answer |
|---|---|
| Why did the display exceed the five-second response-time criterion? | The displayed estimate remained influenced by prior signal history after the 70 bpm to 110 bpm step change. |
| Why did prior signal history continue to influence the display? | The simulated smoothing window averaged an eight-second signal history. |
| Why was the smoothing window set to eight seconds? | The initial simulated design prioritized display stability and reduction of short-term value variation. |
| Why was response-time performance not identified earlier? | The initial simulated design review did not include an explicit quantitative tradeoff assessment between smoothing duration and the five-second response-time requirement. |
| Why was the tradeoff assessment missing? | The simulated firmware design review checklist did not include a specific item requiring confirmation that signal-processing parameter choices satisfied all time-based display requirements. |

## Root Cause Statement

The simulated root cause was an eight-second smoothing-window configuration selected to improve displayed-value stability without a documented quantitative assessment of its impact on DI-003 response-time performance.

A contributing simulated process cause was the absence of a firmware design-review checklist item requiring explicit assessment of signal-processing parameters against time-based design inputs.

## Corrective and Preventive Action Plan

| Action ID | Action Type | Action Description | Owner | Due Date | Status |
|---|---|---|---|---|---|
| CA-001 | Correction | Update simulated firmware from FW-SIM-0.2 to FW-SIM-0.3 and reduce smoothing window from eight seconds to five seconds during stable acceptable-signal-quality conditions. | Simulated firmware engineer | Simulated | Complete |
| CA-002 | Corrective action | Re-execute VT-004 response-time verification using corrected firmware configuration. | Simulated verification engineer | Simulated | Complete |
| CA-003 | Corrective action | Perform regression checks for signal-quality suppression, signal-quality recovery, and stale-value timeout. | Simulated verification engineer | Simulated | Complete |
| PA-001 | Preventive action | Update the simulated firmware design-review checklist to require documented assessment of filtering/smoothing parameters against time-based requirements. | Simulated design-quality engineer | Simulated | Complete |
| PA-002 | Preventive action | Add simulated response-time test consideration to future changes affecting display smoothing, filtering, or update logic. | Simulated design-quality engineer | Simulated | Complete |

## Implementation Evidence

| Action ID | Simulated Evidence |
|---|---|
| CA-001 | ECO-SIM-001 documents the updated simulated firmware configuration and smoothing-window change. |
| CA-002 | RT-004 in `06_verification_test_report.md` records 3.9-second and 3.7-second response times after the simulated change. |
| CA-003 | Regression results in ECO-SIM-001 show continued pass status for VT-005, VT-006, and VT-013. |
| PA-001 | Simulated design-review checklist revision identifies time-based design-input assessment as a required review item. |
| PA-002 | Simulated change-control checklist includes response-time impact assessment for future relevant firmware changes. |

## Effectiveness Check Plan

| Field | Simulated Effectiveness Criterion |
|---|---|
| Objective | Confirm that the corrective action resolves the response-time nonconformance without degrading related signal-quality protections. |
| Evaluation data | RT-004 and regression checks for VT-005, VT-006, and VT-013. |
| Pass criteria | Both response-time step changes meet the five-second criterion, and all related regression checks pass. |
| Recurrence definition | Any stable reference step change requiring more than five seconds to reach within ±5 bpm of the new reference value. |
| Adverse-impact criterion | Failure of signal-quality suppression, recovery, or stale-value timeout regression testing. |
| Action if not effective | Reopen CAPA-SIM-001, assess additional design changes, update risk analysis, and repeat relevant verification. |

## Effectiveness Check Results

| Verification Activity | Simulated Result | Status |
|---|---|---|
| RT-004: 70→110 bpm response | Reached within ±5 bpm of reference in 3.9 seconds. | Pass |
| RT-004: 110→80 bpm response | Reached within ±5 bpm of reference in 3.7 seconds. | Pass |
| VT-005 regression | Numerical display suppressed within protocol-defined timing after persistent inadequate signal quality. | Pass |
| VT-006 regression | Numerical display resumed within protocol-defined timing after sustained acceptable signal quality. | Pass |
| VT-013 regression | Outdated numerical estimate was not displayed during persistent inadequate signal quality. | Pass |

## Risk Review

Following the simulated corrective action and successful re-verification:

- FMEA-004 remains applicable because delayed response is a foreseeable failure mode.
- The simulated occurrence rating may be reduced because the corrected smoothing window met response-time verification.
- Signal-quality risk controls remain unchanged and were confirmed by simulated regression checks.
- No simulated adverse effect on the defined wellness-use scope was identified.

## CAPA Closure Decision

CAPA-SIM-001 is closed within this educational portfolio scenario because:

1. The simulated root cause was identified.
2. Corrective and preventive actions were implemented.
3. The corrected simulated firmware configuration met the response-time acceptance criterion.
4. Related signal-quality controls passed simulated regression checks.
5. The traceability matrix and verification report were updated to show final pass status.

## Related Records

- Intended use and user needs: `01_intended_use_and_user_needs.md`
- Design inputs: `02_design_inputs.md`
- Risk analysis: `03_risk_analysis_fmea.md`
- Traceability matrix: `04_traceability_matrix.md`
- Verification protocol: `05_verification_test_protocol.md`
- Verification report: `06_verification_test_report.md`
- Mock ECO: `07_mock_eco.md`

## Limitations

This CAPA demonstrates a documentation structure and engineering-reasoning workflow only. It is not evidence of a real product investigation, quality-system implementation, regulatory compliance, software validation, or device release.
