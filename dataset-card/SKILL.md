---
name: dataset-card
description: Create, update, and audit fixed-format DATASET.md entry points for biological and omics dataset directories. Use when a user asks to document a dataset folder, refresh its dataset card, or check DATASET.md consistency.
---

# Dataset Card

Maintain exactly one `DATASET.md` at the root of each dataset directory that the user explicitly identifies. Do not discover or modify unlisted dataset directories, and never modify the underlying data files.

## Choose the operation

- **Create:** Write `DATASET.md` when it is missing.
- **Update:** Recheck the whole dataset, migrate an older card to the current template, and preserve verified facts and useful human-authored notes.
- **Audit:** Inspect and report problems without changing files. Make fixes only when the user explicitly requests them.

## Use the fixed template

Read [assets/DATASET.template.md](assets/DATASET.template.md) before every operation.

For created or updated cards:

- Keep every heading, field label, and section in exactly the template order. Do not add, remove, rename, or reorder sections.
- Replace every angle-bracket placeholder. Use `Unknown — <reason>` or `Not applicable — <reason>` when a value cannot be established; never guess.
- Use the actual dataset name as the level-one heading. If no canonical name exists, use the dataset directory name.
- Write the card in English unless the user explicitly requests another language.

## Establish the facts

1. Inspect the specified dataset root and its meaningful top-level entries. Prefer manifests, sample sheets, README files, processing records, and safe text or metadata headers; do not load large binary data merely to document it.
2. Use official repository records and primary publication metadata to confirm accessions, canonical URLs, assay details, and citations. Suitable sources include GEO, SRA, ENCODE, 4DN, DOI records, PubMed, and publisher pages.
3. Treat the observed local layout as authoritative for `Contents` and the local processing state. Treat the official source record as authoritative for provenance. Record material conflicts in `Important Notes` instead of silently choosing one account.
4. When an official source is unavailable or inconclusive, use the available evidence, mark unresolved values explicitly, and stop rather than repeatedly searching or substituting an unverified webpage.

## Apply the field rules

- Keep `Summary` to one to three sentences.
- Keep `Experimental context` on one physical line and describe the tissue, primary cell type, cell line, organoid, or other biological material.
- In `Additional sources`, write `Not applicable — single-source dataset` for a single source; otherwise list additional repository, accession, and canonical URL triplets concisely on the same line.
- Give every meaningful top-level file or directory one `Contents` row. Exclude `DATASET.md` itself and incidental system files such as `.DS_Store`. Summarize homogeneous collections inside a directory rather than listing their files recursively.
- Use `raw`, `processed`, `derived`, `mixed`, or `N/A` for `Data level`. A row may list multiple formats when necessary.
- Use one of `original`, `reprocessed`, `transformed`, `subsetted`, or `mixed` for `Processing status`. Include only processing steps that materially affect interpretation.
- Do not infer a reference build from the organism. The template deliberately has no reference-build field. Add an evidence-backed non-default human or mouse build to `Important Notes`; otherwise omit build commentary.
- Use `- None.` when there are no important notes.
- Set `Last verified` to the current date in `YYYY-MM-DD` only after reviewing the entire card against the current directory and available sources. A read-only audit never changes this date.

## Audit the card

For each explicitly specified dataset directory, check:

- `DATASET.md` exists at the dataset root and follows the exact template structure and field order.
- No template placeholders, unexplained `Unknown` values, or unsupported claims remain.
- The `Contents` table has no missing or stale top-level paths and uses the required columns and data-level vocabulary.
- Repository, accession, URL, publication, experimental context, and processing statements agree with the best available evidence.
- `Important Notes` captures material caveats, source conflicts, unusual sample definitions, and evidenced non-default reference builds.
- `Last verified` is a valid ISO date and truthfully represents a full review.

Report audit results per directory, distinguishing failures from unresolved information. At the end of any operation, summarize created or updated cards, unresolved fields, and authoritative sources consulted.
