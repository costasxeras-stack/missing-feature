# Case study: Missing Feature

## The question

In Second Look I logged how Allegro search handles a car parts query that names the car. The car barely changed the results and no result card said whether a part fits. This project takes the next step a PM would take: define the feature, prototype it, size it honestly and plan the launch.

## Approach

I started from the logged evidence in Second Look, wrote the problem and the requirements, and built the smallest prototype that shows the whole flow. I made the sizing model a tool with placeholders so it can be filled with real data, and wrote a launch plan that separates the parts the search team owns from the part it does not.

## Decisions

### Detect the car from the query instead of asking first

The vehicle filter exists but shoppers have to fill it in, even when the query already names the car.

**Decision:** Parse make, model and generation from the query, show it as a removable chip, and ask only for what is missing.

Full record: [decisions/0001-detect-dont-ask.md](decisions/0001-detect-dont-ask.md)

### Rank fitting parts first, never hide the rest

Fitment data is incomplete. Hiding parts without data would hide good offers.

**Decision:** Four labels: fits, fits some engines, does not fit, no fitment data. Only "does not fit" moves down.

Full record: [decisions/0002-rank-not-hide.md](decisions/0002-rank-not-hide.md)

### Ads fitment rule as a separate decision

Moving non-fitting promoted listings down affects ad revenue, which the search team does not own.

**Decision:** Propose it, but test it separately with the ads team.

Full record: [decisions/0003-ads-separate.md](decisions/0003-ads-separate.md)

### Sizing with placeholders, not guesses

I have no access to Allegro data. A confident number would be invented.

**Decision:** Build the model with editable inputs, label the defaults as examples, and name the most sensitive input.

Full record: [decisions/0004-placeholder-sizing.md](decisions/0004-placeholder-sizing.md)

## What I learned as a PM

- The strongest proposals show where the evidence stops
- A prototype that shows one full journey beats many polished screens
- Naming the stakeholder (ads) and the decision needed makes a proposal actionable

## Limits

- Evidence is one small test log
- Prototype is not tested with users yet
- Sizing defaults are examples

## What I would do next

1. Test the prototype with [5] drivers who bought a car part in the last three months
2. Write the vehicle parser and measure precision on [n] real queries
3. Add the ads team's view to the launch plan

## My role

I framed the problem, made the product calls, checked every number and wrote the conclusions. Claude (Anthropic) wrote the code with me. 
