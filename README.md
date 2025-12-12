# 🏀 Will OKC Break 73–9?

## Why I built this

I’m a Warriors fan first, analytics second.

The 2015–16 Golden State Warriors went **24–1** to start the season.  
Right now, the Oklahoma City Thunder are also **24–1**.

A couple hours before OKC’s next game, I found myself genuinely thinking:  
*“Are they actually about to do this?”*

At the same time, my Twitter feed was full of takes like *“Shai right now is better than prime Curry”* — which, respectfully, felt like pure ragebait. Curry did what he did while going up against **prime LeBron**, changed the way basketball is played, and led a team that defined an era. The league context matters, and people tend to forget that.

So instead of arguing online, I decided to actually **model it** and see what the numbers say.

I’m also fully biased. I’ll admit that upfront.

---

## About me

I’m a very motivated and determined high school student who sets goals and goes out of my way to reach them.  
I’m interested in machine learning, especially applied to sports, and I hope to one day work as an ML engineer (ideally with the NBA).

This project is part of my GitHub portfolio, but honestly, I also did it for myself — so I wouldn’t wake up anxious checking OKC’s record every morning.

---

## What this project does

This project estimates the probability that the **Oklahoma City Thunder reach at least 73 wins** in an 82-game NBA season.

Instead of using a naive “current win percentage” approach (which gives absurd answers like 99%), I built a model that:

- Uses **team strength (Net Rating)**
- Is **calibrated on the 2015–16 Warriors (73–9)**
- Accounts for **home vs away performance**
- Includes **regression to the mean**
- Includes **uncertainty** in how strong OKC actually is after a small sample size

I used Python and simulations to test different assumptions and see how sensitive the result really is.

I did use AI as a **learning tool** while building this — not to copy-paste code, but to guide me, explain concepts, and help debug. I’m new to this space, I don’t want to spend money on courses, and AI has honestly been the best teacher so far without the pressure of strict timelines on top of school.

---

## The core idea (no fluff)

1. Build a **logistic win-probability model**
2. **Calibrate it using the 2015–16 Warriors**
3. Apply the *same model* to OKC
4. Add **shrinkage** so early-season dominance doesn’t get treated as absolute truth
5. Simulate the rest of the season thousands of times

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
- **Optimistic (~40%)**: If OKC’s early net rating is close to their true strength and regression is minimal.
- **Pessimistic (~7%)**: If OKC regresses toward a “normal elite team.”

This explains *why* the 73–9 record is still special.

---

## Why the Warriors were different (biased but honest)

I’m 100% biased, but context matters.

- The Warriors did this while going up against **prime LeBron**
- They reshaped spacing, shooting, and pace across the league
- Their dominance wasn’t just numbers — it forced the NBA to adapt

OKC is a great team.  
But if they ran into that 2016 Warriors squad in a playoff series?  
I’m taking **GSW in 4**.

---

## Limitations

This project is still a work in progress:

- Uses **average remaining SOS** instead of game-by-game schedule
- Net Rating is based on a **small sample size**
- No injury or roster-change modeling
- Assumes independence between games

I’m still in high school and learning — this isn’t meant to be a final answer. The project doesn’t end here.

---

## What’s next

- Game-by-game schedule simulation using opponent SRS  
- Injury / availability adjustments  
- More sports + ML projects (this is just one of many)

I’m mainly exploring, learning, and building.

---

## Final takeaway

After accounting for regression and uncertainty, OKC’s probability of reaching 73 wins is **closer to ~20–25% than 99%** under realistic assumptions.

Which is exactly why the 2015–16 Warriors season still deserves respect.
