# 🛡 Sentinel Example AI App

Acest repository demonstrează integrarea **Sentinel** în fluxul de CI/CD pentru verificarea conformității cu **EU AI Act**.

## Ce este Sentinel?
Sentinel este un scanner de conformitate AI offline care verifică manifestele și codul aplicațiilor tale față de reglementările EU AI Act. Acesta asigură că sistemele tale AI respectă cerințele de transparență, securitate și supervizare umană înainte de a fi puse în producție.

## Rulare Locală
Poți rula scanarea local fără a instala nimic permanent:

```bash
npx -y @radu_api/sentinel-scan ./manifest.json
```

## Integrare CI/CD
Acest proiect folosește `sentinel-scan-action`. Fluxul de lucru este configurat în [`.github/workflows/sentinel.yml`](./.github/workflows/sentinel.yml).

### Cum activezi enforcement-ul (Gating)
Pentru a bloca automat Pull Request-urile care nu sunt conforme, schimbă setarea `enforce` în `true`:

```yaml
      - uses: sentinel-ai/sentinel-scan-action@v1
        with:
          manifest: "./manifest.json"
          enforce: "true" # Acum job-ul va eșua la violări
```

## Preview Raport PR
Când scanarea detectează probleme, Sentinel postează automat un raport în PR:

> ## 🛡 Sentinel EU AI Act Compliance Scan
>
> **Status:** ❌ `NON_COMPLIANT`
>
> ### Triggered Rules
> - `ART13-TRANSPARENCY-MISSING`: High-risk systems must implement transparency measures.
> - `ART10-DATA-GOVERNANCE`: Training data sets must be documented.
>
> **Compliance Score:** 65%
>
> ---
> _Run locally:_
> `npx @radu_api/sentinel-scan ./manifest.json`
> Test PR for Sentinel

---
[sentinel-ai.dev](https://sentinel-ai.dev)

