# ICC ODI Cricket Analytics — Exploratory Data Analysis (EDA) 🏏📊

This repository contains a **Jupyter Notebook** that explores ODI cricket performance through **player, team, venue, and toss-based** lenses.  
It’s designed like a mini-analytics report: **each chart is paired with interpretation** so readers understand *what matters* and *why*—not just what the plot shows.

> **Images live in the `image/` folder** and are embedded below using the same filenames.

---

## Executive takeaways (from the visuals)

- **Scoring profiles differ by player type:** the dataset shows a clear split between **4-heavy accumulators** and **6-heavy power hitters**, which is useful for lineup balance.
- **High wicket volume can come with control trade-offs:** some bowlers appear in both **top wickets** and **top extras**, suggesting aggressive wicket-taking styles that may concede additional runs.
- **Totals ≠ rates:** team “all-time” dominance (total runs/wickets) can reflect match volume, while **average runs per match** better captures “how strong a team scores per game.”
- **Toss advantage is nuanced:** choosing to **field first** shows a higher win rate than batting first, but winning the toss alone is not a guarantee of winning the match.
- **Innings behave differently:** Innings 1 tends to score higher and wider, while Innings 2 is shaped by target pressure, chases, and collapses.

---

## Visual Insights (Charts + Interpretation)

### 1) Top 10 Bowlers by Bowling Average (Lower is better)
![Top 10 Bowlers by Bowling Average](image/bowlingavg.png)

**What it really means (beyond “lower is better”):**
- Bowling average tells you **how expensive a wicket is**. A great strike bowler can still look average if they concede heavily; a controlling bowler can look great even without huge wicket volume.
- Use this chart to identify **efficiency specialists**—the type of bowlers who reduce scoring while still getting breakthroughs.

**How to interpret responsibly:**
- Bowling average is sensitive to **sample size, match conditions, and role** (new ball vs middle overs vs death overs).
- Pair it with the wickets chart (below) to separate:
  - **Elite + durable** (good average, high wickets)
  - **Elite but low volume** (great average, smaller sample)
  - **High volume but pricier** (high wickets, higher average)

---

### 2) Top 10 Batsmen by Batting Average (Higher is better)
![Top 10 Batsmen by Batting Average](image/battingavg.png)

**What this reveals:**
- Batting average is primarily a measure of **consistency** and “how often a batter converts innings into meaningful runs.”
- The leaders here tend to be players with strong **innings-building ability** (high frequency of 40–80 type contributions, fewer cheap dismissals).

**Key nuance:**
- Average can be inflated by **not-outs**, and it doesn’t directly reflect tempo.
- Best practice: read this alongside boundary metrics (4s/6s) or strike rate (if included in your notebook) to understand the balance of **stability vs explosiveness**.

---

### 3) Top 10 Bowlers by Extras (Wides + No-balls)
![Top 10 Bowlers by Extras](image/bowlersextra.png)

**Why this chart matters:**
- Extras are “free runs”—they increase totals without requiring skill from the batter.
- High extras can reflect:
  - genuine discipline issues (spray, overstepping)
  - *or* a tactical trade: bowling at attacking lengths, high pace, swing, yorker attempts at the death.

**How to use it:**
- Combine with wickets to judge **value vs cost**:
  - A bowler conceding many extras but also taking many wickets may still be a net positive.
  - A bowler with high extras and average wickets is a red flag for controllability and match pressure.

---

### 4) Top 10 Bowlers by Total Wickets
![Top 10 Bowlers by Wickets](image/bowlerswick.png)

**What’s actually being captured:**
- This is a **longevity + impact** metric. Bowlers rise here by staying fit, playing lots of ODI cricket, and maintaining wicket-taking ability across eras/conditions.
- It favours bowlers who are trusted across roles: early breakthroughs, middle-overs control, and closing out innings.

**Pro insight:**
- Wicket volume alone can hide economy/average trade-offs. A “complete” ODI bowler often sits well on both:
  - **wickets (volume)**
  - and **average (efficiency)**

---

### 5) Top 10 Players by Sixes
![Top 10 Players by Sixes](image/playerssix.png)

**Why sixes deserve their own analysis:**
- Sixes are a proxy for **scoring acceleration** and “pressure shifting” ability.
- Players high on this list typically change outcomes faster—especially in final 15 overs.

**Practical takeaway:**
- Sixes-heavy profiles are valuable for:
  - setting huge totals from par starts
  - chasing with fewer balls remaining
  - breaking bowling plans when dot-ball pressure builds

---

### 6) Top 10 Players by Fours
![Top 10 Players by Fours](image/playersfours.png)

**What this reveals that sixes don’t:**
- Fours are often associated with **shot placement, timing, and manipulating gaps**, not only brute force.
- A 4-heavy batter tends to be a high-floor run scorer—valuable on tougher surfaces or when power hitting is risky.

**Lineup insight:**
- Teams often need both styles:
  - **4-heavy anchors** to stabilise and build
  - **6-heavy finishers/power hitters** to explode late

---

### 7) Top 10 Players by Total Runs
![Top 10 Players by Total Runs](image/playerstotalruns.png)

**What total runs really measure:**
- This is a “career dominance” indicator driven by:
  - match volume
  - sustained performance
  - role stability (top-order players naturally get more deliveries)

**How to interpret well:**
- Total runs ≠ “best batter” in isolation.
- It’s best read as: **who combined quality with longevity** across the dataset window.

---

### 8) Top 10 Venues by Total Runs
![Top 10 Venues by Total Runs](image/venuetotalrun.png)

**What’s happening here:**
- High total runs at a venue can mean:
  - many matches hosted (volume effect)
  - batting-friendly conditions
  - small boundaries / fast outfield
  - or era effects (modern scoring)

**Smart read:**
- Treat this as a **venue significance / activity** map first.
- If you want “batting-friendly vs bowling-friendly,” extend the notebook by normalising:
  - runs per match at venue
  - average first innings score
  - chasing success rate

---

### 9) Top 10 Teams by Total Wickets
![Top 10 Teams by Total Wickets](image/teamstotalwick.png)

**Why total wickets matters:**
- Wickets correlate with control: teams that regularly take 10 wickets can dictate match tempo and reduce chase probability.
- Like totals in batting, wicket totals reflect both **strength + match volume**.

**Deeper interpretation:**
- A strong ODI team typically ranks high in at least one:
  - wicket-taking dominance (attack)
  - run dominance (batting depth)
- The most complete teams tend to appear across both lists.

---

### 10) Top 10 Teams by Average Runs per Match
![Top 10 Teams by Average Runs per Match](image/teamavgruns.png)

**Why this is more revealing than total runs:**
- Average runs per match is a **rate metric**—it normalises for how often a team played.
- This better captures “modern ODI scoring strength” and can highlight teams that score heavily even with fewer matches.

**Analyst note:**
- A team can rank lower in total runs but high in average runs, implying strong scoring intensity rather than longevity.

---

### 11) Top 10 Teams by Total Runs
![Top 10 Teams by Total Runs](image/teamsruns.png)

**What this tells you:**
- This is a “history + volume + output” scoreboard.
- It rewards teams with:
  - long ODI history
  - high match counts
  - consistent batting eras

**Best paired with:**
- Average runs per match (Chart 10) to separate:
  - “played a lot”
  - from “scored a lot per game”

---

### 12) Win Rate by Toss Decision (Bat vs Field)
![Win Rate by Toss Decision](image/tossdec.png)

**Meaningful interpretation:**
- In this dataset, **fielding first shows a higher win rate** than batting first (visually ~0.95 vs ~0.92).
- This supports the strategic idea that chasing can be advantageous due to:
  - target clarity (you know what to pace)
  - conditions that improve later (dew, ball skidding)
  - reduced pressure when chase is controlled early

**But—important caution:**
- Toss decision interacts with pitch reading, opposition strength, and venue. Captains often choose based on conditions, so this pattern isn’t purely causal.

---

### 13) Impact of Winning the Toss on Match Outcome
![Impact of Toss on Match Outcome](image/tossimpact.png)

**What the chart suggests:**
- Even after winning the toss, the win/loss split remains substantial (in your output, losses appear higher—roughly ~59% loss vs ~41% win).

**How to interpret like an analyst:**
- This highlights an important truth: **toss is a small edge**, not the deciding factor.
- Stronger teams still win more often regardless of toss; weaker teams can lose even with the toss advantage.
- For causal inference, you’d need controls (team strength, venue, era, etc.).

---

### 14) Distribution of Total Wickets per Match (Innings 1 vs Innings 2)
![Distribution of Total Wickets per Match](image/disttotalwick.png)

**What this distribution can indicate:**
- Innings 2 often reflects chase pressure—teams accelerate, increasing dismissal probability.
- If Innings 2 clusters near 10 wickets (all out) more often, it suggests chasing collapses are a meaningful pattern in the dataset.

**Tactical interpretation:**
- When chasing, wicket preservation to the 35–40 over mark is often the difference between a smooth chase and a collapse.

---

### 15) Distribution of Total Runs per Match (Innings 1 vs Innings 2)
![Distribution of Total Runs per Match](image/totalrundist.png)

**What this shows beyond “two histograms”:**
- Innings 1 can have a wider, higher distribution because teams bat without a fixed target and can maximise late overs.
- Innings 2 scoring is constrained by:
  - the target (you stop once you reach it)
  - collapses and pressure chases
  - strategic pacing (anchoring vs aggression)

**Analyst takeaway:**
- If Innings 1 is clearly right-shifted, it supports the idea that **setting totals can be more explosive**, while chasing is more outcome-dependent.

---

## How to run locally

1. Clone the repository
2. (Recommended) Create and activate a virtual environment
3. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
4. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
5. Open **`ICC (1).ipynb`** and run all cells to reproduce outputs.

---

## Notes & limitations

- This is **exploratory** analysis: it describes patterns, not causation.
- Results depend on dataset coverage, timeframe, and any filters used in the notebook.
- Next steps (if you want to upgrade this into a portfolio-grade analytics case study):
  - add a `requirements.txt`
  - add a short “Dataset Overview” section (source + timeframe)
  - include a small “Key Questions Answered” section
  - add normalised venue metrics (runs per match, avg innings score)

---

## Author

**Ishan Khanijo**  
Notebook • Analysis • Visual storytelling
