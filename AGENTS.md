# Working in this repo

`Azganoth.Context` is the private canonical description of the stable personal context that helps AI assistants understand and interact with the user well. Keep it small, durable, and human-maintained.

## Boundaries

- Keep personal context in this repository.
- Do not turn this repository into a project tracker, task log, personal database, or store of temporary state. Agent and platform memory can own ephemeral context.

## Canonical files

- `context/profile.md` owns durable background, interests, preferences, values, and other stable personal context.
- `context/interaction.md` owns how conversations work well, including exploration, reasoning, disagreement, useful assistant behavior, failure modes, and friction. Treat it as the most important context file.
- `context/communication.md` owns writing and messaging voice, including language and relationship-dependent registers.

Create additional structure only after real use makes one of these files meaningfully difficult to maintain. An optional `examples/` area may contain small curated examples that illustrate behavior, never conversation archives.

## Editing context

- Optimize every addition for: “What stable context would help an AI understand the user and make conversations consistently feel good?”
- Write readable Markdown for humans. Prefer concise prose and bullets over structured records or machine-oriented metadata.
- Treat explicit general preferences and corrections as authoritative. Preserve any scope the user gives them, and don't promote clearly situational instructions into durable context.
- When inferring patterns from old conversations, distinguish the user's words from assistant-authored claims and quoted third-party material.
- Convert inferred patterns into concrete interaction guidance rather than vague personality labels.
- Look for recurring preferences, corrections, successful interaction patterns, and friction, but allow review to produce no addition.
- Do not generalize a broad rule from one conversation without clear reason.
- Do not add active-project context, temporary circumstances, expiry machinery, manifests, observation databases, confidence/status fields, supersession systems, ingestion pipelines, or permanent review machinery to the tracked repository. The bounded, ignored source-review workspace described below is temporary working state, not part of the product.
- Preserve unrelated user changes and inspect the current worktree before editing.

## Source chat safety

- Raw conversations from any assistant or platform are supplied manually as Markdown under the ignored `sources/inbox/` directory.
- Never commit files from `sources/` or reconstruct whole conversations elsewhere in the repository.
- During a bounded review, move completed chats to `sources/reviewed/` and add a concise entry to the ignored `sources/review-log.md`. Keep only the filename, a brief review comment, and which canonical area changed or that no change was made.
- Retain reviewed chats only until the collection-wide consistency audit is complete. Then delete local copies when the originals remain safely recoverable, or archive sole copies privately outside the repository. Delete the temporary review log after the audit.
- Treat the inbox, reviewed directory, and log as disposable workflow state, not repository content or a permanent provenance system.
- Keep finalized canonical context independent of its source. Do not add provider names, filenames, chat IDs, citations, confidence metadata, or processing history.
- Keep excerpts rare, short, and behaviorally illustrative. Prefer distilled guidance in the canonical context files.
- Do not assume that an assistant's statement about the user is true merely because it appears in an old chat.

## Verification

For documentation changes, run `git diff --check`, inspect the complete diff, and confirm that `sources/` remains ignored. Do not add tooling or structured validation until real repository content requires it.
