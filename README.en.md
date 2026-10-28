<h1 align="center">Dow Theory Skill</h1>

<p align="center"><a href="README.md">中文</a> | English</p>

An AI skill pack for immediate use — it distills Robert Rhea's *The Dow Theory (Professional Edition)* — the method that judges the stock market's primary trend from the behaviour of two average-price indices alone — into 13 capability cards that can be triggered individually or combined.

It is not a book summary, nor a reading response — it breaks the reusable methodology in the book into skill modules that can be triggered, executed and tested.

## What these skills solve

- Is this a bull market or a bear market right now? The index made a new high (or low) — is that a trend reversal or just another secondary movement?
- One index fired a signal and the other did not follow. Does it count — and when must an unconfirmed signal be filed away as an illusion?
- Is this pullback a secondary reaction or a trend reversal, and roughly how deep and how long do those run?
- The index has been moving sideways for two or three weeks — accumulation or distribution, and which way will it break?
- Should I liquidate at a bull-market top, and can I buy the bottom of a bear market — at which signal level do I scale out?
- Can I buy individual stocks while the broad market is weak; where does the stop go, should I average down, how big should the position be, and what annual return is realistic?

## What was distilled

13 capability cards, organized in the order "fix the direction first, verify the signal second, read the pattern and the stage third, and land on execution last":

- **Direction and confirmation**: `primary-trend-identification` (primary trend: high/low ladder + 3% net reversal + bull/bear reversal criteria), `dual-index-confirmation-filter` (two-index mutual confirmation: an unconfirmed signal is an illusion)
- **Nature of the move and consolidation patterns**: `secondary-reaction-assessment` (secondary reaction identification and magnitude: 33%–66% + speed asymmetry + completion sequence), `line-formation-reading` (narrow-range line reading: accumulation/distribution inference and breakout direction), `secondary-reaction-stat-baseline` (secondary-reaction statistics and data infrastructure: 35-year distribution expectations + record templates + divisor method)
- **Stage and position**: `bull-bear-stage-positioning` (bull/bear three-stage locator: locate by driver anchors and calibrate risk attitude), `bear-bottom-checklist` (bear-market bottom checklist: the nine-bear-market statistical portrait of Figure 1), `bull-top-exit-signals` (bull-market top signal grading and liquidation decision: the September–October 1929 specimen)
- **Volume-price and false signals**: `volume-price-health` (volume-price health: overbought/oversold and dull/active semantics), `pseudo-signal-troubleshooting` (false-signal and attribution troubleshooting: premise gates + anti-pattern checklist)
- **Execution and training**: `stock-preflight-market-check` (pre-flight broad-market check before any single-stock action: a foolproofing gate), `trading-discipline-rules` (trading discipline and money management: stops, position size, adding direction, return expectations), `forecast-self-training` (forecast self-training: cover-the-chart prediction — compare against Dow's columns — attribute the differences)

## Two packaging modes: single and pack

The same 13 capability cards are compiled twice, at two granularities. The content is identical; the only difference is how many entries an agent can discover.

| | single (one entry) | pack (compact pack, multiple entries) |
|---|---|---|
| Discoverable entries | **1**: `dow-theory-skill` | **8**: one source router + 7 promoted standalone skills |
| Where the 13 cards live | All inside the entry's `references/capabilities/`, loaded 1–2 at a time by the router table | 7 high-frequency cards become standalone skills; the other 6 stay in the router's `references/` |
| Triggering | Only the entry description participates in matching; routing happens after entry | The 7 high-frequency capabilities are matched directly, one hop fewer |
| Upgrades | Replace 1 directory | Replace 8 directories |

The 7 cards promoted to standalone skills in the pack:

- `primary-trend-identification-skill` — primary trend (high/low ladder + 3% net reversal + bull/bear reversal criteria)
- `dual-index-confirmation-filter-skill` — two-index mutual confirmation (an unconfirmed signal is an illusion)
- `secondary-reaction-assessment-skill` — secondary reaction identification and magnitude
- `line-formation-reading-skill` — narrow-range line reading (accumulation/distribution and breakout direction)
- `bear-bottom-checklist-skill` — bear-market bottom checklist
- `bull-top-exit-signals-skill` — bull-market top signal grading and liquidation
- `trading-discipline-rules-skill` — trading discipline and money management

The 6 cards left inside the router: `volume-price-health`, `bull-bear-stage-positioning`, `stock-preflight-market-check`, `pseudo-signal-troubleshooting`, `forecast-self-training`, `secondary-reaction-stat-baseline`.

### Which one to install

Pick by the way you work, and **install only one**:

| How you work | Recommended | Why |
|---|---|---|
| You use DSH / Codex / Claude Code with a skills directory and want a clean list | single | Takes 1 slot, loses no capabilities |
| Your daily questions concentrate on "bull or bear now / does this signal count / should I exit / can I buy the bottom" | pack | Those 4 are exactly the promoted standalone skills, matched directly |
| You distribute to several agents or teammates who pick what they need | pack | They can install only the standalone skills they want |
| You want to install once and maintain one directory | single | Upgrades replace a single directory |

> Both builds come from the same bundle and carry identical capabilities. **Installing both will double-trigger**, so pick one.

## Examples

### Example 1: one index made a new high and the other did not — is this a confirmed bull market?

**User question**

"The CSI 300 has cleared its previous high, but CSI All Share is still grinding below. Is the bull market confirmed? Can I add?"

**How the skill reasons**

- Enter `primary-trend-identification`: first slice the noise into legs of advance and decline using "a net change above 3% in either index", then record each index's highs and lows leg by leg to build the ladder
- Then `dual-index-confirmation-filter`: every new high in one index is first classified into one of three states — the other index followed (confirmed, trust it), not yet followed (wait, do nothing), never followed (file as illusion). Confirmation need not occur on the same day, or even in the same week
- Back to `primary-trend-identification` for the reversal criteria: bull-to-bear requires "no new high within a reasonable time + both indices below the prior secondary low"; bear-to-bull requires "no new low + both indices above the previous major rally high". Both are binary criteria, and a break in one index alone does not flip the call
- Finally state the falsification condition: which price behaviour would prove this call wrong

**Sample answer**

> Do not call it a confirmed bull market yet. By the rules, the CSI 300 clearing its prior high is a one-sided signal; while CSI All Share has not followed, the state is "awaiting confirmation" — the action there is to keep the prior call and leave the position alone, not to treat it as a reason to add. If CSI All Share never follows, the new high gets filed as an illusion. Confirmation is not required on the same day or in the same week, so "it did not follow today" is not by itself a refutation; what you need is a timeline: list each side's last valid high and low with dates and see whether the ladder is rising or falling. Two reminders: 3% is the discussion unit for slicing moves, not a trading threshold, and at high index levels it must be read as a percentage and loosened; and do not use a break in a single index to flip the bull/bear call. Adding to a position belongs to `stock-preflight-market-check` (single stock) and `trading-discipline-rules` (position size) — the trend card gives direction, never entry points.

### Example 2: down 8% from the high with each rally weaker — should I liquidate?

**User question**

"The index is 8% off its high and the last two rallies were weaker each time. Is this the top? Should I liquidate?"

**How the skill reasons**

- Enter `bull-top-exit-signals`: the card never predicts a level, it grades signals — first check the precursors (volume persistently rising while price barely advances, i.e. "over-activity"; high call-money rates; junk stocks soaring; leaders yielding less than bonds)
- Treat the first decline after the top as a secondary reaction, and start logging every rally's high and its volume (this step cross-reads `secondary-reaction-assessment`)
- Check the deterioration sequence: are rally highs stepping down, and is volume shrinking on rallies while expanding on declines (the divergence evidence comes from `volume-price-health`, and volume always ranks behind the index)
- Confirmation trigger: only a break of the prior low confirmed by the other index moves the call to the first stage of a bear market and to staged liquidation; a break in one index alone is handled as an illusion by `dual-index-confirmation-filter`, and no liquidation call is issued
- Output two-sided thresholds: above which level the bearish implication is retracted, below which level it strengthens

**Sample answer**

> "Down 8% with weakening rallies" does not support a liquidation call — it only raises the signal level one notch. In the card's order: first, have you checked the precursors — volume rising with little price progress, junk stocks soaring, leaders yielding less than bonds; second, treat the first post-top decline as secondary and log every rally's high and volume to see whether they really are stepping down on shrinking volume; third, and most important, a break must be confirmed by both indices — when only one index breaks its prior low, handle it as an illusion, neither cut the position nor short. If you do cut, cut in stages: each signal level maps to a position level, not one clean sweep. Also note that the 1929 specimen's "about 10% below the peak constitutes a clear liquidation signal" is a case judgement at that index level, not a general formula — do not bolt it onto today's index as a stop. Top signals are inherently late; that is the system's admitted cost, absorbed by staged reduction rather than by guessing the high.

## How these skills were generated

This skill pack was produced with the RIA-TV++ pipeline of **[cangjie-skill](https://github.com/kangarooking/cangjie-skill)**, in six stages:

1. **Whole-book understanding (Adler analysis)** — Mortimer Adler's analytical reading method applied in four steps (structural, interpretive, critical, applicational), producing `BOOK_OVERVIEW.md` and a list of 12 reader tasks
2. **Parallel extraction** — several specialized extractors (frameworks, principles, cases, counter-examples, terminology) work simultaneously to pull candidate methodology units out of the text
3. **Triple-verification screening** — every candidate must pass three tests: at least two independent corroborations in the book (cross-domain), the power to answer questions the book never states (predictive power), and not being common sense (uniqueness). In this round the V2 verification was a paper walkthrough; the conclusions are logged in `verified.md`
4. **RIA++ construction** — each card is structured along six dimensions: R (source quotation), I (rewritten in one's own words), A1 (in-book case), A2 (future trigger scenarios), E (executable steps), B (boundaries and blind spots)
5. **Zettelkasten linking** — dependency, contrast and composition relations between cards are mapped into a capability index and a router table; the `also_read` field is the output of this stage and is summarized in `INDEX.md`
6. **Trigger and output testing** — trigger blind tests (including decoys: fire when it should, stay silent when it should not) and output evaluation scenarios are designed per card; failing cards go back for rework and are re-verified afterwards

## Testing and verification

This repository ships the test material from the generation process: `evals/` holds 13 trigger prompt files (`test-prompts__<slug>.json`) and three per-item scoring reports, including the failures and the rework, not just the passes.

- **Trigger and boundary cases**: 127 in total (9–10 per card: should_trigger, should_not_trigger decoys, edge_case). Triggers 56 / 57, decoys 38 / 39, edge cases 31 / 31
- **One decoy violation**: `bull-top-exit-signals` snt-03 was routed to a neighbouring card — recorded as it happened, not polished
- **Output evaluation**: 13 units × normal / boundary scenarios, mechanical assertions 115 / 115 passed
- **Stop conditions**: all 13 stop points passed — refuse when refusal is right, ask when asking is right, never force a conclusion
- **No-skill baseline**: 13 same-question comparisons without the skill, recording where the cards produced directional differences (e.g. "blue chips resist declines" vs "quality stocks are more fragile", "do not enter while unconfirmed" vs "probe with a small position")

> A limitation worth stating: the trigger judgements in those three reports are **main-flow fallback self-assessments**, not independent blind tests, and each report says so. Output evaluation and stop conditions are assertion-style checks and are less affected by that bias. Once a sub-agent is available, re-run an independent blind test using `evals/test-prompts__*.json` unchanged.

## Repository structure

```text
dow-theory-skill/
├── README.md                      ← the Chinese original
├── README.en.md                   ← you are reading this
├── LICENSE                        ← MIT
├── BOOK_OVERVIEW.md               ← whole-book understanding (Adler four-step, stage 0 output)
├── verified.md                    ← triple-verification conclusions for the 13 capability units
├── INDEX.md                       ← skill map: capability table / dependencies / loading order
├── TEST_SUMMARY.md                ← stage 4 stress-test summary (scope / structure check / results / next actions)
├── CANGJIE_ADAPTATION.md          ← Cangjie adaptation notes (text state / distillation goals / evidence rules / boundaries)
├── candidates/                    ← stage 1 candidate methodology units (5 categories, 201 items)
│   ├── framework.md               ← framework candidates, 21
│   ├── principle.md               ← principle candidates, 90
│   ├── case.md                    ← case candidates, 42
│   ├── counter-example.md         ← counter-example candidates, 22
│   ├── glossary.md                ← terminology candidates, 26
│   ├── verified-A.yaml            ← triple-verification results: frameworks + terminology (47)
│   ├── verified-B.yaml            ← triple-verification results: principles (90)
│   └── verified-C.yaml            ← triple-verification results: cases + counter-examples (64)
├── bundle/                        ← compilation source: cards and verification manifest
│   ├── verified.yaml              ← canonical definition of the 13 cards (title, intents, importance, destination, also_read)
│   ├── cards/                     ← the 13 capability cards (six RIA++ sections)
│   └── book/                      ← overview.md (condensed whole-book view), glossary.md (terminology)
├── single/                        ← single-entry mode
│   └── dow-theory-skill/
│       ├── SKILL.md               ← entry: trigger conditions + router table + loading rules
│       ├── BUILD_MANIFEST.json    ← build manifest and file hashes
│       └── references/
│           ├── overview.md        ← whole-book overview
│           ├── capability-index.md  ← full intent and keyword index
│           ├── cheatsheet.md      ← decision-rule quick reference
│           ├── glossary.md        ← glossary
│           └── capabilities/      ← the 13 capability cards
├── pack/                          ← multi-entry mode (compact pack)
│   ├── BUILD_MANIFEST.json
│   ├── capability-destinations.json
│   ├── dow-theory-skill-router/
│   │   ├── SKILL.md               ← source router entry
│   │   └── references/            ← the 13 cards + indexes, loaded by the router
│   ├── primary-trend-identification-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (10)
│   ├── dual-index-confirmation-filter-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (10)
│   ├── secondary-reaction-assessment-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (10)
│   ├── line-formation-reading-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (10)
│   ├── bear-bottom-checklist-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (9)
│   ├── bull-top-exit-signals-skill/
│   │   ├── SKILL.md
│   │   └── test-prompts.json      ← trigger cases for this card (9)
│   └── trading-discipline-rules-skill/
│       ├── SKILL.md
│       └── test-prompts.json      ← trigger cases for this card (10)
└── evals/                          ← trigger cases and per-item scoring reports
    ├── test-prompts__primary-trend-identification.json
    ├── test-prompts__dual-index-confirmation-filter.json
    ├── test-prompts__secondary-reaction-assessment.json
    ├── test-prompts__line-formation-reading.json
    ├── test-prompts__volume-price-health.json
    ├── test-prompts__bull-bear-stage-positioning.json
    ├── test-prompts__bear-bottom-checklist.json
    ├── test-prompts__bull-top-exit-signals.json
    ├── test-prompts__stock-preflight-market-check.json
    ├── test-prompts__trading-discipline-rules.json
    ├── test-prompts__forecast-self-training.json
    ├── test-prompts__secondary-reaction-stat-baseline.json
    ├── test-prompts__pseudo-signal-troubleshooting.json
    ├── test-results-u01-u05.md    ← per-item scoring and failure/rework records
    ├── test-results-u06-u09.md
    └── test-results-u10-u13.md
```

## How to use

Clone the repository first:

```bash
git clone https://github.com/raphael-y7/dow-theory-skill.git
```

### Install single (try this one first)

```bash
# macOS / Linux
cp -r dow-theory-skill/single/dow-theory-skill ~/.agents/skills/
```

```powershell
# Windows
Copy-Item -Recurse .\dow-theory-skill\single\dow-theory-skill "$env:USERPROFILE\.agents\skills\"
```

### Install pack

Copy only the directories that contain a `SKILL.md`, and do not drag the two json files under `pack/` into your skills directory:

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

> `~/.agents/skills` is the DSH skills directory; with another agent, use its own skills directory (Claude Code, for example, uses `~/.claude/skills`).

### How to confirm it is installed

Ask "the CSI 300 cleared its prior high but CSI All Share did not follow — is this a confirmed bull market?" and see whether the agent goes straight into the "three-state single-index signal check + high/low ladder" procedure instead of giving you a generic market commentary. With single installed it reads the entry first and then follows the router table into a card; with pack installed the matching capability is hit directly.

## Source

- *The Dow Theory (Professional Edition)* by Robert Rhea

## Disclaimer

This repository publishes only the distilled skills, indexes and quick-reference rules. It contains no PDF, EPUB, OCR files, screenshots or full-book transcript. Quotations inside the capability cards serve solely to attribute the methodology and keep it auditable.

Every numeric criterion in the book (3% net reversal, 5% line width, the 33%–66% retracement range, the 60–90 day bottom duration, the "10% below the peak" liquidation yardstick, and so on) is a case-based or experience-based generalisation; the book offers no statistical backtest in support. Its parameters come from the 1897–1931 US market, so re-estimate them with new data before applying them to A-shares, and state the convention you used. Nothing in this repository is investment advice.


## License

[MIT](./LICENSE)
