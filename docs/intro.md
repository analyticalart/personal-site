# Welcome to My Book

> *"The more that you read, the more things you will know."*
> — Dr. Seuss

This is your **introduction page** — the starting point for everything in this collection. Below you'll find a showcase of every markdown feature available, so you can copy patterns and use them in your own pages.

---

## About This Book

This book is a **living document**. Pages are written in plain Markdown (`.md` files), rendered on the fly in your browser — no build step, no framework, no fuss.

You'll find chapters covering:

- Core concepts and foundational knowledge
- Deep dives with examples and code
- Reference tables and quick-lookup guides
- And more as the collection grows

---

## What You Will Learn

### Section Breakdown

| Chapter | Topic | Difficulty |
|---------|-------|------------|
| 1.1 | Overview & Landscape | Beginner |
| 1.2 | Deep Dive | Intermediate |
| 2.1 | Core Concepts | Intermediate |
| 2.2 | Real-World Examples | Advanced |

---

## Prerequisites

Before diving in, make sure you're comfortable with:

1. **Basic terminal usage** — `cd`, `ls`, `cat`, file paths
2. **Git fundamentals** — clone, commit, push, pull
3. **A text editor** — VS Code, Neovim, or anything you love

Optional but useful:

- YAML syntax (for config files)
- A rough mental model of how DNS works
- Familiarity with containers (Docker/Podman)

---

## Key Concepts at a Glance

### What is X?

X is a **declarative, GitOps-friendly** approach to doing Y, where you define *what you want* rather than *how to get there*. Think of it like writing a recipe vs. cooking step by step.

### Why does it matter?

Because **manual processes don't scale**. When your infrastructure grows from 1 server to 100, you need:

- **Reproducibility** — the same config gives the same result, always
- **Auditability** — every change is tracked in Git
- **Speed** — automation beats humans at repetitive tasks every time

### The three pillars

```
+-----------------------------------------+
|           The Three Pillars             |
+-------------+-----------+---------------+
|  Observe    |  Enforce  |  Recover      |
|  (metrics)  |  (policy) |  (chaos)      |
+-------------+-----------+---------------+
```

---

## A Code Example

Here's a minimal working configuration in YAML:

```yaml
# config.yaml
apiVersion: v1
kind: Config
metadata:
  name: my-service
  labels:
    env: production
    team: platform

spec:
  replicas: 3
  strategy: RollingUpdate
  resources:
    requests:
      cpu: "250m"
      memory: "256Mi"
    limits:
      cpu: "500m"
      memory: "512Mi"
```

And the equivalent as a shell one-liner:

```bash
# Apply config and watch rollout
kubectl apply -f config.yaml && kubectl rollout status deploy/my-service
```

Or in Python if you're automating it:

```python
import subprocess

def apply_and_watch(manifest: str) -> None:
    subprocess.run(["kubectl", "apply", "-f", manifest], check=True)
    subprocess.run(["kubectl", "rollout", "status", f"deploy/{manifest}"], check=True)
```

---

## Common Pitfalls

> **Heads up:** These are the mistakes *everyone* makes at least once.

- **Hardcoding secrets** in config files — use environment variables or a secrets manager
- **Skipping resource limits** — unbounded pods will eat your cluster alive
- **No readiness probes** — traffic hits your pod before it's actually ready
- **Manual hotfixes** in production — if it's not in Git, it didn't happen

---

## Folder Structure Reference

```
my-book/
├── index.html          <- The book shell (edit chapters[] here)
├── docs/
│   ├── intro.md        <- This file
│   ├── ch1-overview.md
│   ├── ch1-deep-dive.md
│   ├── ch2-concepts.md
│   └── ch2-examples.md
└── assets/             <- Optional: images, diagrams
```

---

## Quick Checklist

- [ ] Spellcheck the content
- [ ] All code blocks have a language tag
- [ ] Cross-references use the correct `file` path
- [ ] Images are in `assets/` and linked relatively
- [ ] Chapter is registered in `index.html` under `chapters[]`

---

## Useful References

- [Markdown Guide](https://www.markdownguide.org/) — the definitive reference
- [GitHub Pages Docs](https://docs.github.com/en/pages) — deploying this site
- [marked.js](https://marked.js.org/) — the renderer powering this book

---

## How to Navigate

Use the **sidebar** on the left to jump between chapters.
Use **Prev / Next** buttons in the top bar to move page by page.
On mobile, tap the menu button to open the sidebar.

Links in the URL bar are **shareable** — each page updates the hash automatically.

---

*Last updated: 2026 · Built with plain HTML + Markdown · No frameworks were harmed.*
