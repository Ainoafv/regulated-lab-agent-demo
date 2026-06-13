# Regulated Lab Agent Demo

Interactive QC lab scenario for Thermo Fisher outreach (Adam Collins, Etapa 1 — 23 Jun 2026).

**Not Thermo Fisher software** — fictional batch B-2047, HPLC QC, LIMS/ELN vocabulary. Same architecture as [agent-engineering-demo](https://github.com/Ainoafv/agent-engineering-demo): closed action set, permission gate (AUTO / ASK / NEVER), hash-chained audit log.

## Local preview

Open `web/index.html` in a browser (double-click or):

```bash
open web/index.html
```

## Deploy to GitHub Pages

1. Create repo `regulated-lab-agent-demo` on GitHub (public).
2. Push this folder (use `web/` as root for Pages, or copy `web/index.html` to repo root).

```bash
cd thermo-lab-agent-demo
git init
git add web/index.html index.html LOOM-SCRIPT.md
git commit -m "Add regulated lab agent interactive demo"
git branch -M main
git remote add origin https://github.com/Ainoafv/regulated-lab-agent-demo.git
git push -u origin main
```

3. GitHub → Settings → Pages → Source: **main** → folder **/web** (or root if you moved index.html).
4. URL: `https://ainoafv.github.io/regulated-lab-agent-demo/`
5. Update `LOOM-SCRIPT.md` and `EMAIL-ADAM.txt` with the live URL.

## Files

| File | Purpose |
|------|---------|
| `web/index.html` | Interactive demo |
| `LOOM-SCRIPT.md` | 6 min Loom walkthrough for Adam |
| `INTERVIEW-PREP.md` | Call prep (Spanish) |
| `EMAIL-ADAM.txt` | Email template |
| `clients/thermo/CONTEXT.md` | Process tracking |

## Scenarios (preset chips)

1. **Summarize batch** → `generate_summary` → AUTO  
2. **Release batch** → `release_batch` → NEVER  
3. **Flag anomaly** → `flag_anomaly` → ASK  
4. **ELN entry** → `write_eln_entry` → ASK  
5. **LIMS query** → `query_lims_status` → AUTO  
