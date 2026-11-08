# Revelationary Bible data rules

## Verified publisher parsing boundary — 8 November 2026

- HTML verse wrappers may nest, close early or contain book introductions.
  Closing spans and element textContent alone are not reliable verse boundaries.
  Follow explicit numbered markers/reference links, retain continuations outside
  wrappers, and validate every row before writing. SKB Psalms 70:6/125:2 are
  regression examples, not the limit of this rule.
- Separate scripture, numbered superscriptions, inline expansions, editorial
  notes and unnumbered section/book introductions. A quoted alternative inside
  commentary never establishes another scripture row (SKB Psalm 145 Nun example).
- Complete SKB Psalms recovery is local commit `8614a8d9b6fa`; original routes and
  publisher source are retained in `conversion-provenance/2026-11-08/sv-skb/`.
  Chris subsequently approved the remaining missing verses and truncated passages
  on 8 November. The full local repair is recorded in the parent
  `docs/swedish-feature-checks.md` and `remaining-manifest.json` beside the Psalm evidence.
  Comparison differences are review candidates, never permission for hybrid text.

- Even same-edition publisher exports can duplicate a preceding chapter passage,
  shift labels or omit a final passage. Verify correspondence by content against
  retained records; preserve stored IDs/labels/routes and use explicit reviewed
  adapters. Never derive alignment from counts, ordinal positions or offsets.
  Numbers 13, Ecclesiastes 7 and Ezekiel 42 provide regression evidence.
- Complete older wording is retained. Restore a confirmed truncated passage as
  one coherent publisher passage; do not splice revisions or expand intentional
  omissions. Keep frozen original chapters and hash-pinned source archives so
  repeat imports and changed-text evidence are independently checkable.

## Dutch local correction approval — 8 November 2026

Chris approved the six Canisius 1939 passage corrections and local feature plan in
parent `docs/dutch-feature-checks.md`. Preserve all IDs/routes and source omissions;
DAG is publisher Daniel, not an unsupported book. Archive/source hashes and frozen
originals are in `conversion-provenance/2026-11-08/nl-nld1939/`. No Dutch merge,
push or deployment is approved. The earlier Indonesian/Swedish release approval
must not be reused for these new changes.

## Approved same-edition recovery — 8 November 2026

Chris approved the complete TSI publisher import and source-correction plan.
For Swedish, verify Svenska Kärnbibeln itself and recover coherent passages
through the existing CUV-shaped converter. App-generated IDs are persistence
identities, not publisher/version evidence. Do not construct hybrid scripture
by splicing revised publisher wording into truncated old fragments. Archive
the original source, pin the verified same-edition source, retain existing IDs,
labels and routes, and distinguish intentional versification from lost content.
All implementation remains subject to the parent approval rule. Chris requests
local commits as work is completed; no merge, push or deployment is authorized.

Chris reaffirmed these constraints on 7 November 2026. This repository is the
Bible source of truth for Revelationary. If it is checked out inside the webapp,
also read the parent `AGENTS.md` and `docs/verse-identity-evidence.md`.

- **Hard publication gate — Chris, 7 November 2026:** do not merge, push or
  deploy without explicit approval of the concrete operation and changes. This
  supersedes earlier permission to push Bible conversions. Continue approved
  local work, prepare the reviewable result, then wait before publishing.
- **Hard source-of-truth rule — Chris, 7 November 2026:**
  `revelationary.github.io/bible-api` is ALWAYS the Bible authority. External
  editions must not replace its text, labels, IDs or architecture. Treat an
  external discrepancy as a finding for review, never as permission to rewrite
  this source. Verify canonical correspondence against this repository's KJV
  records, using its working CUV edition as the conversion template.
- Keep the existing API folder structure and retrieval paths. Chris explicitly
  selected **CUV (`cuv-zh-hant`), already working in the webapp**, as the conversion
  architecture reference. Add missing OT/NT book aliases to the existing maps
  (7 November 2026).
  Conversion repairs must fit that architecture, not replace it.
- Research the existing source, converter, consumer code, Git history and actual
  WordPress identity before changing data. Unusual verse labels, blank rows and
  combined verses may be deliberate compatibility conventions.
- Preserve source text, record IDs, book/chapter/verse labels and original native
  source files. Conversion into the reader shape must not silently renumber,
  split, duplicate, discard or reinterpret passage content.
- **ALL translations use KJV as the canonical anchor for comments AND Hebrew.**
  Chris specifies WordPress's 31,102 Bible-verse posts as existing KJV identities.
  Every source verse/span must resolve by content through that KJV model; no
  translation or Hebrew dataset may introduce a competing canonical anchor.
- **Shared comments align by content, not equal numbers.** Establish the span
  that contains corresponding content across translations. A regrouped span
  shares the existing WordPress thread at its first corresponding KJV verse.
  Chris's example: `[10, 11, 12] -> 10`, then resume at `13` when both realign.
- ANY corresponding member must reach that shared discussion in ANY supported
  edition, including KJV. The reader must not have to choose the first verse.
  Include every member and both realignment boundaries in verification. A
  source-edition-only override does not establish the cross-language bridge.
- Preserve source and resource labels, but resolve Hebrew/other study resources
  THROUGH the KJV anchor and full verified KJV content span using explicit
  mappings to their internal labels. KJV remains canonical. A span lookup must
  not lose non-first members. Apply this to ALL translations, ALL drift patterns
  and ALL existing/future editions, not only the examples already reviewed.
- Content correspondence can cross a chapter boundary. Do not infer it from
  array positions, total verse counts, the nearest/last available verse, or a
  blanket offset. Keep source references separate from WordPress anchors.
- Preserve verified mappings and the original span-anchoring approach. Do not
  regenerate all mappings or create translation-specific WordPress posts/threads.
  A historical numeric fallback is not proof of content correspondence.
- Known source/post identity: KJV record `888947839710035969` remains Ezra `9:0`.
  WordPress post `11518` uses `ezra-9-0` (live read verified 7 November 2026).
  Renaming that source row to `9:10` breaks the existing integration.
- The existing converter retains full combined verse labels inside records and
  uses their first numeric component for individual filenames. Inspect all
  consumers and collisions before changing this convention.
- Distinguish intentionally excluded books from missing aliases for required
  books. A raw folder count or metadata scope is not converted OT/NT readiness.
  Validate actual chapter/verse output and the edition's own chapter structure.
- Preserve native input when converted and native folders coexist. Repeated
  conversion must not accidentally use previous output as a replacement source.
- Inspect remote history before replaying conversions. In the inspected history,
  `a60acf0b` rolled back `448e76cc` to the four-book repair. Investigate that
  rollback; do not silently reinstate it as a routine update.
- Website enablement requires functioning OT and NT. Prioritize editions paired
  with translated Hebrew learning notes, without treating Hebrew Bible text,
  lesson notes and translated dictionary entries as interchangeable coverage.
- Check chapter and individual-verse routes, source IDs, range labels, shared
  WordPress anchors and generated keyword indexes. Keep reader and search assets
  on the same verified revision. Label simulated tests and actual live checks.
- Do not claim a publication or complete conversion without inspecting the
  committed/pushed revision, delivery responses and remaining integration gaps.
