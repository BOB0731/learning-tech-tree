# Repository guidance

This project is a general learning-tech-tree viewer and data format. It is not restricted to a discipline, institution, degree sequence, duration or research method.

## Before creating a tree

Read `docs/create-with-codex.md`, `docs/data-format.md`, `docs/customization.md`, and `prompts/create-tree.md`. Use `data/minimal-template.json` for the structure; use the CS example only as an illustration, never as a compulsory curriculum.

Use the user's stated background and preferences. Ask only for missing facts that materially change the tree; state reasonable assumptions when scope has been delegated. Do not silently assume a separate master's degree, fixed doctoral years, universal course lists, publication quotas, or institutional admission rules.

## Curriculum semantics

- Nodes are capabilities with defined scope and an observable `outcome`.
- `prereqIds` means genuinely required knowledge for that scope; multiple values mean AND.
- `relatedIds` is non-gating background; it is not a prerequisite or a graph-layout edge.
- `applicationEdges` is directed development/application, with a concrete reason. It does not lock progress.
- The combined prerequisite + application graph must be acyclic. Every node must be reachable from `startId` and be able to reach `endId`.
- Connect specialist branches to meaningful use or deliverables. Do not invent connections or make every specialization mandatory merely to close the graph.
- Keep institutional requirements distinct from suggested capabilities. Label unsupported curriculum judgments as educational design.
- Use primary public sources when verifying specialized claims. Do not claim to have read full text when only metadata, abstracts or course outlines were accessed.

## Files and privacy

Create new definitions under `data/<stable-id>.json`. Build `examples/<stable-id>.html`. Keep IDs stable when editing an existing tree so progress can match them.

Do not place real identities, advisors, student identifiers, contact details, credentials, private paths, personal notes, progress backups, unpublished research, or unauthorized documents in public examples. Use a generic fictional or non-personal profile by default. Ask before publishing personal content if the user explicitly requests a personalized public example.

Keep content changes in JSON. Avoid hard-coding a field, degree or duration into `src/app.js`, `src/engine.cjs` or `src/template.html`. Do not embed API credentials or add a hosted model dependency.

## Authoring commands

The project has no npm dependencies. When validation is authorized:

```sh
node scripts/validate.mjs data/<stable-id>.json
node scripts/build.mjs data/<stable-id>.json examples/<stable-id>.html
```

The builder normally validates graph structure. If the user explicitly opts out of checks, respect that choice, build with `--skip-validation`, and disclose the verification limit. Do not treat a structural pass as academic review or browser QA. Do not claim a command passed without having run it.

Only upload, push or deploy when that action is within the user's request. Generating a GitHub-ready package is not itself an instruction to change repository permissions or publish personal content.
