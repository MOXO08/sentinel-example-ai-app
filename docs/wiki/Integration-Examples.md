# Integration Examples 🚀

Sentinel can be integrated into your development lifecycle in two primary ways.

## 1. GitHub Actions (Automated PR Audit)

Add the Sentinel AI Compliance Scan to your `.github/workflows/main.yml`. This will automatically audit every Pull Request.

```yaml
- name: Run Sentinel AI Audit
  uses: radu_api/sentinel-scan-action@v1
  with:
    manifest: "./manifest.json"
    license_token: ${{ secrets.SENTINEL_LICENSE }}
```

**Benefits**:
- **Smart Gating**: Block non-compliant code from merging.
- **PR Comments**: Automated summaries of violations.

## 2. Local CLI (Developer Sandbox)

Install and run Sentinel locally to verify compliance before you push code.

### Initialization
```bash
npx @radu_api/sentinel-scan --init
```

### Direct Audit
```bash
npx @radu_api/sentinel-scan ./manifest.json
```

---
## 🌐 Connectivity
All remote audits are processed via:
`https://sentinel-api.sentinel-moxo.workers.dev`

[Back to Home](Home)
