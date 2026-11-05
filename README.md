# OSSIntel Badges (`ossintel/badges`)

[![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/repo/ossintel/ossintel.svg)](https://ossintel.js.org/repo/ossintel/ossintel)
[![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/user/mayank1513.svg)](https://ossintel.js.org/user/mayank1513)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> Zero-infrastructure, edge-cached badges for open-source repositories and developer identities, powered by [OSSIntel](https://ossintel.js.org).

---

## 🚀 How It Works

OSSIntel computes deterministic intelligence scores (OSSIQ) and automatically commits both **native dual-color SVGs** and lightweight **Shields.io JSON endpoints** to this repository.

```text
┌─────────────────┐       ┌────────────────────┐       ┌──────────────────┐
│  OSSIntel Web   │ ───►  │  ossintel/badges   │ ───►  │  Your README.md  │
│  (Analysis API) │       │  (GitHub Raw CDN)  │       │  (Native SVG)    │
└─────────────────┘       └────────────────────┘       └──────────────────┘
                                    │
                                    ▼
                          ┌────────────────────┐       ┌──────────────────┐
                          │  Shields.io        │ ───►  │  Your README.md  │
                          │  (Custom Endpoint) │       │  (Shields Badge) │
                          └────────────────────┘       └──────────────────┘
```

- **Zero Compute at Render**: Badges are served directly by GitHub's global raw CDN.
- **Dual-Color Typography**: Native SVGs feature the official OSSIntel circuit eye logo and dual-color `OSS` + `IQ` wordmark.
- **Always Synchronized**: Analyzed repositories and user profiles automatically update on analysis.
- **Privacy Safe**: Zero external tracking or server calls when visitors load your README.

---

## 📦 Usage & Embed Codes

### Option 1: OSSIntel Native Badges (Recommended)

Self-contained vector badges with contrast borders for seamless dark and light mode rendering.

#### Repository Badges

* **Dark Theme (Default):**
  ```markdown
  [![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.svg)](https://ossintel.js.org/repo/:owner/:repo)
  ```
* **Light Theme:**
  ```markdown
  [![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo-light.svg)](https://ossintel.js.org/repo/:owner/:repo)
  ```

#### Developer / User Profile Badges

* **Dark Theme (Default):**
  ```markdown
  [![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/user/:username.svg)](https://ossintel.js.org/user/:username)
  ```
* **Light Theme:**
  ```markdown
  [![OSSIQ](https://raw.githubusercontent.com/ossintel/badges/main/user/:username-light.svg)](https://ossintel.js.org/user/:username)
  ```

---

### Option 2: Shields.io Endpoint Badges

Point [Shields.io](https://shields.io/badges/endpoint-badge) to the `.json` endpoint in this repository:

#### Repository Badge
```markdown
[![OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.json)](https://ossintel.js.org/repo/:owner/:repo)
```

#### User Profile Badge
```markdown
[![OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/user/:username.json)](https://ossintel.js.org/user/:username)
```

#### Shields.io Customization Parameters

| Parameter | Options | Example |
| :--- | :--- | :--- |
| **`style`** | `flat`, `flat-square`, `for-the-badge`, `plastic` | `&style=for-the-badge` |
| **`logo`** | SimpleIcons slug (e.g. `github`, `typescript`) | `&logo=github` |
| **`label`** | Custom text override | `&label=Alpha+Score` |

```markdown
[![OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.json&style=for-the-badge)](https://ossintel.js.org/repo/:owner/:repo)
```

---

## 📂 Repository Directory Layout

```text
ossintel/badges
├── repo/
│   └── :owner/
│       ├── :repo.svg          # Dark native SVG badge (Default)
│       ├── :repo-light.svg    # Light native SVG badge
│       └── :repo.json         # Shields.io endpoint schema
└── user/
    ├── :username.svg          # Dark native SVG badge (Default)
    ├── :username-light.svg    # Light native SVG badge
    └── :username.json         # Shields.io endpoint schema
```

### JSON Schema (Shields.io Endpoint Standard)

```json
{
  "schemaVersion": 1,
  "label": "OSSIQ",
  "message": "95/100",
  "color": "brightgreen",
  "namedLogo": "github",
  "cacheSeconds": 3600
}
```

---

## 🔒 Security & Automation

This repository is machine-managed by the **OSSIntel Platform**. Badge files are committed automatically during repository and profile evaluation. Manual edits to scores will be overwritten on the next sync.

To evaluate or refresh badge scores, visit [ossintel.js.org](https://ossintel.js.org).

---

<p align="center">
  Built with 💖 by the <a href="https://ossintel.js.org">OSSIntel Team</a>
</p>
