# Market Scout Mentor

**Gated fair-value scouting for stocks and crypto.**

Market Scout Mentor is an AI skill that helps you find and evaluate potential value opportunities using sequential gates and explicit fair-value equations. It builds ranked survivor lists from your criteria (or an auto-scout), then opens detailed target cards only for the names you approve. The goal is a transparent, repeatable process that keeps you in control of what gets deeper analysis.

It works for both stocks and crypto, with style-aware logic for swing, long hold, or day trade. All calculations (fair-value price, modified fair-value price, modifiers, and gaps) are shown explicitly so you can follow and verify the reasoning.

---

## Purpose

Screening for value can be noisy and inconsistent. Market Scout Mentor gives you a structured flow:

- Ask for your bias, pace, size sleeve, and trading style up front.
- Run sequential gates that filter on dip, profit path (where applicable), and entry criteria.
- Rank survivors by fair-value gap.
- Present a clear table and open full target cards only for names you select.
- Keep every equation and modifier visible rather than hidden inside a black box.

The result is a short, ranked list of candidates with the math shown, so you can decide what (if anything) deserves further attention.

---

## Core Abilities

| Ability | What it does |
|---------|--------------|
| **Guided setup** | Asks bullish/bearish, conservative/aggressive, size sleeve, trading style (swing / long hold / day trade), and whether this is a back-test. Defaults are stated if you skip. |
| **Sequential gates** | Gate 1 (dip + size door), Gate 2 (profit-path cut on swing/long hold), Gate 3 (entry cut ranked by FVP gap). Day-trade logic is lighter and includes volatility fallbacks. |
| **Fair-value price (FVP)** | Slope-based floor for one share using market cap, actual trend slope, and a short-interest share factor. Formula and inputs are explicit. |
| **Modified fair-value price (MFVP)** | FVP adjusted by the true modifier (M). Target window follows style (six months, twelve months, or next close). |
| **Explicit modifiers** | M is the sum of scored contributors (trend, dividend, EPS, news). Caps and required lines are documented; day-trade uses a simpler set. |
| **Survivor table** | Ranked list with price, FVP, gap, slope, and M. You choose which names (or all, or a new list) receive full target cards. |
| **Target cards** | Detailed eval with MFVP, M table, band, and advice. Opened only for names you pass. |
| **Named evals** | Skip the gates and open cards directly for tickers or coins you name. |
| **List completion** | On swing or long hold, if finished entries are under three, searches for more rows that still clear the entry cut. |

---

## Why Use Market Scout Mentor

- **Structured instead of ad-hoc** — Sequential gates reduce noise before you spend time on deeper analysis.
- **You stay in control** — Target cards open only for names you approve.
- **Math is visible** — FVP, MFVP, modifiers, and gaps are calculated and shown, not buried.
- **Style-aware** — Swing, long hold, and day trade use appropriate candles, windows, and filters.
- **Works for stocks and crypto** — Separate but consistent logic for each.
- **Back-test friendly** — Can evaluate against a past date when requested.
- **Token-efficient hand-off** — Survivor table first; full cards only when you want them.

It is especially useful when you want a repeatable value screen rather than a one-off opinion or a raw watchlist.

---

## How to Install and Use with AI

### Quick Install
1. Open [`Market-Scout-Mentor.md`](Market-Scout-Mentor.md).
2. Copy the **entire** file.
3. Paste it into your AI as a system prompt, custom instructions, project knowledge, or skill upload.

### Activation Notes
- Loading the file does not force every response into scout mode.
- Start a run by describing what you want (e.g., “scout large-cap stocks,” “evaluate these tickers,” or “auto-scout for swing trades”).
- The skill will ask the setup questions if they are not already clear, then run the gates and present the survivor table.
- After the table, tell it which names (or “all” or “new list”) should receive full target cards.
- You can request style-window odds, more detail on a subset, or a Word file only if you ask.

### Practical Tips
- Be explicit about style (swing / long hold / day trade) and bias if you have a preference; otherwise the defaults are stated.
- Named tickers or coins skip the gates and go straight to cards.
- Review the survivor table before requesting full cards so you control token use and focus.
- The skill uses public sources (EDGAR, Yahoo Finance, etc.) and will note when data is missing or incomplete.

---

## Files

| File | What it contains | Best for |
|------|------------------|----------|
| [`Market-Scout-Mentor.md`](Market-Scout-Mentor.md) | Complete skill: setup questions, gate logic, fair-value equations, modifiers, flow, sources, and target-card rules. | Running scouts and evaluations. This is the only file you need to install. |

---

## License

MIT — free to use, modify, and share. See [`LICENSE`](LICENSE).

---

Questions or improvements welcome via issues or pull requests.