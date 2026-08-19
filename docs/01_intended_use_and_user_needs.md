Define simulated intended use and user needs
# Intended Use and User Needs

> **Simulation notice:** All device descriptions, requirements, and user needs in this document are fictional and created for educational portfolio purposes only.

## Document Purpose

This document defines the intended use, intended users, use environment, and high-level user needs for a simulated wearable heart-rate monitor. These user needs will be translated into measurable design inputs and linked to verification activities in later documents.

## Simulated Device Description

The simulated device is a wrist-worn optical heart-rate monitor that uses a photoplethysmography (PPG) sensor and embedded processing to estimate and display heart rate.

The simulated system includes:

- A wrist-worn sensor enclosure
- Optical PPG sensing elements
- Embedded signal-processing logic
- A user-facing heart-rate display
- A rechargeable battery
- A charging interface

## Intended Use

The simulated wearable heart-rate monitor is intended to display an adult user's estimated heart rate during stationary, low-motion wellness use.

The device is intended to provide a convenient, noninvasive display of estimated heart rate for general wellness awareness only.

## Intended Users

- Adults aged 18 years and older
- Individuals using the device for general wellness awareness
- Users able to read the device display and follow basic charging and wear instructions

## Intended Use Environment

- Indoor or outdoor general-wellness settings
- Stationary or low-motion activities
- Ambient temperature from 10 °C to 35 °C
- Non-clinical environments

## Excluded Uses

The simulated device is not intended for:

- Diagnosis, treatment, mitigation, or prevention of disease
- Emergency monitoring or alarm generation
- Arrhythmia detection
- Clinical decision-making
- Pediatric use
- High-motion exercise measurement
- Use during swimming, bathing, or submersion
- Use as a replacement for professional medical assessment

## User Needs

| ID | User Need |
|---|---|
| UN-001 | The user needs to view an estimated heart-rate value that is easy to read during stationary, low-motion wellness use. |
| UN-002 | The user needs the displayed heart-rate value to update within a reasonable time after their heart rate changes. |
| UN-003 | The user needs the device to provide a clear indication when measurement quality is insufficient to provide a reliable estimate. |
| UN-004 | The user needs the device to operate for a typical day of intermittent wellness use without requiring recharge. |
| UN-005 | The user needs to be able to determine when the device requires charging. |
| UN-006 | The user needs the device to be comfortable and remain secured on the wrist during intended low-motion use. |
| UN-007 | The user needs the device display and basic controls to be understandable without specialized training. |
| UN-008 | The user needs the device to avoid presenting a misleading normal-looking heart-rate value when a usable signal is unavailable. |
| UN-009 | The user needs basic instructions describing intended use, limitations, charging, and proper wear. |
| UN-010 | The user needs the device to safely stop heart-rate display or provide a quality-status indication when sensor contact is inadequate. |

## Traceability

Each user need will be assigned measurable design inputs in `02_design_inputs.md`. Design inputs will later be linked to verification tests through the traceability matrix.

## Limitations

This document models early design-control reasoning only. It is not a clinical use specification, a regulatory document, or evidence of device safety, effectiveness, or compliance.
