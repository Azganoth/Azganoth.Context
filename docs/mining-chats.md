# Mining old chats

Old conversations from any assistant or platform can help improve the small canonical context in `context/`. They are working material, not a corpus to preserve or a historical database to reconstruct.

The useful question is:

> What stable context would help an AI understand me and make conversations consistently feel good?

## Source handling

Chat exports are supplied manually as Markdown files under `sources/inbox/`. The entire `sources/` directory is ignored, and its raw conversations and review notes must never be committed.

Use the following temporary layout while reviewing a bounded collection:

```text
sources/
├── inbox/
├── reviewed/
└── review-log.md
```

Read a chat in full, retain only distilled context in the canonical files, and then move the raw chat from `inbox/` to `reviewed/`. Add one concise log entry containing its filename, a brief review comment, and the canonical area it affected—or that it produced no change. Do not include excerpts, provider or chat IDs, confidence fields, or formal evidence records.

Keep the reviewed chats and log until the whole collection has been reviewed and the canonical result has received a final cross-chat audit. After that audit:

- delete local source copies if the originals remain safely recoverable from their platform, export, or another private archive;
- otherwise move the only copies to private storage outside this repository; and
- delete the temporary review log.

The `sources/` workspace is disposable review state, not part of the repository's product. Its short-lived log helps assess the extraction as a whole without becoming a manifest or provenance database. Git ignoring the directory does not manage the files' lifecycle.

## What to look for

Prioritize material that improves one of the three canonical files:

- `profile.md`: durable background, interests, preferences, values, and stable context useful across conversations;
- `interaction.md`: corrections, reasoning preferences, exploratory style, useful disagreement, successful interaction patterns, assistant behaviors that worked, and recurring friction; and
- `communication.md`: writing voice, message rhythm, language habits, tone, humor, and relationship-dependent registers.

`interaction.md` is usually the highest-value destination. A detailed biography is less useful than clear guidance about how to engage naturally and productively.

## Evidence judgment

Explicit preferences and corrections stated by the user are authoritative context. They do not need repeated supporting conversations before being recorded.

Evidence-oriented judgment matters mainly for inferred patterns. When reviewing old chats:

- distinguish the user's words from assistant-authored claims;
- notice when a prompt quotes another assistant, person, or document instead of expressing the user's own view;
- infer concrete guidance rather than labels such as “curious,” “analytical,” or “likes depth”;
- look for corrections, repeated preferences, sustained engagement, successful conversational moves, and friction;
- consider whether an apparent pattern is specific to the topic or relationship;
- allow a conversation to yield nothing; and
- do not turn one old exchange into a universal rule without a clear reason.

Assistant summaries of the user can suggest something worth checking, but they are not authoritative personal context on their own.

## Lightweight review process

1. Read a small, varied set of chats rather than processing the whole archive at once.
2. Note candidate additions under `profile`, `interaction`, or `communication`.
3. Separate explicit user preferences from patterns inferred by the reviewer.
4. Rewrite each useful candidate as short, concrete guidance.
5. Merge it into the relevant Markdown file, removing repetition and preserving important limits.
6. Discard the candidate when it is temporary, overly specific, weakly supported, or unlikely to improve future conversations.
7. Move the reviewed source to `sources/reviewed/` and add its concise result to `sources/review-log.md`.
8. After the collection-wide audit, remove the reviewed sources and log according to the source-handling rules above.

No permanent manifest, normalized-turn store, observation database, confidence taxonomy, or ingestion pipeline is required. The temporary review log is deliberately minimal and remains inside the ignored `sources/` workspace.

## Source-independent results

Once guidance is finalized in `context/`, it should read as durable personal context rather than an extraction result. Do not retain provider names, chat filenames, source IDs, citations, confidence scores, or review history in canonical entries.

If a preference later changes, edit the canonical Markdown directly. Git history is sufficient for tracking changes to the maintained context.

## Writing useful guidance

Avoid vague summaries:

> The user likes deep conversations.

Prefer guidance an assistant can act on:

> When the user introduces an idea speculatively without asking for implementation advice, engage with the idea first. Explore implications, contradictions, analogies, and adjacent ideas instead of immediately converting the discussion into action items.

Good context should be durable, specific enough to change assistant behavior, and compact enough that a human can maintain it directly.

## Curated examples

An optional `examples/` directory may eventually contain short examples of interactions that worked especially well or badly. Each example should explain the behavior it illustrates and include only the minimum excerpt needed.

Examples should be standalone and need not identify the originating provider or chat. They are supporting material; the distilled guidance in `context/` remains canonical.
