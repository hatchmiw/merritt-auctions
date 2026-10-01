# Merritt Auctions

Working repository for Merritt Auction Service / HiBid auction research.

## Current auction

- Auction ID: **778984**
- Auction: **Merritt Online Auction #49**
- Auctioneer: **Merritt Auctions, Inc.**
- Catalog size: **333 lots**
- Close: **October 5, 2026, soft close beginning at 6:00 PM Eastern**
- Catalog: https://merrittauctionservice.hibid.com/catalog/778984/merritt-online-auction--49

## Workflow

This repository follows the proven architecture in `hatchmiw/pioneer-auctions`:

1. Export the complete HiBid catalog to `auctions/<auction-id>/`.
2. Keep permanent metadata in Git.
3. Split auction photos into temporary 100-lot GitHub Actions artifacts.
4. Map lots to those photo artifacts with `photo-batches.json`.
5. Refresh live prices separately from the catalog snapshot.
6. Visually inspect actual photo bytes before making condition-dependent conclusions.

## Current review

Auction **778984** has an initial title/catalog quick pass under
`auctions/778984/QUICK_PASS.md`. It is intentionally not treated as a
completed photo review.
