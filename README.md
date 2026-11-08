# NRR Forecast Simulator

A CS Lab tool: turn one point of retention or expansion into euros of ARR, across three scenarios.

## How it works

- **NRR = GRR + expansion rate**, over 12 months, on existing customers only (new logos are excluded).
- **GRR**: share of starting ARR kept after churn and downgrades, before any upsell.
- **Expansion**: upsell and cross-sell, as a share of starting ARR.
- **ARR in 12 months** = starting ARR × NRR.
- **Scenarios**: Base uses your inputs. Prudent is GRR −3 pts and expansion −4 pts. Ambitious is GRR +3 pts (capped at 100%) and expansion +6 pts.
- **What one point is worth**: 1% of starting ARR, for GRR and for expansion. GRR cannot exceed 100%, so its lever is shown as "Already 100%" once the ceiling is reached; expansion has no cap, which is why NRR can go above 100%.
- **GRR gap to 100%**: the points of retention lost to churn and downgrades, and their value in ARR (starting ARR × gap). It equals the churn bar of the base scenario.
- **Renewal loss** is an approximation: it applies the base GRR to the ARR renewing within 120 days.
- Default figures are illustrative.

## Inputs

Amounts accept `4800000`, `4,800,000`, `4 800 000`, `4.8M`, `4,8M` or `4800k`.

## Privacy

All calculation happens in the browser. No data is sent to a server, and the CSP in `netlify.toml` blocks outgoing connections.

## Deployment

Static site, no build step: publish the folder as is on Netlify (publish directory `.`).
