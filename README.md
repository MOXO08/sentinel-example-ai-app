# 🛡 Sentinel Example AI App
**Automated EU AI Act Compliance Checking**

[![Sentinel Status](https://sentinel-api.sentinel-moxo.workers.dev/api/v1/badge/sentinel-example-ai-app)](https://sentinel-api.sentinel-moxo.workers.dev/dashboard)

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
[sentinel-ai.dev](https://sentinel-ai.dev)
