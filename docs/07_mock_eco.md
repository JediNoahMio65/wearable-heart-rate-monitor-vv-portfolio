# Mock Engineering Change Order

> **Simulation notice:** This engineering change order, including all product configurations, failure references, change descriptions, approvals, impact assessments, and results, is fictional and created for educational portfolio purposes only.

## Change Identification

| Field | Simulated Record |
|---|---|
| ECO ID | ECO-SIM-001 |
| Title | Heart-Rate Response-Time Processing Update |
| Change type | Simulated firmware design change |
| Initiation trigger | DEV-001 from VT-004 response-time verification failure |
| Affected device | WHRM-SIM-001 wearable heart-rate monitor |
| Affected firmware | FW-SIM-0.2 to FW-SIM-0.3 |
| Initiated by | Simulated test engineer |
| Date initiated | Simulated |
| Change status | Implemented and re-verified in simulated portfolio scenario |

## Problem Statement

During simulated verification test VT-004, the device failed the response-time acceptance criterion for a stable simulated heart-rate step change from 70 bpm to 110 bpm.

The display required 5.8 seconds to reach within ±5 bpm of the new simulated reference value. The design input DI-003 requires the display to reach within ±5 bpm of a stable simulated step change within 5 seconds.

The 110 bpm to 80 bpm step change passed at 4.2 seconds. The initial 70 bpm to 110 bpm failure was treated as a simulated verification deviation requiring investigation and corrective design action.

## Proposed Change

The simulated firmware update from FW-SIM-0.2 to FW-SIM-0.3 includes the following changes:

1. Reduce the simulated heart-rate smoothing window from 8 seconds to 5 seconds during stable acceptable-signal-quality conditions.
2. Preserve the existing three-second persistence requirement for inadequate signal-quality detection.
3. Preserve numerical-display suppression when signal quality is inadequate.
4. Add a simulated internal response-time monitoring flag for design-verification logging.
5. Update the simulated firmware configuration record to identify FW-SIM-0.3 as the corrected version.

## Change Rationale

The simulated investigation concluded that the 8-second smoothing window contributed to delayed display response after an upward stable reference step change. Reducing the smoothing window was selected as the simulated corrective action because it addresses response time without removing signal-quality protections.

## Affected Items

| Item Type | Affected Item | Required Simulated Update |
|---|---|---|
| Firmware | FW-SIM-0.2 | Replace with FW-SIM-0.3 configuration |
| Design input | DI-003 | No requirement change; retain 5-second response-time criterion |
| Risk analysis | FMEA-004 | Review occurrence and detectability assumptions after design change |
| Verification protocol | VT-004 | Re-execute existing protocol with corrected simulated firmware |
| Verification report | DEV-001 / RT-004 | Record initial failure and successful re-test |
| Traceability matrix | DI-003 to VT-004 | Update status to final pass after re-verification |
| CAPA record | CAPA-SIM-001 | Link to root-cause analysis and effectiveness check |

## Impact Assessment

### Intended Use

The simulated change does not alter the intended wellness-only use, intended users, use environment, or excluded uses.

### User Needs

The change supports UN-002 by improving update time after a stable heart-rate change. It does not alter the original user-need statements.

### Design Inputs

DI-003 remains unchanged. The change modifies the simulated design implementation intended to meet the existing requirement.

### Risk Assessment

The change is associated with FMEA-004: delayed display response after stable heart-rate change.

Potential new risk consideration: reducing smoothing could increase sensitivity to short-duration signal variation. This simulated concern is mitigated by retaining the existing signal-quality persistence logic, numerical-display suppression during inadequate signal quality, and post-change re-verification of response-time and signal-quality behavior.

### Verification Requirements

The following simulated verification activities are required after implementation:

| Verification Activity | Purpose | Acceptance Criterion |
|---|---|---|
| RT-004: Repeat response-time test | Confirm correction of DEV-001 | Both stable step changes reach within ±5 bpm of the new reference within 5 seconds |
| Regression check of VT-005 | Confirm signal-quality suppression behavior remains effective | Numerical display suppresses and quality indication appears within protocol-defined timing |
| Regression check of VT-006 | Confirm signal-quality recovery behavior remains effective | Numerical display resumes within protocol-defined timing after quality recovery |
| Regression check of VT-013 | Confirm stale-value timeout remains effective | Outdated numerical value is not displayed during persistent inadequate quality |

## Simulated Implementation Plan

1. Document and approve ECO-SIM-001 in the simulated portfolio workflow.
2. Update the simulated firmware configuration from FW-SIM-0.2 to FW-SIM-0.3.
3. Execute RT-004 and listed regression checks.
4. Update the verification report with final results.
5. Complete CAPA effectiveness review.
6. Update traceability status to final pass when all required simulated checks pass.

## Simulated Re-Verification Results

| Test ID | Simulated Result | Status |
|---|---|---|
| RT-004 | 70→110 bpm step reached within ±5 bpm in 3.9 seconds; 110→80 bpm step reached within ±5 bpm in 3.7 seconds | Pass |
| VT-005 regression | Numerical display suppressed 1.5 seconds after quality-fault persistence period | Pass |
| VT-006 regression | Numerical display resumed 3.8 seconds after acceptable-quality persistence period | Pass |
| VT-013 regression | Numerical estimate removed before it became 10 seconds old during persistent inadequate quality | Pass |

## Simulated Approval Record

| Role | Simulated Disposition | Date |
|---|---|---|
| Design engineering reviewer | Approved | Simulated |
| Verification reviewer | Approved after re-verification | Simulated |
| Quality reviewer | Approved after CAPA effectiveness review | Simulated |

## Closure Statement

ECO-SIM-001 is considered closed within this educational portfolio scenario because the simulated response-time failure was corrected, required simulated re-verification passed, and no adverse impact was identified in the defined regression checks.

This closure statement is not evidence of real product change control, regulatory approval, clinical performance, or device release.
