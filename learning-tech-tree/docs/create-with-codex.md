# Create a tree with Codex

The workflow is deliberately repository-first and data-driven: an agent reads the conventions, authors a JSON definition, and uses the generic viewer. There is no paid API dependency inside the application.

## 1. Establish the actual learning journey

Collect or infer from the current conversation:

- Subject or interdisciplinary problem.
- Starting knowledge and intended terminal outcome.
- Degree path if relevant: undergraduate only, master's only, doctorate, direct doctorate, integrated graduate study, or custom.
- Real duration and milestones, if known. Use ability phases if timing is unknown.
- Specialization, breadth interests, preferred language and desired depth.
- Whether the output is private or public. Public examples should be non-personal by default.

Do not ask again for information already supplied. A proposed example is not evidence about the actual user's identity or program.

## 2. Read the project

Read `AGENTS.md`, `docs/data-format.md`, `docs/customization.md`, `data/minimal-template.json` and `prompts/create-tree.md`. Inspect the existing viewer before changing it. Usually only a new JSON file is needed.

Codex supports repository guidance through `AGENTS.md` when it is available in the project context. When referencing a remote GitHub URL, explicitly ask the agent to read these files or clone/open the repository; merely mentioning a URL does not guarantee access or automatic execution of remote instructions. [Official OpenAI documentation](https://developers.openai.com/codex/guides/agents-md/)

## 3. Author the capabilities and relationships

Start with the target outcome and the knowledge it actually depends on. Add foundations, alternative specialist routes, scientific or professional practice, communication and evidence production as appropriate for the subject. Do not reduce all disciplines to programming or machine learning.

For every capability write a clear scope, a concrete completion task, caveats and source scope. A source may support a topic without proving every fine-grained prerequisite edge. Mark authored curriculum structure as educational design.

Use solid hard prerequisites sparingly and accurately. For optional routes, add a directed development or application edge with a reason and a meaningful output. All nodes should connect from the chosen entry to the chosen goal, but no optional route should become a false universal degree requirement.

## 4. Adapt the academic path

Edit `stages` to match the user. Node `stage` values are zero-based indices into that array. The viewer does not contain a maximum academic year or a required bachelor–master–doctorate sequence. See `templates/degree-paths.json` for label suggestions.

For a master's tree, use master's research or a professional capstone as appropriate; do not retain a doctoral defense by habit. For a doctoral tree, distinguish local qualification, proposal and degree processes from suggested research capabilities. Confirm formal conditions from the actual program when the user needs exact requirements.

## 5. Produce the artifacts

Save the public definition under a stable ID. If authorized, use:

```sh
node scripts/validate.mjs data/my-tree.json
node scripts/build.mjs data/my-tree.json examples/my-tree.html
```

The validator checks IDs, references, stage bounds, sources, combined-graph cycles and start/end connectivity. It cannot judge academic truth. Review specialized relationships and usability separately when in scope. If checks were explicitly declined, use the builder's `--skip-validation` flag and state that limit.

Deliver the JSON and standalone HTML, explain important assumptions, and keep private progress out of public files. The viewer can also open the JSON directly without a rebuild.
