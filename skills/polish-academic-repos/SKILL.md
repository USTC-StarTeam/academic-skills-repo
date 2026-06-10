---
name: polish-academic-repos
description: Use when improving or publishing an academic-paper code repository, README, docs site, project/about metadata, citation metadata, official conference/project links, paper figures, experiment summaries, contact info, or hosted release page across GitHub, GitLab, Hugging Face, Zenodo, OSF, or similar platforms.
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
   - Extract title, all authors, first-author or co-first-author markers, corresponding-author markers, venue, year, arXiv/DOI/official links, affiliations, citation, contact emails, method figure, main tables, ablations, efficiency, robustness, and limitations.
   - Render the PDF visually before cropping figures. Do not rely only on text extraction for diagrams and tables.
   - Verify current paper metadata from primary sources when it may have changed.

3. **Verify official publication sources**
   - Search for authoritative public pages for the paper: conference virtual/poster/oral page, proceedings page, OpenReview, arXiv, DOI/publisher page, official project page, lab page, dataset/model card, SlidesLive/YouTube/Bilibili video, and official slide/poster/PPT assets.
   - Prefer the most official and current source for title, author order, venue, date, location, abstract, acceptance type, citation, and contact. Correct stale README claims when a conference page, proceedings page, or OpenReview entry supersedes older preprint metadata.
   - Capture presentation materials when available: `Paper`, `PDF`, `OpenReview`, `Project Page`, `Slides` or `PPT`, `Video`, `Poster`, `Code`, `Dataset`, and `Citation`.
   - Add these links to the Paper section and project page in a compact link line or short materials list. Do not bury them only in hero buttons or repository topics.
   - Check that every official link resolves before publishing, and note uncertainty when a conference page has not yet posted proceedings, slides, or video.

4. **Design the public story**
   - Lead with what the paper is, why the repository matters, where to read it, and how to cite it.
   - Put installation, data, quick start, and reproduction instructions before long experiment galleries.
   - Put experimental highlights after runnable-code sections so the repository still feels usable by developers.

5. **Implement README or docs structure**
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
   - Write the Paper section as a three-part introduction, not a bulky metadata table, unless a table is clearer for the audience:
     - reference-style paper entry with authors, bold title, venue, location or proceedings details, and year
     - separate link line such as `Paper / PDF / OpenReview / Project Page / Citation`
     - one short paragraph explaining what the paper contributes and how the repository supports it
   - When official presentation assets exist, add `Slides`, `PPT`, `Video`, or `Poster` to the link line or a short `Conference materials` list under `1. Paper`.
   - Write the Contact section in role order:
     - first author first; if the paper marks equal contribution or co-first authors, include every co-first author in paper order
     - corresponding author or authors after the first/co-first authors, using the paper's correspondence footnotes or official metadata
     - repository issue/contact instructions last
   - Use verified emails from the paper, official conference page, OpenReview, author homepage, or organization profile. Do not invent a missing email; list the verified name and note that no public email was found if needed.
   - Preserve anchors when headings change, for example add an explicit citation anchor before a numbered citation heading.
   - Keep commands runnable and aligned with existing scripts.

6. **Set repository About metadata**
   - Do not leave host-level About fields empty when the platform supports them.
   - Use a concise description in the style `Venue Year | Project or paper name: short research contribution.` Keep it readable in repository cards and search results.
   - Set the homepage/website to the best public landing page: live project page first, then official conference/project page, OpenReview, DOI, arXiv, or README anchor.
   - When a project page is created, point About homepage to the live page URL and place arXiv/DOI/OpenReview links inside the Paper section instead of using them as the primary homepage.
   - Add 5-8 lowercase topics that cover the task, method, domain, venue, and project name, for example `recommendation-system`, `sequential-recommendation`, `icml-2025`, `benchmark`, or the paper acronym.
   - Verify the remote About metadata after publishing through the repository host UI/API/CLI.

7. **Add method and result assets**
   - Crop the framework figure tightly: include the diagram itself, not neighboring body text, captions, related work, or page headers.
   - Save assets under a stable project path such as `docs/assets/`, `assets/figures/`, `website/static/`, or the existing equivalent.
   - Use descriptive names such as `method-overview.png`, `main-results.png`, `ablation.png`, `efficiency.png`, or `robustness.png`.
   - Visually inspect every crop and include alt text or captions that state the takeaway.

8. **Summarize experimental highlights**
   - Prefer compact Markdown summaries over wide full-paper tables.
   - Include only figures that support clear conclusions: main gains, iteration curves, ablations, generated-data quality, efficiency, robustness, or qualitative examples.
   - State one conclusion after each result block, and avoid claims stronger than the paper supports.

9. **Build or update the public page**
   - Use the existing page stack when present. Common options include README-only, static `docs/index.html`, MkDocs, Jekyll, Docusaurus, Sphinx/ReadTheDocs, GitHub Pages, GitLab Pages, Hugging Face Spaces, or an institutional static site.
   - Treat the project page as the hosted public version of the README, not a short abstract. Represent every public-facing README section: paper identity, official links/materials, highlights, method/results figures, repository structure, installation, data/models, quick start, reproduction/evaluation, configuration notes, experimental highlights, citation, and contact.
   - Mirror the README story: hero or header with paper identity, method section with the framework figure, code/usage section, results section, citation, and contact. Do not stop at only hero, method, a few result cards, and citation when the README contains more runnable or reproducibility content.
   - Put project-page contact information in the same order as the README: first/co-first authors, then corresponding authors.
   - Keep the same paper-introduction hierarchy on the project page: reference-style entry, compact paper links, official presentation/material links, then one contribution paragraph. Avoid burying paper links only in hero buttons.
   - When the page lives under a hosted subdirectory such as `docs/`, rewrite or copy README-local assets so images, PDFs, posters, slides, and repository files resolve from the hosted page. Root-only paths like `fig/...` or `assets/...` may need to move into `docs/assets/` or become repository-host links.
   - Test desktop and narrow mobile widths. Avoid tables, code blocks, and images that force horizontal scrolling.

10. **Publish or hand off safely**
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
- README/project-page parity check: every public-facing README section appears on the project page, or an intentional short summary links to the full README for very long maintainer-only or catalog content
- official-source link check for conference/proceedings pages, OpenReview, arXiv/DOI, project page, slides/PPT, video, and poster assets
- contact-order check: first/co-first authors appear before corresponding authors, all role labels match the paper's author notes, and every email is verified or explicitly omitted
- hosted asset-path check for static pages: local `src` and `href` targets resolve from the page directory, not only from the repository root
- remote file, raw asset, and hosted page checks after publishing
- repository About metadata check: description, homepage/website, and topics
- CI/docs/deploy status check when the host provides one
- final clean VCS status or an explicit patch summary

## Common Mistakes

- Assuming a host- or agent-specific workflow when the same repository story should work across different tools and platforms.
- Putting experiments before installation and quick start, which makes the repository feel like a paper PDF rather than runnable code.
- Leaving paper metadata in a large table when a reference-style entry plus links and a short contribution paragraph is clearer.
- Trusting stale README or preprint metadata without checking official conference, proceedings, OpenReview, DOI, project, slides, video, and poster pages.
- Listing only corresponding authors in Contact and omitting the first author or co-first authors.
- Guessing author emails from name patterns instead of verifying them from the paper or official profiles.
- Cropping method figures with surrounding paper text, related work, captions, or page headers.
- Creating a project page that only summarizes the paper and omits README sections for install, data, quick start, reproduction, configuration, notes, citation, or contact.
- Linking README-local root assets from a hosted subdirectory without copying them into the served assets folder or converting them to repository-host links.
- Breaking README anchors after numbering headings.
- Leaving repository About description, homepage, or topics empty after polishing the README.
- Adding wide tables or single-line code blocks that overflow on mobile.
- Publishing a project page link before the hosted docs build is live.
