# ₿ Bitcoin Security Atlas (2009–2034)

**Bitcoin Security Intelligence Dashboard** — a zero-dependency, static and offline-capable research site.

**Live URL (once GitHub Pages is enabled):** https://base27-cvnss.github.io/BitcoinAtlas/

## Purpose

A visual evidence atlas of Bitcoin security issues, vulnerabilities, public-key exposure and the post-quantum migration discussion. It clearly separates:

- **2009–2026** — documented historical events and verified primary-source observations.
- **2027–2034** — clearly marked scenarios, not future facts or predictions.
- **Public key exposed** is NOT the same as **private key compromised**, **coins lost**, or **quantum attack demonstrated**.

## Modules

1. Overview: evidence-based KPIs, Glassnode 20 May 2026 snapshot, 25-year strip.
2. Timeline: searchable/filterable historical incident cards and detail panel.
3. Vulnerability Matrix: curated event counts by category and epoch (not raw CVE counts).
4. Attack Path Explorer: explainable, non-operational cause → condition → consequence → mitigation paths.
5. Quantum Scenario Lab: editable migration/reachability hypotheses with BTC conservation checks.
6. Mitigations & Sources: BIP-360, BIP-361, safeguards and citations.

## Run locally

Open `index.html` directly in a modern browser. No Node.js, bundler, CDN, database or API key is required. All visuals are implemented with HTML/CSS/SVG and native JavaScript.

## Deploy with GitHub Pages

The repository contains `.github/workflows/pages.yml`. In **Settings → Pages**, set the **Source** to **GitHub Actions**. Pushes to `main` will deploy the site. The site URL is expected to be:

https://base27-cvnss.github.io/BitcoinAtlas/

The workflow cannot guarantee publication until Pages is enabled and GitHub Actions has the requisite repository permissions.

## Dataset and modeling integrity

The initial Glassnode figure is **6.04 million BTC = 30.2% of issued supply**, published **2026-05-20**. It measures **public-key exposure at rest**, not compromised Bitcoin. The dashboard does not present a 2034 Q-Day probability.

Scenario variables:
- `E`: baseline exposed BTC (6.04 million, one dated snapshot)
- `m`: chosen fraction able to migrate in the hypothetical scenario
- `r`: chosen fraction migrated among the movable group
- `q`: chosen fraction of remaining exposed surface hypothetically reached

Then:

```text
moved        = E * m * r
remainMovable= E * m * (1 - r)
remainLocked = E * (1 - m)
remain       = remainMovable + remainLocked
surfaceReach = remain * q

moved + remainMovable + remainLocked = E
```

Neither `surfaceReach` nor `remain` is a claim of actual theft or financial loss. The term `remainLocked` means **user-assumed non-migratable within the model**, not objectively lost keys.

## Data quality

- Events are curated, **not an exhaustive security advisory feed**.
- **Unit consistency** is maintained: BTC balances are never added to counts of keys, CVEs or papers.
- Vulnerabilities with an authoritative fix link are marked appropriately; legacy unpatched installations may remain exposed.
- **BIP-360 and BIP-361 are draft proposals** as of the 2026-10-11 review.
- Future claims and unverified social-media numbers from preliminary dashboards are excluded.

## References

The sources are embedded as clickable links within the app, including Glassnode Research, Bitcoin Core advisories and release notes, bitcoin.org, the Bitcoin BIP repository and NIST.

## License

MIT — Long Ngo, 2026. Vietflexmap. This is a research visualization, not financial advice, a wallet scanner or proof of an exploitable quantum attack.
