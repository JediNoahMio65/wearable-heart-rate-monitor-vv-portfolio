# Portfolio Summary: Simulated Wearable Heart-Rate Monitor V&V

## Project Overview

This repository demonstrates a simulated medical-device verification and validation documentation workflow for a wearable heart-rate monitor intended for stationary, low-motion adult wellness use.

All device details, records, requirements, test data, results, and outcomes are fictional and created for educational portfolio purposes.

## Engineering Contribution

Created a connected documentation set that demonstrates:

- Intended-use definition and user-needs development
- Translation of user needs into measurable design inputs
- Simplified FMEA risk analysis with risk controls
- Requirements-to-test traceability
- Verification protocol development with acceptance criteria
- Simulated verification execution and deviation documentation
- Engineering change control through a mock ECO
- CAPA root-cause analysis, corrective/preventive action, and effectiveness review

## Verification Scenario

The simulated verification plan included 15 test cases.

One initial failure occurred during a response-time test: a 70 bpm to 110 bpm step change required 5.8 seconds, exceeding the five-second criterion.

The simulated root cause was an eight-second smoothing window that prioritized display stability without a documented assessment of its effect on response time. A mock ECO reduced the smoothing window to five seconds. Re-verification showed response times of 3.9 seconds and 3.7 seconds for two simulated step changes, and related signal-quality regression checks passed.

## Skills Demonstrated

- Medical-device design-control concepts
- Requirements engineering
- Verification planning and objective acceptance criteria
- Risk analysis and simplified FMEA
- Requirements traceability
- Test documentation and deviation handling
- Engineering change control
- CAPA and root-cause analysis
- Technical writing and version-controlled documentation

## Limitations

This project is a simulated educational portfolio exercise. It does not represent a manufactured device, clinical validation, regulatory submission, FDA clearance, ISO certification, or compliance evidence.
