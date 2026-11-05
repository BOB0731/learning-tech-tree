# Learning Tech Tree

**Turn a learning journey into a technology tree—with foundations to trace, capabilities to develop, and a goal to work toward.**

Learning Tech Tree is a browser-based viewer, a reusable data format, and a set of Codex authoring guides for creating interactive learning maps. It supports different subjects, starting points, degree paths, and learning goals through editable JSON rather than a fixed curriculum.

**Current version: 0.1.1** · **License: MIT** · **No backend or API key required**

[中文说明](docs/README.zh-CN.md) · [Create a tree with Codex](docs/create-with-codex.md) · [Data format](docs/data-format.md) · [Customization](docs/customization.md) · [Release notes](docs/release-notes.md)

## Why a learning tech tree?

When studying a complex subject, it is easy to collect courses, books, papers, and tools without seeing how they fit together. A useful learning map should explain more than what to study:

- Where does a capability come from?
- Which foundations does it genuinely require?
- Which related topics are helpful but optional?
- What task can demonstrate understanding?
- What can this capability support next?
- How does it contribute to the larger goal?

Inspired by technology trees in strategy and automation games, this project represents capabilities as nodes and their relationships as directed connections. The result is a map that can be explored, questioned, revised, and used to record learning progress.

The subject content is authored separately from the viewer. The same interface can display a focused self-study project, a professional skill pathway, an undergraduate curriculum, or a journey toward independent research.

## Who can use it?

| Learner or author | Possible use |
|---|---|
| Undergraduate students | Connect foundations, disciplinary knowledge, specialist options, and capstone work |
| Master's students | Organize bridge knowledge, advanced topics, research methods, and thesis or professional-project outcomes |
| Doctoral students | Trace theoretical and methodological dependencies, build research evidence, and plan dissertation milestones |
| Independent learners | Define an entry point, explore alternative routes, and work toward a concrete personal goal |
| Researchers entering a new area | Identify unfamiliar foundations and select methods appropriate to a specific problem |
| Teachers and mentors | Explain a subject's structure and define observable learning outcomes |
| Codex users | Generate a new subject-specific tree using an existing viewer, schema, and authoring workflow |

Subjects may include sciences, engineering, humanities, arts, professional practice, and interdisciplinary fields. Each tree needs content and methods appropriate to its own subject; the included computer-science example is one illustration.

## Quick start

### Open the included viewer

1. Download and extract the repository.
2. Open **`index.html`** in a modern browser.
3. Explore the example, select a node, and inspect its learning scope and completion task.

The generated HTML files contain the viewer and their example data. Opening them locally requires no package installation, account, server, or model API key. Internet access is only needed when you choose to visit external sources or access an online-hosted copy.

### Choose an example

- **[Computer-science doctoral example](examples/computer-science-phd.html):** a broad learning and research map with 155 nodes across 14 branches.
- **[Minimal customizable example](examples/minimal-template.html):** a four-node starting structure for creating a different subject or goal.
- **[Computer-science JSON](data/computer-science-phd.json)** and **[minimal JSON](data/minimal-template.json):** editable source definitions.

GitHub's repository file view displays HTML as source. To run the viewer, open a downloaded HTML file locally or visit your published GitHub Pages site.

### Open a custom tree

Select **打开科技树 / Open tree** in the viewer and choose a compatible local JSON definition. You can create that definition manually or ask Codex to generate it using this repository's guides.

The current viewer interface and bundled examples use Chinese. Documentation is provided in English and Chinese. Node content, titles, stages, and sources can use other languages; the `language` field is an HTML content-language hint, not an automatic interface translator.

## Features

### Interactive map exploration

- Drag the canvas to pan through a large tree.
- Use the mouse wheel, zoom buttons, or the continuous slider to change scale.
- Navigate with a minimap, stage buttons, branch filters, and node search.
- Select a node to inspect its scope, outcome, prerequisites, applications, sources, and caveats.
- Inspect a target's complete hard-prerequisite closure.
- Display one representative route from the declared start through the selected node to the declared goal.

The layout uses spaced horizontal columns and distributed connection points to give edges more room. Branch headings retain a minimum screen size in the overview and grow as the map is enlarged. Use the overview to understand structure, then zoom or search to read individual nodes.

### Continuous zoom slider — new in 0.1.1

The lower-left control includes a draggable slider covering **2.5%–240%** zoom. Its logarithmic scale makes both a whole-tree overview and close inspection accessible along one control.

- Drag left to zoom out and right to zoom in.
- The displayed percentage updates while dragging.
- Wheel zoom, plus/minus buttons, double-click zoom, fit-to-view, and navigation update the same slider state.
- Slider zoom is anchored at the center of the visible canvas.
- With the slider focused, use arrow keys to adjust it or **Home / End** to reach its minimum or maximum.

### Progress and learning evidence

Mark capabilities as understood and add private notes about exercises, proofs, experiments, implementations, readings, or unresolved questions. Progress is a self-assessment: the application does not certify mastery or determine academic eligibility.

Each tree has its own stable ID and browser-storage record. Export and restore progress separately from the public tree definition. Marking an advanced node does not automatically complete its prerequisites, and undoing one self-assessment does not erase other records.

## Relationship semantics

The graph distinguishes required foundations from optional learning and applications.

| Relationship | Display | Meaning | Participates in prerequisite locking? |
|---|---|---|---|
| Hard prerequisite | Solid directed edge | Required knowledge for the target node's stated scope | Yes |
| Learning development | Dashed directed edge | A meaningful continuation into another capability | No |
| Application or contribution | Dashed directed edge | A capability can support a particular use or deliverable | No |
| Related background | Link in the detail panel | Helpful context or supplementary knowledge | No |

Multiple hard prerequisites mean **AND**. Several optional applications can represent alternative routes; they do not mean every method is compulsory.

Every node should have a meaningful route from the tree's declared entry and onward to its goal. A specialist branch can end in a concrete contribution—a proof, design, analysis, measurement, implementation, or other work product—and connect that contribution to the larger outcome.

Connections should express real educational or practical meaning. Do not invent a prerequisite merely to make the map connected. The combined solid-and-dashed graph must remain acyclic.

The representative-route action shows **one route through a selected node**. It does not replace the full prerequisite closure or imply that this single route satisfies an institution's degree requirements.

## Any subject, any academic path

The viewer does not hard-code a discipline, institution, advisor, degree duration, or graduation year. The tree definition controls:

- Subject and scope.
- Entry knowledge and target outcome.
- Stage names and stage count.
- Branches and their colors.
- Capability nodes and completion tasks.
- Required, recommended, and application relationships.
- Sources and the limits of their evidence.

Stages may represent years, semesters, ability levels, research phases, or other milestones. The same format supports undergraduate-only, master's-only, doctoral, direct-doctoral, integrated graduate, multi-degree, part-time, and custom learning paths.

[Degree-path profiles](templates/degree-paths.json) provide editable label suggestions. They do not prescribe formal course requirements, compulsory degree sequences, or fixed completion times. A separate master's degree is not automatically required in a doctoral tree.

For a master's project, define a master's-appropriate endpoint. For a portfolio, define a portfolio outcome. For a doctorate, distinguish suggested research capabilities from the actual program's qualification, proposal, dissertation, defense, and degree procedures.

## Included computer-science doctoral example

The example contains **155 nodes across 14 branches**, developing from general foundations through undergraduate knowledge, optional master's-level research training, and doctoral research work.

| Branch | Topics represented |
|---|---|
| General foundations | Reading, quantitative reasoning, logic, observation, and digital information |
| Mathematics and statistics | Discrete mathematics, proofs, calculus, linear algebra, probability, statistics, and optimization |
| Programming and research computing | Program structure, debugging, testing, version control, environments, and reproducibility |
| Algorithms and data structures | Complexity, search, trees, graphs, dynamic programming, randomized methods, and approximation |
| Computer systems | Architecture, operating systems, concurrency, distributed systems, and storage |
| Networks | Protocols, transport, routing, measurement, and communication costs |
| Data | Data models, queries, indexes, transactions, data quality, and information retrieval |
| Theory and languages | Automata, computability, complexity, language semantics, and formal reasoning |
| Security and privacy | Threat models, application protection, data minimization, and authorized evaluation |
| Artificial intelligence | Statistical learning, independent evaluation, and selected specialist methods |
| Human–computer interaction | User needs, accessibility, usability, and participant research |
| Graphics and visualization | Geometry, rendering, simulation, and scientific visualization |
| Software engineering | Requirements, architecture, integration, maintenance, teamwork, and capstones |
| Research and academic work | Literature, questions, evidence, contributions, communication, dissertation, and formal completion |

The example allows different forms of research evidence: theoretical arguments, systems measurements, data experiments, human-participant studies, and other appropriate analyses. Specialist branches connect to usable deliverables rather than becoming mandatory for every researcher.

Its stages are capability and research phases, not fixed years. The map is independently authored educational material. It is not an institution-approved curriculum, a complete encyclopedia of computer science, or a guarantee of doctoral completion.

## Create your own tree with Codex

Replace `<REPOSITORY_URL>` with this repository's actual GitHub URL and send Codex the following prompt:

```text
Use <REPOSITORY_URL> as the implementation reference for a Learning Tech Tree.

First read:
- AGENTS.md
- docs/create-with-codex.md
- docs/data-format.md
- docs/customization.md
- prompts/create-tree.md

Subject or interdisciplinary goal: [fill in]
Starting knowledge: [fill in]
Target outcome: [bachelor / master / doctorate / professional goal / other]
Actual academic path: [fill in, or use flexible capability phases]
Duration and milestones: [fill in if known; do not assume fixed years]
Interests or specialization: [fill in]
Preferred language and depth: [fill in]
Publication scope: [public generic example / private personalized tree]

Create a rich, coherent tree with foundations, subject knowledge, appropriate
methods, evidence production, communication, and practical milestones.

For every node, include its scope, an observable completion task, genuine
hard prerequisites, helpful background, caveats, and honest source scope.

Every node must have a meaningful route from the declared start to the goal.
Use solid edges for required prerequisites and dashed edges for optional
development or applications. Do not make every specialization mandatory.
Keep the combined graph acyclic.

Adapt the content and stages to this request. Do not copy the computer-science
example into another field or assume universal degree rules, publication
quotas, or a separate master's degree.

Keep private identities, notes, credentials, and local paths out of public files.
State educational assumptions separately from formal institutional requirements.

Deliver data/<new-stable-id>.json and examples/<new-stable-id>.html using the
existing viewer. Perform checks only within the authorized scope and state
which checks actually ran. Do not publish or push unless requested.
```

Codex needs access to read or clone the repository. A repository URL serves as a reference; the viewer itself does not call Codex or another model. No hosted AI generation service is included.

The repository contains [English](prompts/create-tree.md) and [Chinese](prompts/create-tree.zh-CN.md) prompt templates, a [step-by-step recipe](docs/create-with-codex.md), and `AGENTS.md` guidance for coding agents. You may also author a tree manually without using an AI assistant.

## Data-driven customization

Public definitions use the **`learning-tech-tree/v1`** format. Start with [the minimal template](data/minimal-template.json), then edit the fields relevant to your journey.

| Field | Purpose |
|---|---|
| `id` | Stable tree identity used to separate progress records |
| `title`, `subtitle`, `description` | Public presentation of the journey |
| `education` | Optional descriptive path, duration, and note |
| `stages` | Any nonempty ordered list of stage labels |
| `branches` | Subject-appropriate tracks, labels, and colors |
| `nodes` | Capabilities, scope, outcomes, relationships, caveats, and source references |
| `applicationEdges` | Directed non-gating development or application relationships with reasons |
| `startId`, `endId` | Declared entry and target nodes |

Each node uses a zero-based stage index. Stages and branches must exist in the same definition. The current viewer supports **2–2500 nodes per tree**.

Keep tree and node IDs stable when retaining their meaning across revisions so progress can continue to match. Use a different tree ID for an unrelated learning journey. Personal notes and completion records belong in progress backups, not public curriculum data.

See [the data-format guide](docs/data-format.md) and [JSON Schema](schema/tree.schema.json) for the complete structure.

## Build and structural validation

**Node.js 20 or newer** is needed only for the authoring scripts. The project has no npm dependencies and requires no installation step to build the bundled pages.

```sh
# Validate the bundled public definitions.
node scripts/validate.mjs

# Validate one custom definition.
node scripts/validate.mjs data/my-tree.json

# Regenerate the bundled standalone pages.
node scripts/build.mjs

# Build a standalone page for a custom tree.
node scripts/build.mjs data/my-tree.json examples/my-tree.html
```

The builder normally validates the definition before generating HTML. The validator checks IDs, references, stage bounds, source references, cycles in the combined graph, and start/end connectivity.

Structural validation does not establish academic accuracy, completeness, appropriate research methods, accessibility, or eligibility for a degree. Review those matters separately and state what was actually reviewed.

If checks are explicitly declined, the builder provides `--skip-validation`; the resulting delivery should disclose that limit. Opening a custom JSON in the browser still applies the viewer's structural input validation before replacing the active tree.

## Publish with GitHub Pages

The generated `index.html` is included in the repository. To publish the supplied viewer:

1. Upload or commit the project files with **`index.html` at the repository root**.
2. Include the `src`, `data`, `examples`, `docs`, `prompts`, `schema`, `scripts`, and `templates` directories, along with the root project files.
3. In GitHub, open **Settings → Pages**.
4. Choose **Deploy from a branch**, select the intended branch and **`/ (root)`**, and save.
5. Use the actual site URL reported by GitHub after deployment.

The bundled standalone pages need no build workflow to be served. Rebuild generated HTML after changing viewer source or bundled data. See [the publishing guide](docs/publish.md) and [official GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

## Privacy and local storage

The public examples are independently authored, non-personal educational material. They do not include an actual learner's identity, advisor, private academic history, notes, progress, credentials, or machine-specific paths.

- Tree JSON is embedded in the page or read from a local file you select.
- The application has no backend, account system, telemetry code, or model API call.
- Progress and notes are saved in the current browser, separately for each tree ID.
- Exporting a tree definition is separate from exporting private progress.
- The application does not upload notes or progress to GitHub.

Browser storage is not encrypted or an automatic backup. Other software or pages sharing the same origin may be able to access it. Clearing data, changing browser profiles, moving to another device, or switching between local and hosted origins can affect access to saved progress. Export a backup before making these changes.

External source links and hosting providers have their own privacy and logging behavior. Do not place credentials, confidential research, or other sensitive information in learning notes. Keep progress backups out of public repositories. See [privacy.md](docs/privacy.md).

## Frequently asked questions

### Is the project limited to computer science or doctoral study?

No. Both the subject and academic path are defined by data. Use an appropriate entry, stages, methods, and endpoint for the actual request.

### Can I start from my current knowledge instead of early education?

Yes. Define the starting point around the learner's existing background. A tree does not need to reproduce every previous year of schooling.

### Must I complete all specialist branches?

No. Optional branches can describe alternatives. Dashed application edges show how selected capabilities can contribute without making all methods prerequisites for the goal.

### Does marking a node prove mastery or satisfy a degree requirement?

No. Progress is a personal record. Observable outcomes help make self-assessment concrete, while formal certification and degree decisions remain with the relevant institution or body.

### Will notes and progress synchronize between devices?

Not automatically. Export a progress backup and restore it for the matching tree. The tree ID must match, and the browser filters entries using the current node IDs.

### Do I need Node.js or an API subscription to use the viewer?

No. Open an included HTML file or load compatible JSON in the viewer. Node.js is for the optional authoring scripts; using an external AI assistant is a separate choice.

### Can I use English or another language for a tree?

Yes. Public labels and text accept Unicode. The current fixed viewer interface is Chinese; full interface localization has not been implemented.

## Repository structure

```text
learning-tech-tree/
├── index.html                  Standalone viewer with the CS example
├── AGENTS.md                   Repository guidance for coding agents
├── README.md                   Project overview and usage
├── LICENSE                     MIT license
├── package.json                Optional authoring-script commands
├── src/                        Generic viewer source and graph engine
├── data/                       Public tree definitions
├── examples/                   Generated standalone example pages
├── templates/                  Editable degree-path stage profiles
├── schema/                     Tree JSON Schema
├── scripts/                    Build and structural-validation utilities
├── docs/                       Authoring, customization, evidence, privacy, release notes
└── prompts/                    Copyable English and Chinese Codex prompts
```

## Evidence, limitations, and release status

Fine-grained curriculum relationships are educational judgments, even when the underlying topics have authoritative sources. A source may support a concept without establishing every prerequisite edge. Document what was actually read and avoid presenting an independent map as an institution-approved program.

The bundled example's public references and evidence boundaries are described in [evidence.md](docs/evidence.md).

**Version 0.1.1 includes regenerated static pages with the continuous zoom slider. Automated validation, a test suite, and browser QA were not run for this delivery. No successful-validation or visual-verification claim is made.** Maintainers can use the supplied commands and perform appropriate academic and usability review before relying on a modified tree.

## Contributing

Contributions can improve subject examples, relationship accuracy, source evidence, documentation, accessibility, or the viewer itself.

For a proposed curriculum correction, identify the relevant node IDs, explain the relationship that should change, and provide a suitable primary source or a narrower scope for the target capability. Keep optional applications separate from required foundations.

Use non-personal public examples, respect third-party rights, and preserve stable IDs when their meaning is retained. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License and acknowledgments

Project code and original example content are available under the **[MIT License](LICENSE)**. Linked papers, standards, websites, and other third-party materials retain their respective rights.

The project draws inspiration from game technology trees, including *Dyson Sphere Program* and *Factorio*. It is an independent educational project, without affiliation with or endorsement by the games' developers. Game names and assets retain their respective ownership.

The viewer and graph engine are independently authored. No third-party skill-tree implementation is bundled.
