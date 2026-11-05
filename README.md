[README.md](https://github.com/user-attachments/files/34417073/README.md)
# Learning Tech Tree

Turn any learning journey into an interactive tech tree. Map prerequisites, explore connections, and track progress across any subject, skill, or educational path.

[中文说明](docs/README.zh-CN.md) · [Create a tree with Codex](docs/create-with-codex.md) · [Data format](docs/data-format.md) · [Customize stages](docs/customization.md)

## Why a learning tech tree?

A course list tells you what exists. A learning tree helps you understand what connects: where a topic comes from, which foundations it genuinely needs, what you can do with it, and how it contributes to a larger goal.

Learning Tech Tree takes inspiration from technology trees in strategy and automation games. Instead of unlocking buildings or machines, you develop capabilities: understanding a concept, completing a proof, building an artifact, running an experiment, or producing a piece of research evidence.

The aim is to make a complex journey navigable while keeping its meaning accurate. Different fields need different methods, and different learners follow different programs. The project provides a reusable viewer and authoring format rather than one universal curriculum.

### Who is it for?

- **Students** planning undergraduate, master's, doctoral, integrated, or direct-doctoral study.
- **Independent learners** connecting foundations to a practical or intellectual goal.
- **Researchers** mapping unfamiliar methods, theoretical dependencies, and evidence-production skills.
- **Teachers and mentors** preparing a visual roadmap with explicit learning outcomes.
- **People using Codex** who want a reusable reference for generating a personalized tree without rebuilding the interface for every subject.

You can map a whole educational journey or a bounded topic. A tree can end at a degree-related milestone, a portfolio, a research contribution, a professional project, or another concrete outcome.

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

### Interaction guide

| Action | How to use it |
|---|---|
| Explore the map | Drag an empty area to pan; use the mouse wheel or zoom buttons to change scale |
| Navigate a large tree | Use the minimap, stage buttons, branch filters, or search |
| Inspect a capability | Select a node to read its scope, outcome, sources, and limitations |
| Find missing foundations | Select a node and use the prerequisite-path action |
| Understand its larger purpose | Open the start → selected node → goal representative route |
| Record understanding | Mark a node as understood and add private evidence or learning notes |
| Load another subject | Use the example selector or open a compatible local JSON definition |
| Save the curriculum | Export the tree definition; personal progress is a separate export |
| Back up learning records | Export progress before changing browser, origin, device, or storage |

Press `/` to focus search. Use `+` and `-` to zoom when you are not editing a text field. `Escape` clears the active route or branch focus when appropriate.

The map uses spacious horizontal columns and distributed connection points to reduce overlapping lines. Branch headings grow when zoomed in and retain a minimum readable screen size in the overview. For very large maps, use the overview for structure and zoom in or search to read individual nodes.

### Every node should answer useful questions

1. **What does this capability include?** A defined scope, not only a course title.
2. **What do I really need first?** Explicit hard prerequisites for that scope.
3. **What background may help?** Non-gating related knowledge.
4. **How can I demonstrate understanding?** An observable task or artifact.
5. **Where can I use it next?** A meaningful continuation or application.
6. **What supports the content?** Sources and an honest account of their evidential scope.
7. **What are its limits?** Assumptions, caveats, and conditions that should not be generalized.

An outcome can be a proof, essay, analysis, design, experiment, implementation, observation record, or another form appropriate to the subject. Programming is not the default outcome for every discipline.

## Any subject, any program

The viewer has no hard-coded discipline, institution, advisor, degree length or graduation year. Change `stages`, `branches`, `startId`, `endId` and the content in JSON. A stage may mean a year, semester, ability phase, research milestone or self-study level.

Bachelor's, master's, doctoral, direct-doctoral, integrated graduate and custom paths are supported by the same format. [Degree-path profiles](templates/degree-paths.json) are editable starting labels, not official curriculum rules. A separate master's degree is not universally required for a doctoral tree.

Every node should have a meaningful route from the declared start and onward to the declared goal. When a specialist skill is optional, connect its actual application or deliverable with a **dashed edge**. Do not invent a hard prerequisite just to make the diagram connected.

### Relationship semantics

| Relationship | Meaning | Locks a node? |
|---|---|---|
| Solid prerequisite edge | Knowledge genuinely required for the target node's stated scope | Yes, when assessing whether its direct prerequisites are ready |
| Dashed development edge | A meaningful progression from an earlier capability into another area | No |
| Dashed application edge | A capability can support a specific use, deliverable, or larger contribution | No |
| Related-background link | Helpful context listed in the detail panel | No |

Multiple hard prerequisites mean **AND**. A set of dashed applications can describe alternatives; it does not mean all methods must be learned.

Progress is a self-assessment. You may mark familiar advanced knowledge directly without filling in every earlier record. The application does not automatically mark its prerequisites as completed, and undoing one self-assessment does not erase others.

The combined solid-and-dashed graph is intended to be acyclic, with a declared entry and goal. The representative-route action shows one route through the selected node; it is not a complete list of every prerequisite or a guarantee that following that one route is sufficient for a degree.

## Included computer-science doctoral example

The bundled example contains **155 nodes across 14 branches**. It begins with general foundations and develops toward an original doctoral research contribution and the applicable formal completion process.

| Branch | Example topics |
|---|---|
| General foundations | Reading, quantitative reasoning, observation, logic, and digital information |
| Mathematics and statistics | Discrete mathematics, proofs, calculus, linear algebra, probability, statistics, and optimization |
| Programming and research computing | Program structure, debugging, testing, version control, environments, and reproducibility |
| Algorithms and data structures | Complexity, trees, graphs, dynamic programming, randomized methods, and approximation |
| Computer systems | Architecture, operating systems, concurrency, distributed systems, and storage |
| Networks | Protocols, transport, routing, network measurement, and communication costs |
| Data | Data models, queries, indexes, transactions, data quality, and information retrieval |
| Theory and languages | Automata, computability, complexity, programming languages, and formal reasoning |
| Security and privacy | Threat models, application protection, data minimization, and authorized evaluation |
| Artificial intelligence | Statistical learning, evaluation, neural networks, and selected specialist directions |
| Human–computer interaction | User needs, interaction, accessibility, usability, and participant research |
| Graphics and visualization | Geometry, rendering, simulation, and scientific visualization |
| Software engineering | Requirements, architecture, integration, maintenance, teamwork, and capstones |
| Research and academic work | Literature, research questions, evidence, original contributions, communication, dissertation, and completion |

Specialist routes connect to concrete deliverables. They are not all compulsory for every doctoral researcher. The example permits different kinds of evidence, including theoretical arguments, systems measurements, data experiments, and human-participant studies.

Its stages describe **capability and research phases**, not fixed years. Master's-level research training is included as an optional route; a separate master's degree is not treated as a universal prerequisite for doctoral study. Formal degree rules must come from the learner's actual institution and program.

This example demonstrates the format. It is not intended to become the template content for every other discipline.

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

### What Codex should produce

For a new subject, the expected deliverables are:

1. A public or private tree definition, according to the requested publication scope.
2. A standalone HTML page built with the existing generic viewer.
3. Explicit assumptions about starting knowledge, stages, and the target outcome.
4. Sources with clear distinctions between verified material and educational design.
5. A statement of which structural, academic, or visual checks were actually performed.

The repository includes English and Chinese [prompt templates](prompts/). `AGENTS.md` gives coding agents a concise set of project conventions; the longer authoring recipe lives in `docs/`.

You can also create or edit a definition manually. Codex is an optional authoring aid, not a requirement for using the viewer.

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

### What to change for a new tree

| Field | What you customize |
|---|---|
| `id` | A stable identity for this tree and its progress records |
| `title`, `subtitle`, `description` | The public explanation of the learning journey |
| `education` | Optional description of the actual program or custom path |
| `stages` | Any number of relevant phase, semester, year, or milestone labels |
| `branches` | Subject-appropriate tracks and their colors |
| `nodes` | Capabilities, outcomes, prerequisites, related background, sources, and caveats |
| `applicationEdges` | Non-gating development and application connections with reasons |
| `startId`, `endId` | The declared entry and target outcome |

Keep IDs stable when revising an existing tree so the browser can match prior progress. Use a new tree ID for an unrelated learning journey. Do not add personal learning notes or completion records to public definition files.

The current viewer accepts **2–2500 nodes per tree**. Its validator checks IDs, references, stage bounds, evidence references, cycles in the combined graph, and start/end connectivity. These are structural checks; they do not establish that a subject's prerequisites are academically correct.

## Publish to GitHub Pages

The generated `index.html` is already included. Upload the **contents of this repository directory**, with `index.html` at the repository root. In the repository's **Settings → Pages**, choose deployment from a branch, select the intended branch and `/ (root)`, then save. No build workflow is required for these standalone files. [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

Use the literal URL reported by GitHub after deployment. This package has not created a repository or deployed a site on your behalf.

If opening `index.html` on the GitHub repository page shows source code, that is expected: the repository file view is not the running website. Use a local downloaded HTML file or the published GitHub Pages URL.

## Privacy, scope and verification status

Public examples are independently authored educational material. No personal learning history, progress, notes, credentials or machine-specific paths are bundled. JSON is read locally, and the application does not send tree contents or notes to a backend. Browser storage is local to the current browser profile and origin; it is not encrypted or an automatic cross-device backup. External source links and the hosting provider have their own privacy behavior. [Privacy details](docs/privacy.md)

Curriculum edges are educational judgments. Graph validation does **not** prove academic prerequisite accuracy, completeness, research suitability or eligibility for a degree. Specific institutions and programs define their own requirements. [Evidence and limitations](docs/evidence.md)

**Initial release status:** the supplied static pages have been generated, but automated validation, tests, and browser QA have not yet been run for this release. The scripts are available for maintainers to use. No successful-validation or visual-verification claim is made. [Release notes](docs/release-notes.md)

## Frequently asked questions

### Is this limited to computer science?

No. Computer science is the included example, not a restriction in the viewer. Other sciences, engineering, humanities, arts, professional skills, and interdisciplinary goals can use the same format. Their content and methods must be authored for the field.

### Can I make a master's-only or undergraduate-only tree?

Yes. Set the stages, content, and endpoint to that actual goal. Do not leave doctoral milestones in a master's tree unless they genuinely belong to the requested path.

### Does the application generate a curriculum automatically?

No. It displays and manages a supplied definition. Codex or another author can create the definition using the repository's guides and schema. The application contains no built-in model call or automatic academic verification.

### Does completing a tree mean I qualify for a degree?

No. The tree records self-assessed capabilities and suggested routes. Institutions, examination boards, supervisors, and professional bodies define their own formal requirements.

### Are my notes uploaded to GitHub?

The application does not upload them. They remain in the current browser unless you export or share them yourself. Keep progress backups out of public repositories.

### Will progress follow me to another browser or device?

Not automatically. Export a progress backup and restore it for the matching tree. Browser storage is scoped to the browser profile and origin, so a local file and a hosted page may not share it.

### Can I use the project without Node.js?

Yes. Open the included HTML, or open a compatible JSON through the viewer. Node.js is only needed for the optional build and structural-validation scripts.

### Can I revise or extend the example?

Yes, under the project's license. Keep node IDs stable when retaining their meaning, explain changed assumptions, and distinguish real prerequisites from optional background and applications.

## Contributing

Contributions can improve the viewer, accessibility, documentation, sources, or subject examples. For a curriculum correction, identify the tree and node IDs, explain the relation that should change, and provide an appropriate primary source or a narrower learning scope.

Please keep examples non-personal, avoid copying copyrighted course material, and do not present an independently authored map as an institution-approved plan. See [CONTRIBUTING.md](CONTRIBUTING.md).

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
