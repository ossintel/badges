# OSSIntel Badges (`ossintel/badges`)

[![OSSIntel OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/ossintel/ossintel.json)](https://ossintel.js.org/repo/ossintel/ossintel)
[![OSSIntel Maintainer](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/user/mayank1513.json)](https://ossintel.js.org/user/mayank1513)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

> Zero-infrastructure, edge-cached endpoint badges for open-source repositories and developer identities, powered by [OSSIntel](https://ossintel.js.org).

---

## 🚀 How It Works

OSSIntel calculates deterministic intelligence scores (OSSIQ, velocity, health, risk, maintainer impact) and commits lightweight JSON endpoints directly to this repository. [Shields.io](https://shields.io/badges/endpoint-badge) reads these raw JSON endpoints and renders verifiable badges with zero server compute overhead.

```text
┌─────────────────┐       ┌────────────────────┐       ┌─────────────────┐       ┌──────────────────┐
│  OSSIntel Web   │ ───►  │  ossintel/badges   │ ───►  │  Shields.io     │ ───►  │  Your README.md  │
│  (Analysis API) │       │  (GitHub Raw CDN)  │       │  (Edge Render)  │       │  (Embedded SVG)  │
└─────────────────┘       └────────────────────┘       └─────────────────┘       └──────────────────┘
```

- **Zero-Compute Serving**: Badges are served directly via GitHub's raw CDN and cached by Shields.io.
- **Always Synchronized**: Analyzed repositories and user profiles automatically update in the background.
- **Privacy & Rate-Limit Safe**: No API keys or backend servers hit when visitors load your README.

---

## 📦 Usage & Embed Codes

### 1. Repository Badges

Replace `:owner` and `:repo` with your target GitHub repository:

#### Markdown
```markdown
[![OSSIntel OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.json)](https://ossintel.js.org/repo/:owner/:repo)
```

#### HTML
```html
<a href="https://ossintel.js.org/repo/:owner/:repo">
  <img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.json" alt="OSSIntel OSSIQ" />
</a>
```

---

### 2. Developer / User Profile Badges

Replace `:username` with your GitHub handle:

#### Markdown
```markdown
[![OSSIntel OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/user/:username.json)](https://ossintel.js.org/user/:username)
```

#### HTML
```html
<a href="https://ossintel.js.org/user/:username">
  <img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/user/:username.json" alt="OSSIntel OSSIQ" />
</a>
```

---

## 🎨 Metric & Style Customization

Shields.io supports query parameters for style, logos, and custom labels:

| Parameter | Options | Example |
| :--- | :--- | :--- |
| **`style`** | `flat`, `flat-square`, `for-the-badge`, `plastic`, `social` | `&style=for-the-badge` |
| **`logo`** | Any SimpleIcons slug (e.g., `github`, `typescript`, `react`) | `&logo=github` |
| **`label`** | Custom badge text override | `&label=Project+OSSIQ` |

#### Example: "For-The-Badge" Style
```markdown
[![OSSIntel OSSIQ](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/ossintel/badges/main/repo/:owner/:repo.json&style=for-the-badge)](https://ossintel.js.org/repo/:owner/:repo)
```

---

## 📂 Repository Directory Layout

```text
├── repo/
│   └── :owner/
│       └── :repo.json       # Repository OSSIQ metrics
└── user/
    └── :username.json       # Developer identity OSSIQ metrics
```

### JSON Schema (Shields.io Custom Endpoint Standard)

```json
{
  "schemaVersion": 1,
  "label": "OSSIntel OSSIQ",
  "message": "88/100",
  "color": "brightgreen",
  "namedLogo": "github",
  "cacheSeconds": 3600
}
```

---

## 🔒 Security & Contribution

This repository is machine-managed by the **OSSIntel Platform**. Pull requests modifying JSON metrics manually will be rejected by CI.

To refresh or update badge metrics for your repository or profile, analyze your project at [ossintel.js.org](https://ossintel.js.org).

---

<p align="center">
  Built with 💖 by the <a href="https://ossintel.js.org">OSSIntel Team</a>
</p>
