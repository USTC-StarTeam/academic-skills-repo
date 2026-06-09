---
name: polish-academic-repos
description: Use when improving or publishing an academic-paper code repository, README, docs site, project page, citation metadata, paper figures, experiment summaries, contact info, or hosted release page across GitHub, GitLab, Hugging Face, Zenodo, OSF, or similar platforms.
---

# Polish Academic Repos

## Overview

Use this as a tool-agnostic workflow for AI coding assistants, repository agents, and agentic IDEs. Turn a paper and its codebase into a clear academic release: paper identity first, method visual next, runnable code before experiment-heavy content, then results, citation, and contact.

## Portability Rules

- Treat tool names as replaceable capabilities: file editor, shell/git, PDF/text extraction, image renderer/cropper, browser or HTTP client, and repository host UI/API/CLI.
- Adapt to the platform in front of you: GitHub, GitLab, Bitbucket, Hugging Face, Zenodo, OSF, institutional pages, or a local-only artifact.
- Use provider-neutral terms: default branch, branch, pull request or merge request, hosted docs, static site, release artifact, file view, raw asset, and deploy status.
- Prefer existing repository conventions, docs frameworks, scripts, citation files, and hosting paths over introducing a new stack.
- If credentials, browser control, PDF tools, or host APIs are unavailable, prepare a clean patch plus exact manual publish/verification steps.

## Core Workflow

1. **Orient the repository**
   - Inspect README, docs/project page, package files, run scripts, configs, data/model layout, citation files, license, release settings, hosting config, and current VCS state.
   - Identify what is public-facing versus maintainer-only, and find the docs pattern: README-only, `docs/`, MkDocs, Jekyll, Docusaurus, Sphinx/ReadTheDocs, static HTML, or platform-specific pages.
   - Avoid changing algorithms, model weights, training behavior, or benchmark logic unless documentation accuracy requires a small fix.

2. **Read the paper**
   - Extract title, all authors, venue, year, arXiv/DOI/official links, affiliations, citation, correspondence, method figure, main tables, ablations, efficiency, robustness, and limitations.
   - Render the PDF visually before cropping figures. Do not rely only on text extraction for diagrams and tables.
   - Verify current paper metadata from primary sources when it may have changed.

3. **Design the public story**
   - Lead with what the paper is, why the repository matters, where to read it, and how to cite it.
   - Put installation, data, quick start, and reproduction instructions before long experiment galleries.
   - Put experimental highlights after runnable-code sections so the repository still feels usable by developers.

4. **Implement README or docs structure**
   - Use a numbered outline unless the project already has a stronger convention:
     - `1. Paper`
     - `2. Highlights`
     - `3. Method At A Glance`
     - `4. Repository Structure`
     - `5. Installation`
     - `6. Data / Models`
     - `7. Quick Start`
     - `8. Reproducing Results / Evaluation`
     - `9. Configuration / Hyperparameters / API Reference`
     - `10. Experimental Highlights`
     - `11. Notes For Maintainers`
     - `12. Citation`
     - `13. Contact`
   - Write the Paper section like a reference entry, not a bulky metadata table, unless a table is clearer for the audience.
   - Preserve anchors when headings change, for example add an explicit citation anchor before a numbered citation heading.
   - Keep commands runnable and aligned with existing scripts.

5. **Add method and result assets**
   - Crop the framework figure tightly: include the diagram itself, not neighboring body text, captions, related work, or page headers.
   - Save assets under a stable project path such as `docs/assets/`, `assets/figures/`, `website/static/`, or the existing equivalent.
   - Use descriptive names such as `method-overview.png`, `main-results.png`, `ablation.png`, `efficiency.png`, or `robustness.png`.
   - Visually inspect every crop and include alt text or captions that state the takeaway.

6. **Summarize experimental highlights**
   - Prefer compact Markdown summaries over wide full-paper tables.
   - Include only figures that support clear conclusions: main gains, iteration curves, ablations, generated-data quality, efficiency, robustness, or qualitative examples.
   - State one conclusion after each result block, and avoid claims stronger than the paper supports.

7. **Build or update the public page**
   - Use the existing page stack when present. Common options include README-only, static `docs/index.html`, MkDocs, Jekyll, Docusaurus, Sphinx/ReadTheDocs, GitHub Pages, GitLab Pages, Hugging Face Spaces, or an institutional static site.
   - Mirror the README story: hero or header with paper identity, method section with the framework figure, code/usage section, results section, citation, and contact.
   - Test desktop and narrow mobile widths. Avoid tables, code blocks, and images that force horizontal scrolling.

8. **Publish or hand off safely**
   - Inspect VCS status and stage only relevant files.
   - Prefer a branch plus PR/MR for nontrivial edits. Directly update the default branch only when the user explicitly requests it or the project workflow permits it.
   - After publishing, verify remote file views, raw/static assets, docs build/deploy status, and the live page when applicable.
   - If publishing is blocked, provide the patch, changed file list, suggested commit message, and manual verification checklist.

## Validation Checklist

Run fresh checks before claiming completion:

- whitespace/diff check, such as `git diff --check`
- relevant compile, test, docs build, or static-site render command
- placeholder scan for `TODO`, `TBD`, `PLACEHOLDER`, `coming soon`, stale local paths, and broken temporary URLs
- image open/size check with a viewer, browser, PIL, ImageMagick, or equivalent
- local link/page check when a project page or docs site exists
- remote file, raw asset, and hosted page checks after publishing
- CI/docs/deploy status check when the host provides one
- final clean VCS status or an explicit patch summary

## Common Mistakes

- Assuming a host- or agent-specific workflow when the same repository story should work across different tools and platforms.
- Putting experiments before installation and quick start, which makes the repository feel like a paper PDF rather than runnable code.
- Leaving paper metadata in a large table when a reference-style sentence is clearer.
- Cropping method figures with surrounding paper text, related work, captions, or page headers.
- Breaking README anchors after numbering headings.
- Adding wide tables or single-line code blocks that overflow on mobile.
- Publishing a project page link before the hosted docs build is live.
