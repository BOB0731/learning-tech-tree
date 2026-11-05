# Learning Tech Tree

Turn any learning journey into an interactive tech tree. Map prerequisites, explore connections, and track progress across any subject, skill, or educational path.

[中文说明](docs/README.zh-CN.md) · [Create a tree with Codex](docs/create-with-codex.md) · [Data format](docs/data-format.md) · [Customize stages](docs/customization.md)

## Start here

Download this repository and open **[index.html](index.html)** in a modern browser. No installation, account, API key, server, or internet connection is needed for the included examples. You can also serve the repository with any static server or GitHub Pages.

- [Computer-science doctoral example](examples/computer-science-phd.html): a broad, independently authored map from early foundations through undergraduate knowledge, optional master's-level training, and doctoral research. It is not tied to a fixed number of years.
- [Minimal customizable example](examples/minimal-template.html): a small starting point for any subject or goal.
- [Computer-science data](data/computer-science-phd.json) · [Minimal data](data/minimal-template.json)

The current viewer interface and examples use Chinese; the public documentation is available in English and Chinese. Tree titles, stages, node text and sources accept Unicode and can be authored in other languages. Complete viewer-interface localization is not implemented.

## What it does

- Zoom and pan a game-inspired canvas; readable branch headings retain a minimum screen size in the overview.
- Follow solid **prerequisite** edges and dashed **development/application** edges. Multiple hard prerequisites mean AND; optional applications do not gate completion.
- Search nodes, focus a branch, inspect all hard prerequisites, or follow one start → selected node → goal route.
- Read a node's scope, observable outcome, related background, sources, continuation and limitations.
- Open your own tree JSON directly in the browser, and export its public definition separately from your progress.
- Save progress and private learning notes per tree ID in the current browser; export and restore a separate progress backup.
- Build a standalone HTML file from a tree definition using the included dependency-free Node scripts.

## Any subject, any program

The viewer has no hard-coded discipline, institution, advisor, degree length or graduation year. Change `stages`, `branches`, `startId`, `endId` and the content in JSON. A stage may mean a year, semester, ability phase, research milestone or self-study level.

Bachelor's, master's, doctoral, direct-doctoral, integrated graduate and custom paths are supported by the same format. [Degree-path profiles](templates/degree-paths.json) are editable starting labels, not official curriculum rules. A separate master's degree is not universally required for a doctoral tree.

Every node should have a meaningful route from the declared start and onward to the declared goal. When a specialist skill is optional, connect its actual application or deliverable with a **dashed edge**. Do not invent a hard prerequisite just to make the diagram connected.

## Ask Codex to create yours

Replace `<REPOSITORY_URL>` with this repository's GitHub URL and send Codex:

```text
Use <REPOSITORY_URL> as the implementation reference for a Learning Tech Tree.
Read AGENTS.md, docs/create-with-codex.md, docs/data-format.md and
prompts/create-tree.md before creating data.

Subject: [your subject or skill]
Starting knowledge: [your current background]
Target: [bachelor / master / doctorate / professional goal / other]
Program and duration: [actual path, flexible phases, or unknown]
Interests: [optional research or career directions]
Language: [preferred language]

Generate a complete tree JSON and a standalone HTML using the repository's
viewer. Include real prerequisites, optional applications, observable outcomes,
sources, and a meaningful route from start to goal for every node.
Do not add personal identities or private records to public files.
State assumptions and distinguish educational design from official requirements.
```

A GitHub link is a reference, not a hosted AI service. Codex needs access to read or clone the repository. The viewer itself does not call Codex or any model. See [the full recipe](docs/create-with-codex.md).

## Edit and build

Node.js 20 or newer is needed only for the authoring scripts. There are no npm dependencies and no installation step.

```sh
# Check bundled or custom definitions; this checks structure, not academic truth.
node scripts/validate.mjs
node scripts/validate.mjs data/my-tree.json

# Regenerate the included standalone pages.
node scripts/build.mjs

# Build your own standalone page.
node scripts/build.mjs data/my-tree.json examples/my-tree.html
```

The browser's **打开科技树 / Open tree** action can load a valid JSON without rebuilding the repository. See [the schema](schema/tree.schema.json) and [data-format guide](docs/data-format.md).

## Publish to GitHub Pages

The generated `index.html` is already included. Upload the **contents of this repository directory**, with `index.html` at the repository root. In the repository's **Settings → Pages**, choose deployment from a branch, select the intended branch and `/ (root)`, then save. No build workflow is required for these standalone files. [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

Use the literal URL reported by GitHub after deployment. This package has not created a repository or deployed a site on your behalf.

## Privacy, scope and verification status

Public examples are independently authored educational material. No personal learning history, progress, notes, credentials or machine-specific paths are bundled. JSON is read locally, and the application does not send tree contents or notes to a backend. Browser storage is local to the current browser profile and origin; it is not encrypted or an automatic cross-device backup. External source links and the hosting provider have their own privacy behavior. [Privacy details](docs/privacy.md)

Curriculum edges are educational judgments. Graph validation does **not** prove academic prerequisite accuracy, completeness, research suitability or eligibility for a degree. Specific institutions and programs define their own requirements. [Evidence and limitations](docs/evidence.md)

**Release status:** this package was generated without executing automated validation, tests or browser QA, in accordance with the commissioning user's instruction. The scripts are supplied so maintainers can run them. No pass or visual-verification claim is made. [Release notes](docs/release-notes.md)

## Repository map

```text
index.html                      ready-to-open viewer + CS example
src/                            independently authored viewer and graph engine
data/                           public tree definitions only
examples/                       generated standalone examples
templates/                      degree-stage profiles
schema/                         documented JSON Schema
scripts/                        dependency-free build and structural validation
docs/                           authoring, privacy, evidence and publishing guides
prompts/                        copyable Codex instructions
AGENTS.md                       repository guidance for coding agents
```

## License and acknowledgments

Project code and original example content are provided under the [MIT License](LICENSE). Source links retain their respective rights; this repository does not relicense linked papers, standards or websites.

Inspired by game technology trees and the idea of mapping learning dependencies. The interface and engine in this repository are independently authored; no third-party skill-tree implementation is bundled. Educational source references are listed inside the example and in [evidence.md](docs/evidence.md).
