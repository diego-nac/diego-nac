# GitHub Profile README Redesign

**Date:** 2026-07-21  
**Profile:** `diego-nac`  
**Audience:** Data Engineering and Data Analytics recruiters, engineering peers, and research collaborators

## Objective

Replace the outdated Full Stack profile with an English-language portfolio that positions Diego Melo primarily as a Data Analyst and Data Engineer. AI systems, RAG, GraphRAG, and information retrieval appear as differentiators without displacing the main data focus.

Every biographical and professional claim must be supported by Diego's 2026 resume, LinkedIn profile, or public GitHub repositories. The README must not expose his phone number, invent business metrics, disclose confidential Maplink projects, or imply production maturity for academic repositories.

## Creative Direction

Use a “Data Platform Command Center” aesthetic: dark, technical, and polished, with cyan, blue, and violet accents. The page should feel dynamic while remaining readable to a recruiter scanning it in under two minutes.

The README will be responsive within GitHub's renderer and use GitHub-Flavored Markdown plus supported HTML. Dynamic images must include descriptive alternative text. Content must remain understandable if a third-party widget fails.

### Personal Octocat

Use Diego's supplied transparent Octocat artwork as the central visual identity in the hero. Copy the source image from `/home/diego-maplink/Downloads/octocat-1784646456476.png` into the repository as `assets/octocat-diego.png` so the profile does not depend on an external image host. Render it centered at 260 pixels wide immediately after the animated headline and before the contact badges, with the alternative text `Diego Melo's personal Octocat working on a laptop`. Preserve the original artwork without cropping, recoloring, or other image edits.

## Content Architecture

1. Animated hero identifying Diego as a Data Analyst and Data Engineer, with Analytics and AI Systems as supporting specialties.
2. Contact badges for LinkedIn, email, GitHub, location, and profile views.
3. Concise professional summary based on the resume and LinkedIn.
4. Current-status panel covering Maplink, the UFC Computer Science MSc, and GraphRAG research.
5. A visual data-flow narrative: Sources → Ingestion → Transformation → Warehousing → Analytics → AI.
6. Technology stack organized by engineering layer rather than a generic icon wall.
7. Professional experience focused on verified responsibilities and technologies.
8. Six featured public repositories with accurate descriptions.
9. A collapsible explorer linking every public repository by category.
10. Dynamic GitHub metrics and contribution visualizations.
11. Education, research, selected certifications, languages, and contact call to action.

## Verified Professional Positioning

- Current role: Data Analyst / Data & Innovation Analyst Jr. at Maplink.
- Core work: data modeling, ELT pipelines, data quality, analytical workflows, BigQuery, Python, SQL, geospatial and operational datasets, data products, and dashboards.
- Supporting AI work: LLM agents, retrieval-augmented systems, embeddings, vector search, and GenAI.
- Education: BSc in Computer Engineering from UFC, completed February 2026; MSc in Computer Science at UFC, March 2026–March 2028.
- Research: GraphRAG and graph-based information retrieval for LLMs.
- Verified external evidence: LinkedIn recommendation describing large-volume BigQuery work, POI/basemap analytics, and a strategic Looker Studio dashboard.
- Languages: Portuguese native, English professional/intermediate working proficiency, and French elementary proficiency. Wording should avoid overstating fluency where the sources differ.

## Repository Strategy

### Featured repositories

1. `semantic_search_v2`: parallel academic search, API/browser source integration, DOI/BibTeX/PDF enrichment, filtering, normalization, and CLI delivery.
2. `systematic_search`: multi-source extraction pipeline, asynchronous processing, standardized JSONL outputs, filters, and DOI extraction.
3. `automatic_learning`: regression, classification, KNN, decision trees, statistics, and analytical notebooks.
4. `ica-homeworks`: real sensor-data EDA, PCA, regression, classification, cross-validation, and technical reports.
5. `smart-room-pubsub`: event-driven sensor architecture using RabbitMQ, gRPC, Flask, and REST.
6. `data-visualization`: interactive analytical visualization using Vega-Lite.

The cards must distinguish tools, academic work, and demonstrations. Repository descriptions must reflect the public contents and must not claim stars, users, production deployment, or performance outcomes that are not documented.

### Complete repository explorer

All 16 public repositories observed on 2026-07-21 will be linked in collapsible groups:

- Data, Analytics & Research: `automatic_learning`, `semantic_search_v2`, `systematic_search`, `ica-homeworks`, `data-visualization`, `reconhecimento-de-padroes`.
- Data-adjacent Systems & Web Foundations: `smart-room-pubsub`, `dist-systems-lab-1`, `login-system`, `estudosLaravel`, `eeepjaa`.
- Profile: `diego-nac`.
- Forks / archived learning references: `brazil-as-100-people`, `teste-momento2-edital-tecnico`, `eeepjaa-1`, `snk`.

## Technology Layers

- Languages and analysis: Python, SQL, JavaScript, Bash, Pandas, NumPy, Matplotlib, Plotly.
- Data platform: BigQuery, PostgreSQL, MySQL, MongoDB, ELT/ETL, data modeling, data quality, governance, distributed computing.
- Cloud and delivery: GCP, Cloud Run, Cloud Functions, Pub/Sub, Vertex AI, Cloud Storage, Docker, Linux, GitHub Actions, CI/CD.
- Analytics: Looker/Looker Studio, Tableau, data visualization, experimentation, operational and product analytics.
- AI and retrieval: machine learning, NLP, LLM agents, LangChain, embeddings, vector search, RAG, GraphRAG, TensorFlow.
- Messaging and automation: RabbitMQ and n8n.

Icons may represent only tools supported by the resume, LinkedIn, or repositories. Concepts without dependable brand icons should use text badges.

## Dynamic Features

- Readme Typing SVG for the headline.
- Shields.io badges and Skill Icons or Devicon assets for technologies.
- One GitHub Readme Stats card generated by `stats-organization/github-readme-stats-action@v2`, using the actively maintained GitHub Stats Extended renderer. Configure it with `show_icons=true`, `include_all_commits=true`, `show=reviews,prs_merged`, `hide_rank=true`, `number_format=long`, and `custom_title=Public GitHub Activity`. The resulting card must consolidate total commits, pull requests, issues, code reviews, merged pull requests, and contributed repositories where the GitHub API provides them. Do not add Top Languages, streak, trophies, an activity graph, a letter grade, or a percentile rank.
- Place a visible caption under the Stats card: `Public GitHub activity — commits, contributions, pull requests, issues and repositories. These numbers represent public activity, not technical proficiency.`
- Contribution snake generated by a GitHub Actions workflow, producing light and dark SVG variants on an `output` branch.
- GitHub-supported `<details>` sections for repository exploration, experience, and credentials.
- Render the six data-flow stages as `<kbd>` elements to create a lightweight interactive-control aesthetic without JavaScript or another remote dependency.

External widget URLs must use the correct `diego-nac` username and HTTPS. The README must not embed tokens or secrets. The snake workflow requires read-only contents access and permission to publish generated assets to the output branch. Actions should be pinned to stable major versions or commit SHAs where practical.

Dynamic presentation must come from purposeful motion, progressive disclosure, responsive composition, and the personal Octocat—not from repeated or vanity-heavy statistics. Keep the animated headline, profile-view badge, layered technology icons, collapsible sections, light/dark contribution snake, and hover/click behavior naturally provided by links and `<details>`.

## Experience Presentation

Experience will be concise rather than reproducing the full resume:

- Maplink, Data & Innovation Analyst Jr. (April 2024–present): data models, ELT, quality monitoring, analytics, BigQuery, Python/SQL, geospatial datasets, data products, and AI/retrieval systems.
- Maplink, IT Intern (April 2022–April 2024): extraction, transformation, visualization, automation, and internal analytical tools.
- Dell Lead, Python trainee/developer scholar (September 2021–January 2022): Python, applied data science, NLP prototypes, and supporting libraries.
- Fix Tecnologia, IT Intern (August–October 2021): JavaScript/PHP institutional site, administration interface, and email automation.

Employer logos will not be hotlinked unless a stable, authorized public asset is available. Plain text and badges are sufficient.

## Education and Credentials

Show the UFC MSc and BSc prominently, followed by the technical degree in Informatics. Display only selected credentials with the strongest relevance:

- NVIDIA Fundamentals of Deep Learning, clearly marked as previously issued rather than implied current if an expiration date is shown.
- Google Maps Tech Credential Exam.
- Google Maps Sales Fundamentals Credential.
- Relevant Python and web-development training may live inside a collapsible section.

## Validation

Before publication:

1. Check every personal claim against the three approved sources.
2. Confirm every repository link and external image URL returns successfully.
3. Validate the Markdown structure and inspect the rendered page where practical.
4. Verify YAML syntax and permissions for the snake workflow.
5. Search for stale usernames, outdated emails, placeholder text, phone numbers, and accidental secrets.
6. Review the final diff, commit locally, then push only after GitHub authentication succeeds.

## Publication

Implementation will update `README.md` and add or replace the snake-generation workflow under `.github/workflows/`. Publication will use Diego's authenticated GitHub account, create an implementation commit, push to `main`, and then verify the rendered public profile and workflow run. Authentication credentials must not be written into the repository or displayed in logs.
