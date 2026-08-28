# Azganoth.Context

`Azganoth.Context` is a small, private, version-controlled description of the personal context that helps AI assistants understand and interact with me well.

It answers one question:

> What stable context would help an AI understand me and make conversations consistently feel good?

It is not a comprehensive biography, a continuously updated personal knowledge base, a project tracker, or an archive of everything I have said. Agent and platform memory can hold temporary or situational context.

## Canonical context

The canonical context is intentionally limited to three human-maintained Markdown files:

```text
context/
├── profile.md
├── interaction.md
└── communication.md
```

| File | Owns |
| --- | --- |
| [`context/profile.md`](context/profile.md) | Durable background, interests, preferences, values, and other stable context that helps an assistant understand me. |
| [`context/interaction.md`](context/interaction.md) | How conversations with me work well: exploration, reasoning, disagreement, useful assistant behavior, failure modes, and sources of friction. This is the most important file. |
| [`context/communication.md`](context/communication.md) | My writing and messaging voice, including language and relationship-dependent registers. |

Add another file only when real use shows that one of these owners has become meaningfully difficult to maintain. A small `examples/` directory may eventually hold carefully curated examples of interactions that worked especially well or badly, but it must never become a conversation archive.

## Maintaining context

- Write for humans first. Prefer concise prose and bullets over schemas or metadata records.
- Treat preferences I state explicitly as authoritative context unless I later change them.
- Use evidence-oriented review mainly when inferring patterns from old conversations.
- Turn inferred patterns into concrete guidance, not personality labels.
- Keep only context that is stable and broadly useful to future interactions.
- Do not record active projects, temporary circumstances, reminders, expiry dates, review schedules, or other ephemeral state.
- Do not add a manifest, observation database, confidence system, ingestion pipeline, or generated hierarchy without demonstrated need.

## Source chats

Old conversations from any assistant or platform may be supplied manually as Markdown files under `sources/inbox/`.

The entire `sources/` directory is ignored by Git. Its contents are private, temporary working material and must never be committed. During a bounded review, move completed chats to `sources/reviewed/` and record a brief result in `sources/review-log.md`. The log exists only to support the final cross-chat audit; it is not canonical context or a permanent provenance record.

Keep reviewed chats only until the current collection has been reviewed and the resulting canonical context has received a final consistency pass. Then delete local copies whose originals are safely recoverable elsewhere. If a chat is the only copy, archive it privately outside this repository instead. Delete the temporary review log when the audit is complete. Ignoring a file prevents Git from tracking it; it does not delete or preserve it.

Finalized context should stand on its own. Do not attach provider names, chat filenames, source IDs, citations, confidence metadata, or processing history to canonical entries. Git history records how the maintained context changes; it is not a provenance database for raw conversations.

See [Mining old chats](docs/mining-chats.md) for lightweight guidance. The goal is useful editorial judgment, not reconstruction of a rigorous historical database.
