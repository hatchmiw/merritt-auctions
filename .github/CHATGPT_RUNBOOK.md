# ChatGPT Runbook — Merritt Auctions

## Mandatory startup rule

At the start of any Merritt auction review, analysis, debugging, or automation work:

1. Read this file.
2. Read the repository `README.md`.
3. Read the relevant auction metadata under `auctions/<auction-id>/`.
4. Do not assume photo inspection occurred merely because a filename, URL, title, description, or manifest was read.

## Repository role

GitHub is the source of truth for Merritt auction data, live bid snapshots,
screening notes, and temporary photo-batch mappings.

Permanent auction metadata normally lives under:

```text
auctions/<auction-id>/
  README.md
  summary.md
  summary.csv
  lots.json
  live.json
  photo-batches.json
  QUICK_PASS.md
```

## Photo review rule

A lot is not "photo reviewed" unless the actual image bytes have been supplied
to vision. Titles, descriptions, URLs, thumbnails listed in metadata, and image
filenames are not substitutes for visual inspection.

For GitHub Actions photo artifacts:

1. Read `photo-batches.json`.
2. Identify the artifact containing the lot.
3. Retrieve only the relevant artifact.
4. Extract and inspect only the needed lot photos.
5. Do not infer visual details from metadata alone.

## Screening rule

Fast screening may use catalog title/description to identify candidates. Do not
turn a title-only candidate into a confident value or max-bid recommendation
until condition, completeness, authenticity, and relevant photos are checked.

### Default screening lens

Prioritize:

- practical personal use;
- farm/shop/automotive usefulness;
- Michigan/local-interest collectibles;
- obvious intrinsic-value items;
- unusually favorable resale opportunities.

Penalize:

- fragile or slow-moving bulk inventory;
- high sorting labor;
- uncertain condition/authenticity;
- bulky items with weak resale value;
- titles that overstate what photos actually support.

## Auction 778984

Initial screening is stored in `auctions/778984/QUICK_PASS.md` and
`auctions/778984/quick-pass.csv`.

That pass is title/catalog based and is **not** a completed photo review.
