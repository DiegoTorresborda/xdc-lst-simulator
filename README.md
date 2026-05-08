# XDC LST — LP Yield Simulator

Interactive yield simulator for prospective Liquidity Partners in the XDC Liquid Staking protocol by Protofire.

**Live demo:** open `index.html` directly in any modern browser, or deploy via GitHub Pages (see below).

---

## What it does

Lets an LP model their projected APY across the five revenue streams of the XDC LST as a function of:

- LP commitment ticket ($250k Standard / $500k Strategic / $1M Anchor)
- XDC token price (entry vs prevailing/exit)
- Total LST market share (% of XDC circulating supply)
- Total cohort raise ($2M – $5M)
- Lock period (12 – 48 months)

### Two views

- **Year 1 view** — single-year snapshot with a stacked breakdown of base staking yield, protocol fee share, and outcome-based compensation.
- **3-Year cumulative** — full ramp curve with per-year revenue, exit scenarios at end of Y1 / Y2 / Y3, IRR, and detailed cash-flow table. Reflects the deal mechanic that protocol fee share continues for 3 years even after early exit.

### Quick scenarios

Both tabs include 10% / 20% / 30% supply-target preset buttons that snap the TVL slider(s) to common LP-pitch scenarios.

---

## Mathematical model

See `LP_Reward_Model.docx` for the full derivation. Headline:

```
APY = (R₁ + R₂ + R₃ + R₄) / I

R₁ = A_LP · r · (1 − f) · price                 base staking yield
R₂ = N_LP · (A_node · r · f · price · ν − C)   validator ops margin
R₃ = ρ · λ · max(0, Π)                          protocol fee share
R₄ = ρ · λ · OBC_pool                           outcome-based compensation
```

Where ρ is the tier rate (20% / 30% / 40%) and λ = I / T is the LP's pro-rata in the cohort.

---

## Hosting on GitHub Pages

After pushing this repo to GitHub:

1. Settings → Pages
2. Source: `main` branch, `/ (root)`
3. Save

The simulator becomes available at `https://<org>.github.io/<repo>/`.

---

## License

Confidential. For prospective Liquidity Partners only.

© Protofire — diego@protofire.io
