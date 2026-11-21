# 0001: Detect the car from the query instead of asking first

**Status:** accepted, 0.1.0

## Context

The vehicle filter exists but shoppers have to fill it in, even when the query already names the car.

## Decision

Parse make, model and generation from the query, show it as a removable chip, and ask only for what is missing.

## Tradeoff

- A wrong detection is visible and must be easy to undo
- Removes a step for most shoppers
