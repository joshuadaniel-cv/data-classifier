# CV Data Classification Tool

A static single-page application (SPA) for classifying data assets against **ISO/IEC 27001:2022** and **GDPR (EU) 2016/679**.

## Overview

This tool provides a guided wizard to assess data assets across three dimensions — Confidentiality, Integrity, and Availability (CIA) — and identify applicable GDPR data categories. It then produces an overall classification label and a list of relevant ISO 27001 controls.

All processing is client-side. No data is transmitted or stored.

## Quick Start

Open `index.html` in any modern browser, or deploy to GitHub Pages.

### GitHub Pages Deployment

1. Push this repository to GitHub.
2. Go to **Settings → Pages → Source → Deploy from a branch**.
3. Select `main` / `/ (root)` and save.
4. The site will be live at `https://<your-org>.github.io/<repo-name>/` within 60 seconds.

## Repository Structure

| File | Purpose |
|------|---------|
| `index.html` | Main application (self-contained SPA) |
| `fonts/` | Self-hosted Plus Jakarta Sans font files |
| `TECH_SPEC.md` | Technical specification |
| `TEST_CASES.md` | Validation test cases |
| `README.md` | This file |
| `.github/workflows/deploy.yml` | GitHub Actions deployment (optional) |

## Browser Support

Chrome, Edge, Firefox, Safari (macOS/iOS), mobile responsive. Print/PDF export supported. Internet Explorer is not supported.

## Governance

| Role | Responsibility |
|------|---------------|
| Governance Analyst | Content accuracy, classification logic, standard references |
| DPO | GDPR article accuracy |
| ISMS Manager | ISO 27001 control mapping accuracy |
| IT / DevOps | Repository management, GitHub Pages configuration |

## Standards

- ISO/IEC 27001:2022
- GDPR (EU) 2016/679
