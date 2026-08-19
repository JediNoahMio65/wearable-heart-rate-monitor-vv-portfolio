# Verification Test Protocol

> **Simulation notice:** All test articles, procedures, inputs, equipment, data, acceptance criteria, and results referenced in this document are fictional and created for educational portfolio purposes only.

## Document Purpose

This protocol defines simulated verification activities for the wearable heart-rate monitor design inputs. It establishes test objectives, methods, acceptance criteria, and pass/fail decision rules before simulated results are reviewed.

## Scope

This protocol applies to the simulated device concept and design inputs defined in `02_design_inputs.md`. It covers functional behavior, simulated accuracy, response time, signal-quality handling, battery behavior, retention, display, charging, and documentation inspection.

This protocol does not cover clinical validation, electrical safety, electromagnetic compatibility, cybersecurity, biocompatibility, software validation, usability validation, or human-subject testing.

## Simulated Test Article

| Item | Simulated Description |
|---|---|
| Test article | WHRM-SIM-001 wearable heart-rate monitor prototype |
| Firmware version | FW-SIM-0.2 |
| Display configuration | HR value, `bpm` unit, battery icon, quality-status indicator |
| Sensor input | Simulated PPG signal generator with configurable heart rate, amplitude, and signal-quality status |
| Test environment | Simulated indoor wellness-use environment at 22 °C ± 3 °C |
| Data record | Simulated verification data table maintained for this portfolio project |

## General Test Rules

- All acceptance criteria are defined before simulated test execution.
- Each test shall document the test input, observed output, pass/fail result, and any anomaly.
- A test passes only when all applicable acceptance criteria are met.
- Simulated deviations or failures shall be documented in the verification report.
- Re-testing after a simulated design change shall reference the applicable mock ECO and CAPA documents.

## Test Case Summary

| Test ID | Title | Related Design Input(s) | Verification Method |
|---|---|---|---|
| VT-001 | Heart-Rate Display Range Test | DI-001 | Functional test |
| VT-002 | Simulated Heart-Rate Accuracy Test | DI-002 | Accuracy test |
| VT-003 | PPG Sampling-Rate Configuration Inspection | DI-013 | Configuration inspection |
| VT-004 | Heart-Rate Response-Time Test | DI-003 | Response-time test |
| VT-005 | Inadequate Signal-Quality Suppression Test | DI-004 | Fault-condition test |
| VT-006 | Signal-Quality Recovery Test | DI-005 | Recovery test |
| VT-007 | Simulated Battery-Life Analysis | DI-006 | Battery-life analysis |
| VT-008 | Low-Battery Indicator Test | DI-007 | Functional test |
| VT-009 | Wristband Retention Test | DI-008 | Retention test |
| VT-010 | Enclosure Visual Inspection | DI-015 | Visual inspection |
| VT-011 | Display Status Indicator Inspection | DI-009 | Inspection |
| VT-012 | User-Instructions Content Inspection | DI-010 | Documentation inspection |
| VT-013 | Stale Heart-Rate Display Timeout Test | DI-012 | Fault-condition test |
| VT-014 | Inadequate Sensor-Contact Detection Test | DI-014 | Fault-condition test |
| VT-015 | Charging-State Interlock Test | DI-011 | Functional test |

---

## Detailed Test Procedures

### VT-001: Heart-Rate Display Range Test

**Objective:** Verify that the device displays an estimated heart-rate value from 40 to 180 bpm when acceptable simulated PPG signal quality is available.

**Preconditions:**

- WHRM-SIM-001 is powered on.
- Simulated remaining battery capacity is above 15%.
- Simulated PPG signal quality is acceptable.

**Procedure:**

1. Apply simulated reference heart-rate inputs of 40, 60, 100, 140, and 180 bpm.
2. Allow the display to stabilize for 5 seconds at each input.
3. Record the displayed heart-rate value and quality-status indication.
4. Confirm that the numerical display remains available at each valid input.

**Acceptance Criteria:**

- A numerical estimated heart-rate value is displayed for each valid simulated input from 40 to 180 bpm.
- No inadequate-signal-quality indication is shown during acceptable simulated PPG input.

---

### VT-002: Simulated Heart-Rate Accuracy Test

**Objective:** Verify that the displayed estimate meets the simulated accuracy requirement.

**Preconditions:**

- WHRM-SIM-001 is powered on.
- Simulated PPG signal quality is acceptable.
- Device is not charging.

**Procedure:**

1. Apply ten simulated reference heart-rate inputs between 50 and 150 bpm.
2. Allow the display to stabilize for 5 seconds at each input.
3. Record the simulated reference value and displayed value.
4. Calculate absolute error for each test point.

**Acceptance Criteria:**

- At least 9 of 10 valid test points have absolute error of 5 bpm or less.

---

### VT-003: PPG Sampling-Rate Configuration Inspection

**Objective:** Verify that the simulated PPG input configuration meets the minimum nominal sampling-rate requirement.

**Procedure:**

1. Review the simulated firmware configuration record for active measurement mode.
2. Record the configured nominal PPG input rate.

**Acceptance Criteria:**

- Configured nominal PPG input rate is at least 25 Hz.

---

### VT-004: Heart-Rate Response-Time Test

**Objective:** Verify display response following a stable simulated reference heart-rate step change.

**Preconditions:**

- WHRM-SIM-001 is powered on and displaying a valid heart-rate estimate.
- Simulated PPG signal quality is acceptable.

**Procedure:**

1. Stabilize the simulated reference input at 70 bpm for at least 10 seconds.
2. Apply a stable step change from 70 bpm to 110 bpm.
3. Measure the elapsed time until the displayed estimate is within ±5 bpm of 110 bpm.
4. Repeat for a stable step change from 110 bpm to 80 bpm.

**Acceptance Criteria:**

- For each step change, the displayed value is within ±5 bpm of the new reference within 5 seconds.

---

### VT-005: Inadequate Signal-Quality Suppression Test

**Objective:** Verify that the device suppresses numerical display and provides a quality indication during persistent inadequate simulated signal quality.

**Procedure:**

1. Establish a valid 80 bpm simulated input with acceptable signal quality.
2. Change the simulated PPG signal-quality index to below the defined acceptance threshold.
3. Maintain inadequate simulated quality for 3 consecutive seconds.
4. Record display state and quality-status indication.
5. Measure elapsed time from the end of the 3-second persistence period to numerical-display suppression.

**Acceptance Criteria:**

- Numerical heart-rate display is suppressed.
- Measurement-quality indication is displayed.
- Suppression occurs within 2 seconds after the 3-second inadequate-quality persistence period.

---

### VT-006: Signal-Quality Recovery Test

**Objective:** Verify that numerical display resumes after sustained recovery of acceptable simulated signal quality.

**Procedure:**

1. Begin with numerical display suppressed because of inadequate simulated signal quality.
2. Restore acceptable simulated signal quality.
3. Maintain acceptable simulated quality for 3 consecutive seconds.
4. Measure elapsed time until numerical heart-rate display resumes.

**Acceptance Criteria:**

- Numerical display resumes within 5 seconds after the 3-second acceptable-quality persistence period.
- A current simulated heart-rate value is displayed with no inadequate-quality indication.

---

### VT-007: Simulated Battery-Life Analysis

**Objective:** Verify that the simulated device meets the intermittent-use battery-life requirement.

**Procedure:**

1. Review the simulated power-budget worksheet for the defined intermittent wellness-use profile.
2. Confirm that the profile includes active measurement, display update, standby, and charging-loss assumptions.
3. Record the calculated operating duration between full charge and low-battery threshold.

**Acceptance Criteria:**

- Calculated simulated operating duration is at least 16 hours.

---

### VT-008: Low-Battery Indicator Test

**Objective:** Verify low-battery indication at or below the defined remaining-capacity threshold.

**Procedure:**

1. Set simulated remaining battery capacity to 16%.
2. Confirm that the low-battery indicator is not displayed.
3. Set simulated remaining battery capacity to 15%.
4. Confirm display state.
5. Repeat at 10% simulated remaining capacity.

**Acceptance Criteria:**

- Low-battery indication is displayed at 15% and 10% remaining capacity.
- Low-battery indication is not displayed at 16% remaining capacity.

---

### VT-009: Wristband Retention Test

**Objective:** Verify simulated wristband retention during intended low-motion use.

**Procedure:**

1. Secure the simulated wristband retention feature using the documented normal-wear configuration.
2. Perform a 30-minute low-motion wear simulation.
3. Inspect the retention feature at the conclusion of the simulation.

**Acceptance Criteria:**

- No unintentional release occurs during the 30-minute low-motion wear simulation.
- Retention feature remains intact and functional after simulation.

---

### VT-010: Enclosure Visual Inspection

**Objective:** Verify that the simulated enclosure meets visual-inspection criteria.

**Procedure:**

1. Inspect simulated enclosure surfaces before verification testing.
2. Inspect simulated enclosure surfaces after verification testing.
3. Record any sharp exposed edges, cracks, visibly damaged surfaces, or loose external components.

**Acceptance Criteria:**

- No sharp exposed edges are observed.
- No visibly damaged external surfaces or loose external components are observed.

---

### VT-011: Display Status Indicator Inspection

**Objective:** Verify required user-readable display information.

**Procedure:**

1. Apply an acceptable simulated PPG input.
2. Inspect the active display.
3. Inspect the display at low-battery condition.
4. Inspect the display during inadequate simulated signal quality.

**Acceptance Criteria:**

- Active display includes a heart-rate value and `bpm` unit label.
- Battery status is visible.
- Measurement-quality status is visible or clearly indicated.
- Inadequate signal quality is distinguishable from normal measurement state.

---

### VT-012: User-Instructions Content Inspection

**Objective:** Verify that simulated instructions contain required intended-use and safety-limitation information.

**Procedure:**

1. Review the simulated user-instructions document.
2. Confirm presence of required content.

**Acceptance Criteria:**

The instructions include:

- Intended use
- Excluded uses
- Charging instructions
- Proper wear instructions
- Meaning of measurement-quality indication
- General-wellness disclaimer

---

### VT-013: Stale Heart-Rate Display Timeout Test

**Objective:** Verify that an outdated numerical heart-rate estimate is not displayed during ongoing inadequate signal quality.

**Procedure:**

1. Establish a valid simulated 80 bpm display.
2. Introduce inadequate simulated signal quality.
3. Maintain inadequate signal quality for more than 10 seconds.
4. Record display behavior throughout the interval.

**Acceptance Criteria:**

- A numerical heart-rate estimate older than 10 seconds is not displayed while current simulated signal quality remains unacceptable.
- Measurement-quality indication is displayed.

---

### VT-014: Inadequate Sensor-Contact Detection Test

**Objective:** Verify detection of inadequate simulated sensor contact.

**Procedure:**

1. Establish a valid simulated PPG input.
2. Set simulated PPG amplitude below the defined minimum threshold.
3. Maintain low amplitude for 3 consecutive seconds.
4. Observe measurement-quality and display behavior.

**Acceptance Criteria:**

- Device identifies inadequate sensor contact or inadequate signal quality.
- Numerical heart-rate display is suppressed according to DI-004.

---

### VT-015: Charging-State Interlock Test

**Objective:** Verify that numerical heart-rate display is disabled while charging.

**Procedure:**

1. Connect the simulated charging interface.
2. Observe charging-status indication.
3. Apply an otherwise valid simulated PPG input.
4. Observe numerical-display behavior.
5. Disconnect the simulated charging interface and return to active measurement mode.

**Acceptance Criteria:**

- Charging-status indication is displayed while charging.
- Numerical heart-rate display is not presented while charging.
- Device returns to normal measurement behavior after charging is disconnected.

## Deviations and Unexpected Results

Any simulated deviation, unexpected observation, or failed acceptance criterion shall be recorded in the verification report. A simulated failure may trigger a mock ECO, root-cause analysis, CAPA, and re-verification activity.

## Traceability

Each test case is linked to the requirements traceability matrix in `04_traceability_matrix.md`. Simulated execution results will be documented in `06_verification_test_report.md`.

## Limitations

This protocol is a portfolio example only. It does not demonstrate test execution on an actual device and does not replace formal verification planning, statistically justified sampling, calibrated equipment, protocol approval, independent review, or objective regulatory evidence.
