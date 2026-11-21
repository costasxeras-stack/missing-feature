# 0002: Rank fitting parts first, never hide the rest

**Status:** accepted, 0.1.0

## Context

Fitment data is incomplete. Hiding parts without data would hide good offers.

## Decision

Four labels: fits, fits some engines, does not fit, no fitment data. Only "does not fit" moves down.

## Tradeoff

- Lists stay long
- No false negatives from missing data
