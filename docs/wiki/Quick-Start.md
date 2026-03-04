# Quick Start Guide 🚀
**Running Sentinel v1.1.0 (Hardened Architecture)**

Get up and running with the most secure EU AI Act compliance engine in under a minute.

## 📦 Requirements
- Node.js 18.0.0 or higher.
- A valid `manifest.json` in your project root.
- A Sentinel License Token (for remote audits).

### 0. Get a Free License Token
To run remote audits and enable your compliance badge, you need a license token.
- **Get yours here (Free)**: <a href="https://radumuresanu.lemonsqueezy.com/checkout/buy/c3dd992f-74d8-4d6c-859e-92095a5f171c?embed=1" class="lemonsqueezy-button">Get Free License</a>
<script src="https://assets.lemonsqueezy.com/lemon.js" defer></script>

## 🛠️ Installation & First Run

You don't need to install anything globally. Use `npx` to fetch the latest hardened binary:

### 1. Initialize your project
This creates a template `manifest.json` if you don't have one.
```bash
npx @radu_api/sentinel-scan --init
```

### 2. Run a Local Diagnostic
Verify your compliance status offline. This uses the sub-3ms WASM engine.
```bash
npx @radu_api/sentinel-scan ./manifest.json
```

### 3. Run a Remote Audit (Recommended for CI/CD)
Remote audits generate a persistent report ID and allow for dynamic compliance badges.
```bash
npx @radu_api/sentinel-scan ./manifest.json --remote --api-key YOUR_DEVELOPER_KEY
```

## 🛡️ Understanding the Output
Sentinel v1.1.0 provides three possible verdicts:
- ✅ **COMPLIANT**: No violations found.
- ⚠️ **HUMAN_INTERVENTION_REQUIRED**: AI analysis required for edge cases.
- ❌ **NON_COMPLIANT**: Critical violations of Articles 5, 10, 13, 14, or 22.

---
[Back to Home](Home) | [Compliance Framework](Compliance-Framework)
