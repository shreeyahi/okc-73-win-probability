# 🏀 Will OKC Break 73–9?

## Why I built this

I’m a Warriors fan first, analytics second.

The 2015–16 Golden State Warriors went **24–1** to start the season.  
Right now, the Oklahoma City Thunder are also **24–1**.

A couple of hours before OKC’s next game, I found myself genuinely thinking:
*“Are they actually about to break this record?”*

At the same time, my Twitter feed was full of takes like *“Shai right now is better than prime Curry.”*  
That kind of comparison ignores context. Curry’s peak came while facing **prime LeBron**, reshaping the league’s style of play, and sustaining dominance across an entire season. The league has changed, and records don’t exist in a vacuum.

So instead of arguing online, I decided to test the claim properly — using data and probability instead of hot takes.

I’m fully biased toward the Warriors. This project doesn’t try to hide that — it tries to account for it.

---

## What this project does

This project estimates the probability that the **Oklahoma City Thunder reach at least 73 wins** in an 82-game NBA season.

A naive approach — projecting the current win percentage forward — suggests near-certainty.  
That felt wrong.

Instead, I built a model that:

- Uses **team strength (Net Rating / SRS)** rather than raw wins
- Is **calibrated on the 2015–16 Warriors (73–9)** so the scale is historically grounded
- Accounts for **home vs away performance**
- Explicitly includes **regression to the mean**
- Includes **uncertainty** in how strong OKC actually is after a small sample size

The goal isn’t to predict a single outcome, but to understand **how likely** breaking 73–9 really is once realism is added back into the model.

---

## The core idea (no fluff)

1. Build a **logistic win-probability model**
2. **Calibrate it using the 2015–16 Warriors**, forcing the model to reproduce ~73 wins
3. Apply the *same model* to OKC
4. Shrink early-season dominance so it isn’t treated as absolute truth
5. Run Monte Carlo simulations to estimate probabilities, not certainties

Same math. Same assumptions. Different teams.

---

## Results

I tested three scenarios based on how much OKC might regress and how uncertain their true strength is.

| Scenario     | Mean Wins | P(≥73) | P(≥74) | 5–95% Win Range |
|--------------|-----------|--------|--------|----------------|
| Optimistic   | 69.4      | 39.8%  | 33.5%  | 55 – 79        |
| **Baseline** | **67.5**  | **23.7%** | **18.0%** | **56 – 77** |
| Pessimistic  | 65.0      | 7.2%   | 4.4%   | 56 – 73        |

### How to read this

- **Baseline (~24%)**: Breaking 73–9 is possible, but unlikely without sustained, historic dominance.
- **Optimistic (~40%)**: If OKC’s early net rating reflects real, long-term strength with minimal regression.
- **Pessimistic (~7%)**: If OKC regresses toward a more typical elite team.

This range is the point.  
Once uncertainty and regression are included, records stop looking inevitable.

---

## Why the Warriors were different (biased, but deliberate)

I won’t pretend to be neutral here — context matters.

- The 2016 Warriors sustained dominance while facing **prime LeBron**
- Their style of play permanently changed spacing, shooting, and pace across the league
- Their success wasn’t just statistical — it forced the NBA to adapt

OKC is an excellent team.  
But if this Thunder squad ran into the 2016 Warriors in a playoff series, I’m taking **Golden State in 4** without hesitation.

---

## Limitations

This project is still evolving:

- Remaining schedule strength is modeled using **average SOS**, not game-by-game opponents
- Net Rating is based on a **small sample size**
- No injury, fatigue, or roster-change modeling
- Games are treated as independent events

These limitations are intentional — this project is exploratory, not final.

---

## What’s next

- Full game-by-game schedule simulation using opponent SRS
- Injury and availability adjustments
- Additional sports + ML projects building on this framework

I built this both as a portfolio project and for myself — to replace anxiety and hot takes with actual reasoning.

---

## Final takeaway

Once regression and uncertainty are included, OKC’s probability of reaching 73 wins is **closer to ~20–25% than 99%** under realistic assumptions.

Which is exactly why the 2015–16 Warriors season still deserves respect.
