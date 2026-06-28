# Claude / Girl Friday Handoff - LGV Executive Campaign Site

Date: 2026-06-28
From: Codex
To: Claude / Girl Friday

## TL;DR

LGV is sleeping. Do not disturb the DNS tonight. `lgv.sunified.ai` remains pointed at GitHub Pages so we can see whether GitHub completes HTTPS certificate provisioning.

Vercel is already deployed and working as the fast HTTPS fallback:

`https://lgv-executive-minisite.vercel.app/`

## Repo

```txt
https://github.com/FUSED-ID/lgv-executive
```

Local M4 path:

```txt
/Users/lg/Documents/Codex/2026-06-27/in-2/outputs/lgv-executive-minisite
```

## Current State

- Site source: pushed to GitHub.
- GitHub Pages: built.
- GitHub custom domain: `lgv.sunified.ai`.
- DNS CNAME: `lgv.sunified.ai -> fused-id.github.io`.
- GitHub HTTPS: not enforced; certificate still pending.
- Vercel: live, HTTPS, GitHub-integrated.
- Infomaniak: preferred strategic/sovereign hosting candidate, not yet deployed.

## Important User Preferences

- Inter font only.
- Online site may be dark teal.
- Printed CV/PDF should stay off-white/readable.
- Campaign email is `lgv@sunified.ai`.
- Keep Sunified on the front foot.
- Do not make the campaign look like LGV is abandoning Sunified.
- Agent-ready matters: keep `llms.txt`, `resume.json`, `cv.txt`, sitemap, robots, and workflow YAML.

## Tomorrow Value-Add Ideas

1. Re-check GitHub cert:

```bash
cd /Users/lg/Documents/Codex/2026-06-27/in-2/outputs/lgv-executive-minisite
gh api repos/FUSED-ID/lgv-executive/pages --jq '{status, cname, html_url, https_enforced}'
gh api repos/FUSED-ID/lgv-executive/pages -X PUT -F https_enforced=true -F 'source[branch]=main' -F 'source[path]=/'
```

If GitHub says the cert exists, enforce HTTPS and test:

```bash
curl -I https://lgv.sunified.ai/
```

2. If GitHub cert is still stuck, recommend moving `lgv.sunified.ai` to Vercel:

```txt
lgv.sunified.ai CNAME cname.vercel-dns.com
```

Only change DNS after LGV confirms.

3. If Infomaniak wins, use GitHub as source and deploy static files to Infomaniak Web Hosting. Do not use the site builder for this project.

4. Improve mobile polish:
   - Check hero headline fit on iPhone width.
   - Portrait is hidden under 900px; confirm this still feels right.
   - Buttons are full-width under 560px.

5. Add a short `docs/domain-migration-runbook.md` if DNS changes tomorrow.

6. Consider one small UX addition:
   - Add a footer link to `llms.txt` / `resume.json` as "Agent profile" only if LGV likes visible agent affordances.

## Things Not To Do Without LGV

- Do not move DNS overnight.
- Do not send Angela email.
- Do not add forms or tracking scripts.
- Do not commit `.vercel/project.json`.
- Do not replace Inter.
- Do not darken the CV/PDF.

## Verification Links

```txt
Vercel live: https://lgv-executive-minisite.vercel.app/
GitHub Pages live over HTTP: http://lgv.sunified.ai/
Repo: https://github.com/FUSED-ID/lgv-executive
```

## Suggested Morning Message to LGV

GitHub cert status is [ready/still pending]. Vercel is already healthy. My recommendation is [stay on GitHub / move lgv.sunified.ai to Vercel / set up Infomaniak], because [one-sentence reason].
