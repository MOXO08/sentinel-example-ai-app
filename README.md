# 🛡 Sentinel Example AI App
**Automated EU AI Act Compliance Checking**

[![Sentinel Status](https://sentinel-api.sentinel-moxo.workers.dev/api/v1/badge/sentinel-example-ai-app)](https://github.com/MOXO08/sentinel-example-ai-app/wiki/Compliance-Framework)

This repository demonstrates the integration of **Sentinel** into a CI/CD workflow for verifying compliance with **EU AI Act** regulations.

## What is Sentinel?
Sentinel is an offline AI compliance scanner that verifies your application's manifests and code against the EU AI Act safety standards. It ensures that your AI systems meet transparency, security, and human oversight requirements before deployment.

## Local Execution
You can run the scan locally without installing anything permanently:

```bash
npx -y @radu_api/sentinel-scan ./manifest.json
```

## CI/CD Integration
This project uses `sentinel-scan-action`. The workflow is configured in [`.github/workflows/sentinel.yml`](./.github/workflows/sentinel.yml).

### Enable Enforcement (Gating)
To automatically block non-compliant Pull Requests, set `enforce` to `true` in your workflow:

```yaml
      - uses: MOXO08/sentinel-scan-action@v1
        with:
          manifest: "./manifest.json"
          enforce: "true" # The job will fail on compliance violations
```

## PR Audit Summary
When a scan is triggered by a Pull Request, Sentinel automatically posts an audit summary as a comment:

> ## 🛡 Sentinel EU AI Act Compliance Scan
>
> **App:** `sentinel-demo-app` @ `v1.1.0`
> **Status:** ✅ `COMPLIANT`
> **Risk Score:** `0/100`
>
> ### 🚩 Triggered Flags / Issues
> _None_
>
> ---
> _Usage in Workflow:_ 
> ```yaml
> - uses: radu_api/sentinel-scan-action@v1
>   with:
>     manifest: "./manifest.json"
> ```
> _Powered by [Sentinel](https://sentinel-ai.dev)_

---
## 💎 Professional Licensing
Scale your AI compliance with advanced audit trails and priority support.

| Plan | Price | Checkout |
| :--- | :--- | :--- |
| **Sentinel Developer** | $0 | <a href="https://radumuresanu.lemonsqueezy.com/checkout/buy/89ca9ead-179c-497d-b2b7-2a474814ba80?embed=1" class="lemonsqueezy-button">Buy Sentinel Developer (Free)</a> |
| **Sentinel PRO** | $49/mo | <a href="https://radumuresanu.lemonsqueezy.com/checkout/buy/aefa17e9-7794-44c0-bf3f-65b1a93c5182?embed=1" class="lemonsqueezy-button">Buy Sentinel Pro</a> |
| **Sentinel Enterprise** | $299/mo | <a href="https://radumuresanu.lemonsqueezy.com/checkout/buy/2af0bd06-7319-4390-91d4-397998ab012b?embed=1" class="lemonsqueezy-button">Buy Sentinel Enterprise</a> |

<script src="https://assets.lemonsqueezy.com/lemon.js" defer></script>

---
[sentinel-ai.dev](https://sentinel-ai.dev)
