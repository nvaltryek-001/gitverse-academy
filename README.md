<h1 align="center">🚀 GitVerse Academy</h1>

<p align="center"><b>Learn Git, GitHub and GitHub Actions by doing: lessons, a safe Git simulator, games and quizzes in one offline web app.</b></p>

<p align="center">
  <img src="https://img.shields.io/badge/HTML%2FCSS%2FJS-no%20dependencies-0ea5e9?style=flat-square" alt="No dependencies" />
  <img src="https://img.shields.io/badge/works-offline-34d399?style=flat-square" alt="Works offline" />
  <img src="https://img.shields.io/badge/deploy-GitHub%20Pages-181717?style=flat-square&logo=github" alt="GitHub Pages" />
</p>

<p align="center"><img src="docs/demo.gif" width="800" alt="Walkthrough of GitVerse: dashboard, lessons, commands, terminal lab, games, quiz and progress" /></p>

## Why

Beginners usually learn Git by memorising commands they are scared to run. GitVerse lets them type real Git commands into a **simulator that tracks repository state** (commits, branches, merges, remotes) without touching their machine, then reinforces it with games and a quiz.

## Features

| | Feature | What it does |
|---|---|---|
| 🏠 | Dashboard | XP, daily streak, chapter progress and quick-start actions |
| 📚 | Learn | 9 chapters in plain English, from "what is Git" to Actions |
| ⌨️ | Commands | Searchable command reference |
| 💻 | Terminal Lab | Git simulator with guided missions (init → commit → branch → merge → push) |
| 🎮 | Games | Command-recall mini games |
| 📝 | Quiz | Multiple-choice checks with instant feedback |
| 🏆 | Progress | Saved locally in the browser (`localStorage`), no account needed |

## Screenshots

| Dashboard | Terminal Lab |
|---|---|
| ![Dashboard](docs/screenshots/01-dashboard.png) | ![Terminal Lab](docs/screenshots/04-terminal-lab.png) |
| **Learn** | **Quiz** |
| ![Learn](docs/screenshots/02-learn.png) | ![Quiz](docs/screenshots/06-quiz.png) |

<p align="center"><img src="docs/screenshots/mobile.png" width="260" alt="Mobile layout" /></p>

## Run it

```bash
git clone https://github.com/nvaltryek-001/gitverse-academy
cd gitverse-academy
python -m http.server 8000   # or just open index.html
```

## Architecture

```mermaid
flowchart LR
  UI[index.html<br/>single-file SPA] --> R[Router: Dashboard · Learn · Commands · Lab · Games · Quiz · Progress]
  R --> SIM[Git simulator<br/>in-memory repo model]
  R --> ST[(localStorage<br/>XP · streak · repo state)]
  GH[GitHub Actions] -->|pages.yml| PG[GitHub Pages]
```

## Deployment

`.github/workflows/pages.yml` publishes the site to GitHub Pages on every push to `main`.

## Limitations

- The terminal is a teaching simulator; it supports a curated subset of Git commands.
- Progress is per-browser; clearing site data resets it.

<sub>Screenshots and demo were captured from the running app with Playwright.</sub>
