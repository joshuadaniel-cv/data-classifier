# Technical Specification — CV Data Classification Tool

**Version:** 1.0.0
**Last Updated:** 5 March 2026
**Standards:** ISO/IEC 27001:2022, GDPR (EU) 2016/679

---

## Architecture

| Property | Value |
|----------|-------|
| Type | Static single-page application (SPA) |
| Hosting | GitHub Pages |
| Files | `index.html` + `fonts/` directory |
| Fonts | Plus Jakarta Sans (self-hosted TTF, weights: 300, 400, 500, 700, 800) |
| Frameworks | None — vanilla HTML5 / CSS3 / ES6+ |
| Build Process | None required |
| Data Storage | None — client-side only, no data transmitted |

---

## Wizard Flow (4 Steps)

| Step | Name | Fields |
|------|------|--------|
| 1 | Confidentiality | Radio: Low / Medium / Medium-High / High / Critical |
| 2 | Integrity & Availability | Radio x2: Low / Medium / High / Critical each |
| 3 | GDPR Categories | Checkbox: Personal / Special / Children / Financial / Criminal / None |
| 4 | Result | CIA cards + overall badge + GDPR flags + ISO controls |

---

## CIA Scoring Logic

**Overall classification** = `max(confidentiality, integrity, availability)`

**Level order:** Low < Medium < Medium-High < High < Critical

| Overall Score | Classification Label |
|--------------|---------------------|
| Low | Public |
| Medium | Internal |
| Medium-High | Confidential |
| High | Confidential |
| Critical | Restricted |

---

## ISO 27001 Controls

| Control | Annex Reference | Trigger Condition |
|---------|----------------|-------------------|
| Information Classification | A.8.2 | Always |
| Information Labelling | A.8.3 | Confidentiality ≥ Medium |
| Access Control Policy | A.9.1 | Confidentiality ≥ Medium |
| Cryptography | A.8.24 | Confidentiality ≥ High |
| Configuration Management | A.8.9 | Integrity ≥ High |
| Logging and Monitoring | A.8.15 | Integrity = Critical |
| Information Backup | A.8.13 | Availability ≥ High |
| Redundancy | A.8.14 | Availability = Critical |
| GDPR Art. 32 TOMs | GDPR | Any personal data category selected |

---

## GDPR Data Categories

| Value | GDPR Article | Label |
|-------|-------------|-------|
| personal | Art. 4(1) | Personal Data |
| special | Art. 9 | Special Category Data |
| children | Art. 8 | Children's Data |
| financial | Art. 5(f) | Financial Data |
| criminal | Art. 10 | Criminal Records |
| none | N/A | No Personal Data |

---

## Design System

### Colours

| Token | Hex | Usage |
|-------|-----|-------|
| --black | #000000 | Dark mode bg / light mode text |
| --white | #FFFFFF | Light mode bg / dark mode text |
| --green-light | #A8FFA3 | Primary accent / interactive (dark mode) |
| --green-mid | #5BFF54 | Hover states |
| --green-dark | #00C200 | Primary accent (light mode) |
| --navy | #0A1628 | Reserved |
| --blue | #1A1AFF | Reserved secondary accent |

### Themes

| Theme | Background | Card | Text |
|-------|-----------|------|------|
| Dark (default) | #000000 | #111111 | #FFFFFF |
| Light | #FFFFFF | #F7F7F7 | #000000 |

---

## Important Links

| Label | URL | Editable |
|-------|-----|----------|
| ISO 27001 Classification | https://www.isms.online/iso-27001/annex-a-2022/5-12-classification-of-information-2022/ | No |
| GDPR Full Text | https://gdpr-info.eu/ | No |
| Internal Data Protection Policy | SharePoint link | Yes |
| Data Protection Officer | uk.privacy@cvglobal.co | Yes |
| ENISA Guidelines | https://www.enisa.europa.eu/topics/data-protection | No |
| CV Privacy Policy | https://www.cvglobal.co/en/privacy-policy | No |

---

## Security

| Control | Status |
|---------|--------|
| Data transmission | None — fully client-side |
| Cookies | None |
| Analytics | None |
| LocalStorage | Not used (sessionStorage for theme only) |
| HTTPS | Enforced by GitHub Pages |

---

## Browser Support

Chrome/Edge, Firefox, Safari (macOS/iOS), mobile responsive, print/PDF. Internet Explorer not supported.
