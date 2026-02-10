# Fetch and Retry Rules

## Candidate Selection

Default `sync` selection:
- Include entries with URL (`canonical_url` or `url`) present.
- Include rows with missing content state (`entry_content` absent).
- Include rows with `status != ready` (typically failed).

Optional selection controls:
- `--force`: include all rows (including ready).
- `--only-failed`: include only failed rows.
- `--refetch-days N`: include ready rows older than `N` days.

## URL and Extraction Priority

1. Pick URL:
- `canonical_url` first.
- fallback `url`.

2. Extract body text:
- Prefer `trafilatura` if installed and not disabled.
- Fallback to built-in HTML parser.

3. Quality threshold:
- Enforce `--min-chars`.
- Treat too-short extraction as failure.

## Failure Handling

- HTTP/network/parsing/content-type errors are recorded per entry.
- One failed entry does not stop the rest of the sync batch.
- `--fail-on-errors` optionally returns non-zero if new failed states are produced.

## Operational Guidance

- Run `ai-tech-rss-fetch sync` first to keep `entries` fresh.
- Run this skill on a separate schedule:
  - high-velocity feeds: every 10-30 minutes
  - normal feeds: every 30-120 minutes
- Keep `--limit` bounded for predictable runtime per job.
