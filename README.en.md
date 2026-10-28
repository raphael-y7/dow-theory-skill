<h1 align="center">Dow Theory Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills the index-reading methods from Robert Rhea's *The Dow Theory* into 13 capability cards that can be triggered individually or combined.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the book into skill modules that can be triggered, executed and tested.

## What these skills solve

- One index prints a new high and the other does not follow — should the signal be accepted, waited on, or dismissed as an illusion? Three states, three completely different actions
- Is this decline a "most deceptive" secondary reaction, or has the primary trend already reversed? A secondary reaction usually retraces 33%–66% of the prior primary movement and moves faster than it; mistaking one for a reversal is the main source of losses
- Which stage of the bull market are we in, or how far into the bear market are we — and should the stance be aggressive or defensive?
- After a long bear market with bad news everywhere the index stops falling — can I buy in? And conversely, is this a top, should I trim or exit? These are two separate checklists, and their thresholds must not be borrowed from each other
- Do volume and price agree, and is the market overbought or oversold? And should I act on claims like "the big players are dumping", "a double top is confirmed" or "major news just broke"?
- Where does the stop go, how large a position lets me sleep, should I average down or add, and what annual return is realistic?

## What was distilled

13 capability cards, organized in the order "fix the direction first, then the position, then verify the evidence, and finally land on execution":

- **Trend and structure**: `primary-trend-identification-skill` (primary trend call: high/low staircase + 3% net reversal + bull/bear reversal criteria), `dual-index-confirmation-filter-skill` (dual-index mutual confirmation filter: an unconfirmed signal is an illusion), `secondary-reaction-assessment-skill` (secondary reaction identification and depth: 33%–66% + speed asymmetry + completion sequence), `line-formation-reading-skill` (narrow-range line reading: accumulation/distribution inference and breakout direction)
- **Bull/bear position and tops/bottoms**: `bull-bear-stage-positioning-skill` (three-stage locator: anchor by driver and calibrate risk stance), `bear-bottom-checklist-skill` (bear-market bottom checklist: the nine-bear-market profile of Figure 1), `bull-top-exit-signals-skill` (bull-market top signal grading and exit decisions: the September–October 1929 specimen)
- **Evidence and false signals**: `volume-price-health-skill` (volume-price health: overbought/oversold and the dull/active vocabulary), `pseudo-signal-troubleshooting-skill` (false-signal and attribution triage: premise gates + anti-pattern list)
- **Execution, statistics and training**: `stock-preflight-market-check-skill` (pre-flight market trend check before any single-stock trade: the fail-safe gate), `trading-discipline-rules-skill` (trading discipline and money management: stops / position size / adding direction / return expectations), `secondary-reaction-stat-baseline-skill` (secondary-reaction statistical baselines and data infrastructure: 35-year distribution + record template + divisor method), `forecast-self-training-skill` (forecast self-training: cover-the-chart forecast — compare with Hamilton's commentary — attribute the differences)

## Two packaging modes: single and pack

The same 13 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `dow-theory-skill` | **8**: one source router + 7 promoted standalone skills |
| Where the 13 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the routing table | 7 high-frequency cards become standalone skills; the other 6 stay in the router's `references/` |
| Triggering | Only the entry description participates in matching; routing happens after entry | The 7 high-frequency capabilities are matched directly, one hop fewer |
| Upgrades | Replace 1 directory | Replace 8 directories |

The 7 cards promoted to standalone skills in the pack:

- `primary-trend-identification-skill` — primary trend call (staircase + 3% net reversal + reversal criteria)
- `dual-index-confirmation-filter-skill` — dual-index mutual confirmation filter
- `secondary-reaction-assessment-skill` — secondary reaction identification and depth
- `line-formation-reading-skill` — narrow-range line reading
- `bear-bottom-checklist-skill` — bear-market bottom checklist
- `bull-top-exit-signals-skill` — bull-market top signal grading and exits
- `trading-discipline-rules-skill` — trading discipline and money management

The 6 cards that stay in the router and are served by it directly: `volume-price-health-skill`, `bull-bear-stage-positioning-skill`, `stock-preflight-market-check-skill`, `secondary-reaction-stat-baseline-skill`, `forecast-self-training-skill`, `pseudo-signal-troubleshooting-skill`.

### Which one to install

Pick by the way you work, and **install only one**:

| How you work | Recommended | Why |
|---|---|---|
| You use DSH / Codex / Claude Code with a skills directory and want a clean list | single | Takes 1 slot, loses no capabilities |
| Your daily questions concentrate on "bull or bear now / is this new high trustworthy / how deep is this pullback / is this the bottom / should I exit / where is my stop" | pack | Those are exactly the promoted standalone skills, matched directly |
| You distribute to several agents or teammates who pick what they need | pack | They can install only the standalone skills they want |
| You want to install once and maintain one directory | single | Upgrades replace a single directory |

> Both builds come from the same bundle and carry identical capabilities. **Installing both will double-trigger**, so pick one.

## Examples

### Example 1: one index prints a new high and the other does not follow

**User question**

"The Shanghai Composite made a new high for the year today and the Shenzhen index did not follow. Is that a valid breakout? Can I add to my position?"

**How the skill reasons**

- First pass the data-quality gate in `dual-index-confirmation-filter-skill`: before any reading, strip mechanical displacement caused by corporate actions (dividends, splits, index reconstitution), then check whether the index pair is dominated by a single policy variable or a few individual stocks. The in-book specimen is specific: in one week of September 1926 the industrial index showed a surface decline of 3.19 points, which looked like real selling, but a General Motors ex-dividend mechanically pushed the index down 3.35 points — the entire decline (and more) came from mechanical displacement, with no real selling pressure
- Then run the three-state test: the other index has followed in the same direction = "confirmed"; it has not yet = "awaiting confirmation", and the only correct action there is to write down what the other index must do to count as confirmation, then wait; it never confirms = "dismiss as illusion" and file it. Confirmation need not occur on the same day, or even in the same week
- Negative insurance rule: when only one index gives an indication, treat it as "no signal" — do not enter, and do not trade the other way either. "Half a forecast is not better than none"
- If the conclusion is to be upgraded to "trend reversal", it must go through the full criteria in `primary-trend-identification-skill`: bull-to-bear = no new high within a reasonable time + both indices break below the prior secondary low; a break by one index is only a warning, not a change of call

**Sample answer**

> Do not call it a breakout yet. This filter has exactly three outputs: confirmed, awaiting confirmation, dismissed as illusion. You are in the second one — Shenzhen has not followed, so the correct action is not to add, but to write down the confirmation condition (which level or range Shenzhen must clear) and then wait. How long? The book gives no quantitative rule for the confirmation window — there is no number in the original text — so set your own observation period from the "3 weeks to several months" statistical range of secondary reactions and state that it is a convention, not something to revise afterwards. Also check one thing first: were there large ex-dividend events or index reconstitutions in the past few days? In the book, the entire 3.19-point "decline" in that September 1926 week came from a 3.35-point mechanical drop after the General Motors dividend; it was not selling pressure. One more layer has to be stated: the book's two indices are Dow industrials plus railroads, and A-shares have no counterpart — "Shanghai plus Shenzhen" is only a translator's analogy in the Chinese edition, not a Rhea rule, and it has never been tested for co-movement, so attach an "untested substitute index pair" disclaimer to this conclusion. If you later want to upgrade it to "trend reversal", that is a separate pass through the reversal criteria: both indices must break below the prior secondary low; a break by one index is only a warning.

### Example 2: a year of decline, bad news everywhere — can I buy the bottom?

**User question**

"The market has fallen for almost a year. Bad news keeps coming, but the index barely falls any more and volume has dried up. Is it time to buy the bottom?"

**How the skill reasons**

- Go into `bear-bottom-checklist-skill` and tick the items from the nine-bear-market profile of Figure 1: the bottom zone lasts 60–90 days with index amplitude within 3% (7 of 9 cases, the other 2 close to 5%); volume has been declining for months before the low (6 of 9 — in the other 3 the volume signal fails, so watching volume alone misleads); the market is immune to bad news, dull, with pessimism everywhere; the bottom shows up as a narrow-range line that is clearly broken upward, with rebound lows stepping higher
- Reverse exclusion: a double bottom is not a judgment criterion. Of the 9 bear markets, 3 had a double bottom in one index only, 3 had it in both, and 3 had none at all — "double bottom = bottom" does not hold
- Confirmation criteria (bear to bull): no new low + both indices rebound above the high of the last major rebound; the safe buying point = a huge reaction after a big advance that does not break the recent bear-market low, followed by a second rebound that clears the prior rebound high
- Summary: only when all seven items are present does it upgrade to "bottom probability high + long entry timing confirmed"; if any item is missing, the conclusion is fixed at "downgrade to observation" and "you can buy the bottom" is forbidden

**Sample answer**

> Your two arguments hit only two items on the checklist, which is not enough to conclude "you can buy the bottom". First measure the two numbers of the bottom zone: how many days it lasted and what the amplitude was — 7 of the book's 9 bear markets had a bottom zone of 60–90 days with amplitude inside 3%, the other 2 were close to 5%, and anything beyond that must be down-weighted and noted in the conclusion. On shrinking volume: that held in only 6 of 9 cases, and in the other 3 the volume signal failed, so it is second-order evidence and cannot carry a bottom call on its own. Then go through the bad news item by item: is it "news still bad but the index refuses to make a new low" (that is what immunity looks like), or did the news just land while the index is still sliding? Finally the confirmation criteria: no new low + both indices rebound above the high of the last major rebound — only when both are met is it a bear-to-bull turn; if either is missing, the output can only be "downgrade to observation", never "you can buy the bottom". Two expectations to accept up front: buying within 10% of the low counts as luck, and by the time price is up 20% the trend change is already obvious to anyone familiar with this method — bottom confirmation is inherently late. The boundary also has to be stated: Figure 1 samples only 9 US bear markets from 1897–1923, with no weighted scoring and no out-of-sample test, and the 60–90 days and 3% parameters were set for old index levels and old volatility, so they must be re-estimated before use on A-shares. The book also reports no hit rate for bottom signals — this is probability language, not a guarantee.

## How these skills were generated

These skills were produced with the **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)** RIA-TV++ pipeline, in six stages:

1. **Whole-book comprehension (Adler analysis)** — apply Mortimer Adler's analytical reading method to the book: structure, interpretation, criticism, application
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) mine candidate methodology units from the source text
3. **Triple verification** — every candidate must pass three checks: at least two independent in-book supports (cross-domain), the ability to answer questions the book never explicitly addresses (predictive power), and not being common sense (distinctiveness)
4. **RIA++ construction** — structure each unit along R (quotation) / I (restatement in own words) / A1 (in-book case) / A2 (future trigger scenario) / E (executable steps) / B (boundaries and blind spots)
5. **Zettelkasten linking** — map dependencies, contrasts and combinations between cards, producing the capability index and routing table
6. **Trigger and output testing** — design trigger scenarios and output evaluations for every card, checking trigger conditions, boundaries and stop behaviour item by item, with failing cards sent back for rework

The book's own structure also shapes the distillation: the upper part, Rhea's main text (chapters 1–19), is the theoretical backbone; the six embedded "professional analysis" sections are the Chinese edition's adaptation notes for the A-share context, usable only as adaptation clues and never promoted to Rhea's own rules; the lower part, chapter 20, is a compilation of Hamilton's 1903–1929 columns, serving as the case and citation library and as the comparison material for the forecast self-training card. Every card's boundary section carries the stage-0 critique: all parameters come from the US market of 1897–1931, with no out-of-sample test, and must be re-evaluated before use on A-shares.

## Repository layout

```text
dow-theory-skill/
├── README.md                      ← Chinese version
├── README.en.md                   ← you are reading this
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← whole-book comprehension (Adler four-step, stage 0 output)
├── verified.md                    ← triple-verification summary (174 verified units)
├── single/                        ← single-entry build
│   └── dow-theory-skill/
│       ├── SKILL.md               ← entry: triggers + routing table + loading rules
│       ├── BUILD_MANIFEST.json    ← build manifest and file hashes
│       └── references/
│           ├── overview.md        ← whole-book overview
│           ├── capability-index.md  ← full intent and keyword index
│           ├── cheatsheet.md      ← decision-rule quick reference
│           ├── glossary.md        ← glossary
│           └── capabilities/      ← 13 capability cards
├── pack/                          ← multi-entry build (compact pack)
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── dow-theory-skill-router/
│   │   ├── SKILL.md               ← source router entry
│   │   └── references/            ← 13 cards + indexes, called by the router
│   ├── primary-trend-identification-skill/
│   │   └── SKILL.md
│   ├── dual-index-confirmation-filter-skill/
│   │   └── SKILL.md
│   ├── secondary-reaction-assessment-skill/
│   │   └── SKILL.md
│   ├── line-formation-reading-skill/
│   │   └── SKILL.md
│   ├── bear-bottom-checklist-skill/
│   │   └── SKILL.md
│   ├── bull-top-exit-signals-skill/
│   │   └── SKILL.md
│   └── trading-discipline-rules-skill/
│       └── SKILL.md
```

## Usage

Clone the repository first:

```bash
git clone https://github.com/raphael-y7/dow-theory-skill.git
```

### Install single (recommended first try)

```bash
# macOS / Linux
cp -r dow-theory-skill/single/dow-theory-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\dow-theory-skill\single\dow-theory-skill "$env:USERPROFILE\.agents\skills\"
```

### Install pack

Copy only the directories that contain a `SKILL.md`; do not copy the two JSON files under `pack/` into your skills directory:

```bash
# macOS / Linux
cd dow-theory-skill/pack
cp -r dow-theory-skill-router \
      primary-trend-identification-skill \
      dual-index-confirmation-filter-skill \
      secondary-reaction-assessment-skill \
      line-formation-reading-skill \
      bear-bottom-checklist-skill \
      bull-top-exit-signals-skill \
      trading-discipline-rules-skill ~/.agents/skills/
```

```powershell
# Windows
$pack = ".\dow-theory-skill\pack"
$dest = "$env:USERPROFILE\.agents\skills"
@('dow-theory-skill-router','primary-trend-identification-skill','dual-index-confirmation-filter-skill','secondary-reaction-assessment-skill','line-formation-reading-skill','bear-bottom-checklist-skill','bull-top-exit-signals-skill','trading-discipline-rules-skill') |
  ForEach-Object { Copy-Item -Recurse -LiteralPath (Join-Path $pack $_) -Destination $dest }
```

> `~/.agents/skills` is the DSH skills directory; with another agent, use its own skills directory (for example `~/.claude/skills` for Claude Code).

### How to verify the install

Ask: "The Shanghai Composite made a new high but Shenzhen did not follow — is that a breakout?" If the agent enters the three-state confirmation test of the dual-index filter (confirmed / awaiting confirmation / dismissed as illusion) instead of giving generic technical commentary, the install works. With the single build it reads the entry first and then routes to a card; with the pack build the matching capability is hit directly.

## Sources

- *The Dow Theory* by Robert Rhea
- Distilled from the whole book, producing 13 capability cards

## Notice

This repository publishes distilled skills, indexes and rule quick references only. It contains no PDF, EPUB, OCR files, screenshots or full-book transcripts of the source book. Quotations that appear in the capability cards serve solely to attribute methodology and keep the material auditable.

All numeric criteria in the book (3% net reversal, the 33%–66% retracement band, 5% line width, the 60–90 day bottom zone, 3% amplitude, consecutive new-high counts, stop and position conventions, etc.) are case- and experience-based rules without statistical backtesting, and every parameter is based on the US market of 1897–1931; re-estimate them for A-shares and declare the convention you use. Nothing in this repository is investment advice.

## License

[MIT](./LICENSE)

