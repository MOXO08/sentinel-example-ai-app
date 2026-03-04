# EU AI Act Compliance Framework ⚖️

This page defines how Sentinel evaluates AI systems against the European Union AI Act (2026 Regulation).

## 📊 Risk Categories

| Category | Description | Requirement |
| :--- | :--- | :--- |
| **Minimal Risk** | Spam filters, simple games. | No specific obligations. |
| **Limited Risk** | Chatbots, AI-generated content. | Transparency (disclosure). |
| **High Risk** | Recruitment, Credit scoring, Healthcare. | **Full Audit Required (P0).** |
| **Unacceptable** | Social scoring, Real-time biometric surveillance. | **Prohibited in the EU.** |

## 🛡️ Mandatory High-Risk Flags (Art. 10-14)

Systems categorized as **High Risk** must declare and verify these 8 core flags:

1. `human_oversight_enabled`: Mechanism for natural persons to oversee the system.
2. `bias_assessment_performed`: Evaluation of training data for discriminatory patterns.
3. `transparency_disclosure_provided`: Clear info for users and stakeholders.
4. `data_governance_policy_documented`: Traceable and high-quality data handling.
5. `robustness_testing_completed`: Resistance to interference or adversarial attacks.
6. `cybersecurity_framework_implemented`: Protection against digital threats.
7. `risk_management_system_active`: Continuous assessment of potential harms.
8. `technical_documentation_available`: Detailed architecture and training logs.

## 🛑 Common Compliance Errors

### `INVALID_PAYLOAD`
* **Meaning**: The `manifest.json` file is malformed or uses an incorrect schema.
* **Fix**: Validate your JSON structure and ensure `app_name` and `version` are strings.

### `HUMAN_INTERVENTION_REQUIRED`
* **Meaning**: One or more mandatory flags for the declared Risk Category are missing.
* **Fix**: Ensure all 8 flags listed above are present in your `declared_flags` array.

---
[Back to Home](Home)
