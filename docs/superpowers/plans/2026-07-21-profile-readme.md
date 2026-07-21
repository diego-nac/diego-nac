# Data Portfolio Profile README Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace Diego Melo's outdated profile README with a verified, English-language Data Engineering and Data Analytics portfolio featuring dependable dynamic visuals.

**Architecture:** `README.md` is the presentation layer and remains useful without dynamic images. `.github/workflows/snake.yml` is the only automation component; it renders light/dark contribution SVGs and publishes them to the existing `output` branch. Validation combines repository-link checks, external asset checks, content-policy searches, Markdown inspection, YAML parsing, and public post-push verification.

**Tech Stack:** GitHub-Flavored Markdown, supported inline HTML, Shields.io, Skill Icons/Devicon, Readme Typing SVG, GitHub Readme Stats, Streak Stats, Activity Graph, Profile Trophy, GitHub Actions, Platane/snk, GitHub Pages-compatible HTTPS assets.

## Global Constraints

- Write all portfolio copy in English.
- Position Diego primarily as a Data Analyst and Data Engineer; AI/RAG/GraphRAG are differentiators.
- Use only claims supported by the 2026 resume, supplied LinkedIn profile, or public repositories observed on 2026-07-21.
- Do not publish Diego's phone number, secrets, confidential Maplink details, invented metrics, clients, or outcomes.
- Use `diego-nac` in every GitHub widget and repository URL.
- Keep useful text visible when third-party widgets fail and provide descriptive image alternative text.
- Include all 16 observed public repositories in the repository explorer, separated into owned work and forks.
- Do not imply production maturity for academic repositories.

---

### Task 1: Static Portfolio Narrative and Repository Catalog

**Files:**
- Modify: `README.md`
- Reference: `docs/superpowers/specs/2026-07-21-profile-readme-design.md`

**Interfaces:**
- Consumes: verified resume, LinkedIn copy supplied in the conversation, and the public repository audit in the approved design.
- Produces: stable README anchors and text sections that dynamic cards can enhance but are not required to understand.

- [ ] **Step 1: Capture the pre-change policy failures**

Run:

```bash
rg -n 'Desenvolvedor Web Full Stack|diego-melo|Diego-Melo|diegomelo624@gmail.com|Sistema de Login|HTML, CSS e JS' README.md
```

Expected: matches for the stale role, username, email, and project focus, proving the current README violates the approved positioning.

- [ ] **Step 2: Replace the hero and professional narrative**

Create a centered hero with the exact primary title `Diego Melo — Data Analyst & Data Engineer` and supporting specialties `Data Modeling • ELT • Data Quality • Analytics • AI Systems`. Add a compact English summary that states:

```text
I build reliable data models, ELT pipelines, analytical workflows, and data products with Python, SQL, BigQuery, and Google Cloud. At Maplink, I work with operational and geospatial data to support analytics and product decisions. I am also an MSc student in Computer Science at UFC, researching GraphRAG and graph-based information retrieval for LLMs.
```

Add contact badges for `https://www.linkedin.com/in/diegonac`, `mailto:diego.nac@hotmail.com`, `https://github.com/diego-nac`, and Fortaleza, Brazil. Do not add a phone badge.

- [ ] **Step 3: Add the data-platform narrative and layered stack**

Add a readable pipeline line with the exact flow:

```text
Sources → Ingestion → Transformation → Warehousing → Analytics → AI Systems
```

Group badges/icons under Languages & Analysis, Data Platform, Cloud & Delivery, Analytics, AI & Retrieval, and Messaging & Automation. Include only technologies enumerated in the approved design.

- [ ] **Step 4: Add concise professional experience and education**

Use four collapsible experience entries with the approved dates and responsibilities for Maplink Data & Innovation Analyst Jr., Maplink IT Intern, Dell Lead, and Fix Tecnologia. Add UFC MSc, UFC BSc, and the EEEP technical degree. Add the three selected NVIDIA/Google credentials and label credentials as issued credentials without presenting expired credentials as current.

- [ ] **Step 5: Add six truthful featured-project cards**

Add static HTML/Markdown cards or compact tables for:

```text
semantic_search_v2 — Multi-source scholarly search, enrichment, normalization, and CLI delivery.
systematic_search — Asynchronous academic extraction pipeline with standardized JSONL outputs.
automatic_learning — Analytical notebooks for regression, classification, KNN, and decision trees.
ica-homeworks — Sensor-data EDA, PCA, regression, classification, and cross-validation.
smart-room-pubsub — Event-driven sensor system using RabbitMQ, gRPC, Flask, and REST.
data-visualization — Interactive analytical visualization using Vega-Lite.
```

Each card must link to `https://github.com/diego-nac/<repository>` and identify academic work where applicable.

- [ ] **Step 6: Add the complete collapsible repository explorer**

Use `<details>` groups containing all repositories exactly once:

```text
Data, Analytics & Research: automatic_learning, semantic_search_v2, systematic_search, ica-homeworks, data-visualization, reconhecimento-de-padroes
Systems & Web Foundations: smart-room-pubsub, dist-systems-lab-1, login-system, estudosLaravel, eeepjaa
Profile: diego-nac
Forks & Learning References: brazil-as-100-people, teste-momento2-edital-tecnico, eeepjaa-1, snk
```

- [ ] **Step 7: Run static content checks**

Run:

```bash
python3 - <<'PY'
from pathlib import Path

text = Path('README.md').read_text()
required = [
    'Data Analyst', 'Data Engineer', 'BigQuery', 'ELT', 'Data Quality',
    'GraphRAG', 'semantic_search_v2', 'systematic_search',
    'automatic_learning', 'ica-homeworks', 'smart-room-pubsub',
    'data-visualization', 'reconhecimento-de-padroes', 'dist-systems-lab-1',
    'login-system', 'estudosLaravel', 'eeepjaa', 'brazil-as-100-people',
    'teste-momento2-edital-tecnico', 'eeepjaa-1', 'snk'
]
for value in required:
    assert value in text, f'missing: {value}'
for forbidden in ['diego-melo', 'Diego-Melo', 'diegomelo624@gmail.com', '+55 85', '98832-4122']:
    assert forbidden not in text, f'forbidden: {forbidden}'
print('static README policy checks passed')
PY
```

Expected: `static README policy checks passed`.

- [ ] **Step 8: Review and commit the static portfolio**

Run `git diff --check && git diff -- README.md`, verify no unsupported claim was introduced, then commit:

```bash
git add README.md
git commit -m "feat: reposition profile around data"
```

Expected: one commit modifying only `README.md`.

---

### Task 2: Dynamic Profile Features and Contribution Workflow

**Files:**
- Modify: `README.md`
- Replace or create: `.github/workflows/snake.yml`
- Remove if superseded: `.github/workflows/main.yml`

**Interfaces:**
- Consumes: README section anchors and the GitHub username `diego-nac` from Task 1.
- Produces: external dynamic cards and two assets at `output/github-contribution-grid-snake.svg` and `output/github-contribution-grid-snake-dark.svg`.

- [ ] **Step 1: Add dynamic hero and analytics cards**

Add HTTPS images using `diego-nac` for:

```text
Readme Typing SVG: Data Analyst; Data Engineer; Analytics & AI Systems; GraphRAG Researcher
Profile views: komarev.com
GitHub Readme Stats: overall stats and compact top languages
GitHub Streak Stats
GitHub Profile Trophy
GitHub Readme Activity Graph
```

Use matching dark/cyan themes. Each image must have distinct alt text. Do not place essential biography only inside images.

- [ ] **Step 2: Define the snake workflow**

Create `.github/workflows/snake.yml` with this complete behavior:

```yaml
name: Generate contribution snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:
  push:
    branches: [main]

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      - name: Generate contribution SVGs
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: diego-nac
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - name: Publish generated SVGs
        uses: crazy-max/ghaction-github-pages@v4
        with:
          build_dir: dist
          branch: output
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Delete `.github/workflows/main.yml` only if it is the stale snake workflow and `snake.yml` fully replaces it.

- [ ] **Step 3: Embed light/dark snake assets**

Use a `<picture>` element whose dark source is:

```text
https://raw.githubusercontent.com/diego-nac/diego-nac/output/github-contribution-grid-snake-dark.svg
```

and whose default image is:

```text
https://raw.githubusercontent.com/diego-nac/diego-nac/output/github-contribution-grid-snake.svg
```

Use alt text `Diego Melo's GitHub contribution snake`.

- [ ] **Step 4: Validate YAML and widget usernames**

Run:

```bash
python3 - <<'PY'
from pathlib import Path
import yaml

workflow = yaml.safe_load(Path('.github/workflows/snake.yml').read_text())
assert workflow['permissions']['contents'] == 'write'
job = workflow['jobs']['generate']
assert job['timeout-minutes'] == 10
readme = Path('README.md').read_text()
assert 'github_user_name: diego-nac' in Path('.github/workflows/snake.yml').read_text()
assert readme.count('diego-nac') >= 10
assert 'diego-melo' not in readme.lower()
print('dynamic feature checks passed')
PY
```

Expected: `dynamic feature checks passed`. If PyYAML is absent, run `ruby -e "require 'yaml'; YAML.load_file('.github/workflows/snake.yml'); puts 'yaml parsed'"` and separately run the README assertions.

- [ ] **Step 5: Check all remote assets and repository links**

Extract HTTPS URLs from `README.md`, request each with redirects enabled and a browser user agent, and report failures:

```bash
python3 - <<'PY'
import re, subprocess
from pathlib import Path

urls = sorted(set(re.findall(r'https://[^\s)\]"<>]+', Path('README.md').read_text())))
failures = []
for url in urls:
    result = subprocess.run(
        ['curl', '-L', '-A', 'Mozilla/5.0', '-sS', '-o', '/dev/null', '-w', '%{http_code}', url],
        text=True, capture_output=True
    )
    code = result.stdout[-3:]
    if code not in {'200', '301', '302', '307', '308'}:
        failures.append((code, url))
print(f'checked {len(urls)} URLs')
assert not failures, failures
PY
```

Expected: `checked <N> URLs` with no assertion. The two raw snake URLs may return 404 before the first workflow run; record them as the only permitted pre-publication exception and recheck after dispatch.

- [ ] **Step 6: Review and commit dynamic functionality**

Run `git diff --check && git status --short && git diff -- README.md .github/workflows`, then commit:

```bash
git add README.md .github/workflows
git commit -m "feat: add dynamic profile visuals"
```

Expected: a commit containing the dynamic README additions and one canonical snake workflow.

---

### Task 3: Publication and Public Verification

**Files:**
- Verify: `README.md`
- Verify: `.github/workflows/snake.yml`
- Verify: public profile `https://github.com/diego-nac`

**Interfaces:**
- Consumes: locally verified commits from Tasks 1 and 2.
- Produces: updated `main`, a successful snake workflow run, populated `output` assets, and a publicly verified profile.

- [ ] **Step 1: Run the full local release gate**

Run:

```bash
git diff --check
git status --short
git log --oneline -5
rg -n 'diego-melo|Diego-Melo|diegomelo624|\+55 85|98832-4122|TBD|TODO' README.md .github/workflows
```

Expected: clean diff check, only the intentionally committed plan may be ahead of `origin/main`, expected implementation commits are present, and the search returns no matches.

- [ ] **Step 2: Authenticate GitHub CLI without persisting secrets in the repository**

Run `gh auth status`. If unauthenticated, run `gh auth login --web --git-protocol https`, let Diego complete the browser/device authorization, then rerun `gh auth status`.

Expected: authenticated to `github.com` as `diego-nac` with repository and workflow access.

- [ ] **Step 3: Push the approved commits**

Run:

```bash
git push origin main
```

Expected: `main -> main` and no non-fast-forward or permission error.

- [ ] **Step 4: Trigger and monitor the snake workflow**

Run:

```bash
gh workflow run snake.yml --repo diego-nac/diego-nac
gh run list --repo diego-nac/diego-nac --workflow snake.yml --limit 1
```

Capture the run ID, then run `gh run watch <run-id> --repo diego-nac/diego-nac --exit-status`.

Expected: workflow conclusion `success` and the `output` branch contains both SVG files.

- [ ] **Step 5: Verify the public result**

Run:

```bash
curl -fsSL https://raw.githubusercontent.com/diego-nac/diego-nac/main/README.md | rg 'Data Analyst|Data Engineer|semantic_search_v2|GraphRAG'
curl -fsSI https://raw.githubusercontent.com/diego-nac/diego-nac/output/github-contribution-grid-snake.svg
curl -fsSI https://raw.githubusercontent.com/diego-nac/diego-nac/output/github-contribution-grid-snake-dark.svg
```

Expected: all four README terms appear and both SVG requests return HTTP 200. Open `https://github.com/diego-nac` and inspect hero, cards, details blocks, and light/dark snake rendering.

- [ ] **Step 6: Report exact publication evidence**

Provide the pushed commit IDs, workflow run URL/conclusion, public profile URL, verification commands and outcomes, and any third-party widget that remains temporarily unavailable. Do not claim completion if the push, workflow, assets, or public rendering has not been verified.
