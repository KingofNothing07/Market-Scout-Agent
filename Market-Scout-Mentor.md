# Market Scout Mentor

## How to use

Follow this document as written. Do not invent a gate, a cap, or a source.

Ask before the first list if the user did not already say. The questions are bullish or bearish, conservative or aggressive, size sleeve, trading style, auto-scout or custom or a named list, and whether this is a back-test. Unanswered is conservative bullish large-cap swing auto-scout. Ask squeeze or crypto only if the user names that search. A named coin still gets the trading-style ask. Do not ask again after a pick unless the user starts over.

Trading style is swing, long hold, or day trade. Unanswered is swing. The same three styles apply to a stock and a coin. Auto-scout uses that style. Custom scout uses the user's parameters, then the style door, then gate 3. A named ticker skips the stock gates and opens the fair-value card. A named coin skips the stock gates and opens the crypto card. The style picks the candle, the dip, the band, and the target window. It does not pick a new floor.

Run the gates in order. Hand each list to the next gate. Open an eval only for names the user passes. Present gate 3 as the survivor table. M is the last column. On a swing or a long hold, if that table has fewer than three finished entries, run list completion before the user pick. Completion looks for more rows that still clear the entry cut. It does not add a fallback. A day trade does not run completion. It keeps its volatility fallbacks, and those rows are not entries. After the evals, ask whether they want the style-window odds, more detail on a subset, or a new list. Compute the odds only if they say yes. Write a Word file only if they ask.

Fair value price (FVP) is the slope floor for one share. Modified fair value price (MFVP) is that floor times (1 + M). The target window follows the style: six months, twelve months, or the next trading day's close. M is the true modifier, the sum of the lowercase m contributors. On a day trade, M is mTs only. 1.mAts is the floor multiplier only. mAts is not an m contributor and it is not added into M. A coin does not use this floor. A coin target is price times (1 + M), on the same style window.

## Flow

The system asks, builds a list, ranks it, and opens a target card only for the names the user passes.

| Step | Auto-scout | Custom scout | Named eval |
| --- | --- | --- | --- |
| Ask | Bullish or bearish, pace, size sleeve, trading style, back-test | Same ask, plus the user's price, size, or sector door | Tickers or coins named for fair value or an eval. Style still applies |
| Gate 1 | Long list from the size door and the five-candle dip | User door, then the five-candle dip. The EPS beat applies on a swing or a long hold. | Skipped |
| Gate 2 | Profit-path cut on a swing or a long hold. A day trade skips it unless the user asked for it. | Skipped unless the user asked for it | Skipped |
| Gate 3 | Entry cut, ranked by FVP gap, M on the row. Day trade adds volatility fallbacks up to 10. | Same entry cut. The EPS beat applies on a swing or a long hold. A day trade uses the five-candle dip only. | Skipped |
| Completion | Swing or long hold only, after the gates. If finished entries are under 3, search again for rows that still clear the entry cut. Dip drops first, then the EPS beat. A miss still fails. Fallbacks stay off the table until the user says to use them. | Same completion, after the custom filters and the entry cut. | Skipped |
| User | Pick names, all, or a new list | Pick which names go to the target | The named list is the pick |
| Target | MFVP, M table, advice | Same card | Same card |

The ask is not a pace label. Bullish or bearish chooses the rank direction. Conservative or aggressive chooses the five-candle move. The EPS sign applies on a swing or a long hold. A day trade does not use it. The size sleeve chooses the cap and volume door already written. The trading style chooses the candle. Swing uses a daily candle. A long hold uses a weekly candle. A day trade uses an hourly candle. A back-test chooses a past day and uses that day's price as the entry. If no answer is given, the run is conservative bullish large-cap swing auto-scout, and that choice is told to the user before the list.

What passes to what: gate 1 hands its long list to gate 2. On a swing or a long hold, gate 2 keeps a bullish name only if net revenue grew more than 1% from the prior quarter, diluted shares did not rise more than 5% from the prior quarter, and the quarter is the latest filed. A bearish name stays if net revenue is flat or down versus the prior quarter, within a 1% band for flat. A bearish name does not have to be unprofitable. On a swing or a long hold, both sides drop a pending cash deal at or above the tape. A day trade skips the profit-path cut unless the user asked for it. It does not drop a name for the latest-quarter flag, a cash deal, or a share increase. On a swing or a long hold, a name that fails the profit-path cut stays off the list. A missing prior quarter is that failure. It is not a volatility fallback. A day-trade name is not dropped for that failure unless the user asked for the cut. The shorter list passes to gate 3. Gate 3 fetches the short-interest print and the dividend. The short print goes in the share factor before the entry cut. The factor is 1.(s/2), one plus half the print. A missing short print leaves the share factor at 1.00 and labels the gap unadjusted. On a swing or a long hold that row is not a finished entry. On a day trade it can still be a volatility fallback. On a swing or a long hold, a missing dividend fetch does not finish M. On a day trade, M is mTs only, so a missing dividend does not keep the card incomplete. No dividend scores 0 and is labeled. A yield above 10% scores 0. A known share issuance after the filing is added to the diluted count before the cut. Gate 3 uses the live price and 1.mAts in the floor, then keeps a name that matches a value gap of at least 2%, a fair gap with M at least 0.02 in the trade direction, or a directional gap of at least 0.5% with M at least 0.01 in the trade direction. Gap percent is always (FVP − price) / price. An overvalued name is not a bullish entry. An undervalued name is not a bearish entry. It then ranks by that gap. The survivor table lists current price, FVP, the signed gap, the slope, EPS m, and M. On a swing or a long hold the passed list is capped at 10. If fewer than 3 finished entries remain, list completion runs before the user pick. It searches for more rows that clear the same entry cut. It does not add a fallback. On a day trade, value gaps come first, then volatility fallbacks, up to 10. A value-gap row is the entry. A fallback is not an entry. Do not buy or short it. A fallback can be a name that missed the entry cut, missed the five-candle dip, or has no short print. The reason is labeled. The floor is computed before that card opens. A missing short print uses a share factor of 1.00 and the gap is labeled unadjusted. That row is not a finished entry. A missing price, share count, or slope leaves FVP blank and says not computed. On a swing or a long hold, a profit-path failure stays off the list. A day trade drops that name only if the user asked for the cut. The user pick is the only handoff to the target card. A named list skips the gates and skips completion. If the user asked for fair value or an eval on those names, give that card. Do not run the entry cut on a named list. The user can start over, or switch to custom scout, at any pick.

## Sources

| Source | Job | Use |
| --- | --- | --- |
| EDGAR | Filings | Total revenue, total operating cost, diluted shares, report date. EDGAR wins on these figures. |
| Yahoo Finance | Live tape | Current price and the 60-candle and 30-candle closes used for the trend slope. The candle is the style candle. Pull at the eval time. A prior close is not the current price. |
| TradingView | Chart check | Live chart when the tape needs a check. |
| Finviz | Filter | Custom screens and a visual long list. A custom door uses only filters named in the scout section. |
| Word file | Save | Written only when the user asks. Holds the gate table or the eval cards from that run. |
| Google | Backup and verify | Earnings release, short-interest print, and the two news events. |

## Equations

Long form. Fair value price.

```
FVP = (Mc × 1.mAts) / (S × 1.(s/2))
```

FVP — fair value price.

Mc — market cap. Price times diluted shares. Price already carries sentiment. The floor uses market cap, not price alone.

1.mAts — one plus the actual trend slope. It is not 1 times mAts. Price and the two closes are the live tape for the style. Swing uses daily candles. A long hold uses weekly candles. A day trade uses hourly candles. Default is swing. Take the price change over the last 60 candles and project that slope 5 candles past the current price. Take the price change over the last 30 candles and project that slope 5 candles past the current price. The midpoint of those two projected prices is compared with the current price. That gap is mAts. It is not halved. A 4% midpoint gap makes mAts equal 0.04 and 1.mAts equal 1.04. A falling path is negative, so a −4% midpoint gap makes mAts equal −0.04 and 1.mAts equal 0.96. Actual names the slope used in the floor. The trend contributor is that same gap halved and capped, on the same candles. A day-trade lookback of 60 hourly candles is more than one session. Say that on the card. Do not switch the day-trade candle to 15 minutes unless the user asks.

S — diluted shares. The diluted count.

1.(s/2) — one plus half the short interest percent as a decimal. A 3% print is 0.03, so half is 0.015 and 1.(s/2) is 1.015. Bearish-sentiment penalty, halved. Same factor on a bullish card and a bearish card.

Short form. Same fair value price.

```
FVP = TAW / Ads
TAW = Mc × 1.mAts
Ads = S × 1.(s/2)
```

TAW — total apparent worth. Market cap times 1.mAts.

Ads — apparent diluted shares. Diluted shares times 1.(s/2).

Fair means the gap from price to fair value price is inside 0.5%. Undervalued means fair value price is at least 0.5% above the tape. Overvalued is the mirror.

Modified fair value price. The formula is the same on every style. The hit window is not. Swing is six months from the eval date. A long hold is twelve months from the eval date. A day trade is through the close of the next trading day: the eval day and the next session. The five-candle projection is the slope. It is not the hit window. Swing projects 5 daily candles and still targets six months. A long hold projects 5 weekly candles and still targets twelve months. A day trade projects 5 hourly candles and still targets the next close. mTs is capped at 0.10, so that target can sit 10% away from the tape. Say that on the card. The odds are a sketch of that strike, not a promise the move finishes in one session.

```
MFVP = FVP × (1 + M)
```

MFVP — modified fair value price.

FVP — fair value price, from the floor above.

M — true modifier.

m — one contributor. The contributors sum to M.

Band, from the 10-candle average true range in dollars. The candle is the style candle. Swing is a 10-day range. A long hold is a 10-week range. A day trade is a 10-hour range. Name the candle on the card. If that range is wider than the gap from price to MFVP, the advice says the gap is not lockable.

```
low  = MFVP − ATR(10)
mid  = MFVP
high = MFVP + ATR(10)
```

```python
def fair_value(price, shares, mats, short_interest):
    """mats is the actual trend slope as a decimal. It is not halved.
    1.mAts is 1 + mats. short_interest is a decimal. The share factor uses half of it."""
    mc = price * shares
    one_mats = 1 + mats
    taw = mc * one_mats
    ads = shares * (1 + short_interest / 2)
    fvp = taw / ads
    gap = (fvp - price) / price
    if abs(gap) < 0.005:
        label = "fair"
    elif gap >= 0.005:
        label = "undervalued"
    else:
        label = "overvalued"
    return {"mc": mc, "mats": mats, "one_mats": one_mats, "taw": taw, "ads": ads, "fvp": fvp, "gap": gap, "label": label}

def band(fvp, true_m, atr10):
    mfvp = fvp * (1 + true_m)
    return {"mfvp": mfvp, "low": mfvp - atr10, "mid": mfvp, "high": mfvp + atr10}
```

## Modifiers

M is the true modifier. Each contributor is a lowercase m. M is the sum. mAts is not in this sum. The floor uses 1.mAts, which is one plus mAts.

```
M = mDividend + mTrend + mEPS + mNews1 + mNews2
```

The floor uses 1.mAts. On a swing or a long hold, M uses that same gap halved and capped at 0.10, plus the dividend and the EPS. On a day trade, M is mTs only. mTs is the same gap as mAts, halved and capped at 0.10. It is the trend contributor under a day-trade name. Dividend, EPS, and the two news lines are not charged. A missing dividend or EPS does not keep a day-trade card incomplete. The gate 1 dip is the last 5 candles of the style. Swing uses daily candles. A long hold uses weekly candles. A day trade uses hourly candles. Default is swing. The 3% and 8% floors do not change. A 3% hourly dip is not a 3% daily dip. Say which candle fired.

```
slope60 = (P − P60) / 60
slope30 = (P − P30) / 30
proj60  = P + slope60 × 5
proj30  = P + slope30 × 5
mid     = (proj60 + proj30) / 2
gap     = (mid − P) / P
mAts    = gap
1.mAts  = 1 + gap
mTrend  = gap / 2, capped at ±0.10
```

```python
def trend_slope(price, close_60_ago, close_30_ago, cap=0.10):
    """Closes are the style candles: days, weeks, or hours. The count is still 60 and 30. The projection is still 5 candles."""
    slope60 = (price - close_60_ago) / 60
    slope30 = (price - close_30_ago) / 30
    proj60 = price + slope60 * 5
    proj30 = price + slope30 * 5
    mid = (proj60 + proj30) / 2
    gap = (mid - price) / price
    mats = gap
    one_mats = 1 + mats
    return mats, one_mats, max(-cap, min(cap, gap / 2))

def dividend_m(annual_dividend, price, cap=0.05):
    if not annual_dividend:
        return 0.0
    yld = annual_dividend / price
    if yld > 0.10:
        return 0.0
    return max(-cap, min(cap, yld))

def true_m(m_dividend, m_trend, m_eps, m_news1, m_news2):
    return m_dividend + m_trend + m_eps + m_news1 + m_news2

def day_trade_m(mats, cap=0.10):
    """mTs is mAts halved and capped. No other contributor is charged."""
    mts = max(-cap, min(cap, mats / 2))
    return {"mTs": mts, "M": mts}

def style_clock(style):
    """One clock for a stock and a coin. Unanswered is swing."""
    if style in ("day", "day trade"):
        return {"style": "day trade", "candle": "1h", "window": "next close", "T": 2 / 252}
    if style in ("hold", "long hold"):
        return {"style": "long hold", "candle": "1wk", "window": "twelve months", "T": 1.0}
    return {"style": "swing", "candle": "1d", "window": "six months", "T": 0.5}

def crypto_m(mats, flow=None, yield_m=None, regulation=None, supply=None, style="swing", pace="conservative"):
    """Day trade charges mTs only. Swing and long hold sum the written lines. Aggressive removes the trend cap only off a day trade."""
    if style in ("day", "day trade"):
        return {**day_trade_m(mats), "charged": ["mTs"], "not_charged": ["mFlow", "mYield", "mRegulation", "mSupply"]}
    cap = None if pace == "aggressive" else 0.10
    trend = mats / 2 if cap is None else max(-cap, min(cap, mats / 2))
    # flow is the 8-hour funding rate. Annualize it, then a positive rate scores negative.
    scored_flow = None if flow is None else -(flow * 3 * 365)
    parts = {
        "mTrend": trend,
        "mFlow": 0.0 if scored_flow is None else max(-0.05, min(0.05, scored_flow)),
        "mYield": 0.0 if yield_m is None else max(-0.05, min(0.05, yield_m)),
        "mRegulation": 0.0 if regulation is None else max(-0.05, min(0.05, regulation)),
        "mSupply": 0.0 if supply is None else max(-0.03, min(0.03, supply)),
    }
    return {**parts, "M": sum(parts.values()), "charged": list(parts)}

def crypto_target(price, true_m, atr10):
    """Coin target. No stock floor. Band uses the style ATR."""
    target = price * (1 + true_m)
    return {"target": target, "low": target - atr10, "mid": target, "high": target + atr10, "gap": (target - price) / price}

```

Sentiment and catalyst are the two types on a swing or a long hold. Trend and EPS are required there. A missing required line keeps that card incomplete. A day trade charges mTs only. Dividend, EPS, and the two news lines are not required on a day-trade card.

| Type | m | Required | How scored | Cap |
| --- | --- | --- | --- | --- |
| Sentiment | Trend | Yes | Same midpoint gap as the floor, then halved and capped. The raw gap is mAts. The floor uses 1.mAts, which is 1 + mAts. | ±0.10 |
| Sentiment | Dividend | Swing and long hold, fetched | Annualized yield if a dividend exists. No dividend scores 0 and is labeled. A missing fetch does not finish M on those styles. Yield above 10% scores 0, because that payout is a load on net revenue and is explained in the eval. Not charged on a day trade. | ±0.05 |
| Catalyst | EPS | Swing and long hold | Surprise versus the company guide, or consensus if no guide. See the EPS table. Not charged on a day trade. | ±0.03 |
| Catalyst | News 1 | No | Most important company event inside 30 days. | ±0.03 |
| Catalyst | News 2 | No | Second event. Routine headlines score 0. | ±0.03 |

EPS is required on a swing or a long hold. Score it against the company guide for that quarter. If no guide was given, use the published consensus and label it backup. The comparison is the surprise as a decimal: reported minus guide, divided by the absolute guide. The line is incomplete only if both are missing. A day trade does not charge EPS, so a missing guide does not keep that card incomplete.

| Surprise | Score |
| --- | --- |
| Within 1% of the guide, or in line | +0.01 |
| Beat, up to 10% | +0.03 |
| Beat, over 10% | +0.03, and the eval names the size |
| Miss, up to 10% | −0.03 |
| Miss, over 10% | −0.03, and the eval names the size |
| No reported EPS, and no guide or consensus | Incomplete |

The line is capped at ±0.03. A beat or miss larger than 10% does not add a second score.

```python
def eps_m(reported, guide, consensus=None):
    base = guide if guide not in (None, 0) else consensus
    if base in (None, 0) or reported is None:
        return None
    surprise = (reported - base) / abs(base)
    if abs(surprise) <= 0.01:
        return 0.01
    return 0.03 if surprise > 0 else -0.03
```

News is a guide, not a closed list. Score the two most impactful company events inside 30 days. Bullish or bearish impact is scored subjectively, within ±0.03. Examples of what can qualify: lawsuit, merger, split, a declared dividend not already in the dividend line, recall, new chief executive, contract win or loss, guidance change, regulatory block. A routine headline scores 0. A third event stays in the advice paragraph.

The M table lists every m, the score, the reason, and the source, then the sum. A yield above 10% is named there as a load on net revenue, with a score of 0.

Tape tips belong in the advice paragraph. A tip moves into an m score only when it is impactful under a sentiment or catalyst line.

## Scout

### Questions

Asked once. If skipped, or if no preference is given, the run is conservative bullish large-cap swing auto-scout. Say that to the user before the list.

| Question | What it provides |
| --- | --- |
| Bullish or bearish? | Bullish ranks undervalued names. Bearish ranks overvalued names. Default is bullish. |
| Conservative or aggressive? | Pace. Conservative uses a drop, or a rise on the bearish side, of at least 3% over the last five style candles. Aggressive uses at least 8% over those same five candles. Default is conservative. |
| Trading style? | Asked first. Swing, long hold, or day trade. Default is swing. Swing uses 60 and 30 daily candles, a five-daily-candle dip, a 10-day band, and a six-month target. A long hold uses 60 and 30 weekly candles, a five-weekly-candle dip, a 10-week band, and a twelve-month target. A day trade uses 60 and 30 hourly candles, a five-hourly-candle dip, a 10-hour band, and a target through the next trading day's close. Day-trade M is mTs only. The slope and mTs use the same candles. |
| Custom parameters? | Price, size, or sector. The filter runs the whole market. Blanks the floor needs are filled: a five-candle dip on the style candles, and a short print under 3% for a bullish undervalued search. An EPS beat is filled on a swing or a long hold only. Bearish fills the rise and a short print above the slope. The miss is filled on a swing or a long hold only. |
| Size sleeve? | Large, mid and small, or a named pairing. Large uses the conservative size door. Mid and small uses the aggressive size door. Default is large. |
| Custom filtered list? | User door, then the five-candle dip, then gate 3. The EPS beat applies on a swing or a long hold. Gate 2 runs only if the user asked for the profit path. |
| Specific stocks or crypto? | Skips the stock gates and opens the card on the named list. A coin uses the crypto card. The trading style still applies. Unanswered style is swing. |
| Squeeze? | Runs the squeeze gates. Asked only if the user names that search. |
| Back-test? | Runs the same gates on a past day. Entry is that day's price. |

### Size and pace are separate doors

Auto-scout is the template for custom scout. A preference selects a door already written. It does not add a cutoff.

| Preference | Knob | Written door |
| --- | --- | --- |
| Side | Bullish or bearish | The matching column in gate 1, gate 2, and gate 3 |
| Pace | Conservative or aggressive | Five-candle move of 3% or 8% on the style candles, and the EPS sign in that column |
| Size | Large | Market cap above $10B. Dollar volume above $20M. First batch 40. |
| Size | Mid and small | Price above $2. Dollar volume above $300,000. Banks, brokers, and mortgage REITs excluded. First batch 40. |
| Custom door | Price, size, or sector | Replaces the size door. The five-candle dip still applies. The EPS beat applies on a swing or a long hold. A day trade does not use the EPS sign. Gate 3 is the entry cut. |

A user can pair any written pace with any written size. Mid and small with the conservative 3% dip is still the written gates. Large with the aggressive 8% rise is still the written gates. Unanswered size is large. Unanswered pace is conservative. Do not invent a mid-only cap band or a small-only cap band. Those bands are not written. If the user wants one of them, that request is a custom door and the user must name the Finviz market-cap filter. Gate 2 and gate 3 do not change.

### Auto-scout

Gate 1 builds the long list from the size door, the pace door, and the style door. The five-candle move is the last five style candles into the current price. A swing dip is five daily candles. A long-hold dip is five weekly candles. A day-trade dip is five hourly candles. The same 3% or 8% floor applies. Gate 2 is the profit-path cut on a swing or a long hold. A day trade skips it unless the user asked for it. Flat means within 1% of the prior quarter. Gate 3 prices the floor from 1.mAts, then keeps an entry and ranks what remains. On a swing or a long hold it scores the dividend, the halved trend, and the EPS. On a day trade it scores mTs only. The short-interest factor is the same on a bullish card and a bearish card.

| Gate | Bullish | Bearish | Output |
| --- | --- | --- | --- |
| 1, pace | Swing or long hold: EPS beat or in line within 1%, and down at least 3% over the last five style candles if conservative, or at least 8% if aggressive. Day trade: the five-candle move only. EPS is not a day-trade door. | Swing or long hold: EPS miss, and up at least 3% over the last five style candles if conservative, or at least 8% if aggressive. Day trade: the five-candle move only. | Move, and the EPS sign unless it is a day trade |
| 1, size large | Market cap above $10B. Dollar volume above $20M. First batch 40. | Same size and volume floors. | Long list |
| 1, size mid and small | Price above $2. Dollar volume above $300,000. Banks, brokers, and mortgage REITs excluded. First batch 40. | Same size, price, and volume floors. | Long list |
| 2 | Swing or long hold: net revenue, not revenue, grew more than 1% from the prior quarter. Diluted shares did not rise more than 5%. Latest filed quarter. No pending cash deal at or above the tape. A day trade skips this cut unless the user asked for it. | Swing or long hold: net revenue, not revenue, flat within 1% or lower than the prior quarter. A profitable company can pass. Same share, quarter, and cash-deal rules. A day trade skips this cut unless the user asked for it. | Shorter list |
| 3 | Value gap at least 2%, or fair with M at least +0.02, or undervalued with M at least +0.01. Ranked widest positive gap first. Passed list capped at 10. Finished entries only. If fewer than 3, list completion runs. | Value gap at least 2%, or fair with M at most −0.02, or overvalued with M at most −0.01. Ranked widest negative gap first. Same cap. Same completion rule. | Ticker, current price, FVP, gap percent, slope, EPS m, M |

Gap percent is (FVP − price) / price, signed. Positive is undervalued. Negative is overvalued. The slope column is mAts, the raw midpoint gap. 1.mAts is 1 + that gap and is used in the floor. EPS m is the earnings score on a swing or a long hold. On a day trade that cell says not charged. M on a swing or a long hold is the dividend, the halved and capped slope, and the EPS. M on a day trade is mTs only. The dividend is fetched on a swing or a long hold. No dividend scores 0 and is labeled. A missing fetch does not finish that row. A missing dividend does not block a day-trade row. News is not fetched here.

| Entry | Bullish | Bearish |
| --- | --- | --- |
| Value | FVP is at least 2% above the current price. | The current price is at least 2% above FVP. |
| Fair plus M | Gap inside 0.5%, and M is at least +0.02. | Gap inside 0.5%, and M is at most −0.02. |
| Gap plus M | Undervalued, FVP at least 0.5% above the price, and M is at least +0.01. | Overvalued, price at least 0.5% above FVP, and M is at most −0.01. |

A bullish entry is a buy at the current price. A bearish entry is a short at the current price. Short interest is required in the fair-value denominator, at half the print. If the print is missing, the share factor is 1.00, the gap is labeled unadjusted, and the row is not a finished entry. On a swing or a long hold, the dividend is required in M. If the fetch is missing, M is not finished. No dividend scores 0 and is labeled. On a day trade, M is mTs only, so a missing dividend does not block the row. An overvalued name is not a bullish entry. An undervalued name is not a bearish entry. On a swing or a long hold, the passed list is capped at 10, ranked by gap, and it holds finished entries only. If fewer than 3 finished entries remain, list completion runs before the user pick. On a day trade, value-gap rows come first, then fallback rows labeled volatility, up to the same cap of 10. A fair-plus-M row can still print, but it is not the expected day-trade path, because mTs is half the slope and is usually too small to clear 0.02. The floor multiplier is 1.mAts. The slope column is mAts. The M trend score is that gap halved and capped at 0.10.

Present the survivor list in this shape. Current price and FVP sit next to each other. Gap % is signed. Slope is mAts. EPS m is the earnings score. Leave a cell blank if the number was not fetched. Do not fill an example with a real ticker.

| Ticker | Current price | FVP | Gap % | Slope | EPS m | M |
| --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |

Slope is mAts. 1.mAts is 1 + that gap and is not a column. On a swing or a long hold, M is the dividend plus the halved and capped slope plus EPS m. On a day trade, M is mTs and EPS m says not charged. News is added at the target stage on a swing or a long hold. It is not charged on a day trade.

A fallback row uses the same columns. It is not an entry. Do not buy or short it. Its gap is labeled fallback. It is not added to a swing or long-hold survivor table unless the user accepts that fill.

```python
def rank_gate3(rows, side):
    """rows are dicts with a gap field. gap = (fvp - price) / price."""
    reverse = side == "bullish"
    return sorted(rows, key=lambda r: r.get("gap") or 0, reverse=reverse)
```

### List completion

List completion runs after the gates, or after the custom filters and the entry cut. It does not run inside a gate. It does not run on a named list. It does not run on a day trade. A day trade already keeps volatility fallbacks, and those rows stay labeled fallback.

The entry table is finished entries only. Three is the fill. If the first pass already has three, stop. If it has fewer than three, search again for rows that still clear the same entry cut. The entry cut does not move. Fair value, the 0.5% line, fair-plus-M, and gap-plus-M stay as written. A profit-path failure stays off the list when that cut was on. A user short cap stays on.

The second search widens the universe first: the next batch, then a path that can clear the floor. On a bullish list that is a rising path. On a bearish list that is a falling path. The first retry drops the five-candle dip and keeps the EPS door. The second retry drops the EPS beat. In-line still passes. A miss still fails. A missing print does not finish the row and is not an entry. Two retries is the cap. A row found only after a drop is an entry under that labeled pass. It is not a default-scout entry.

Say it in the first sentence when a door moved. If the dip was dropped: the first pass was short, and the five-candle dip was dropped to fill the entry list. If the EPS beat was dropped as well: the EPS beat was dropped on the next pass, a miss still fails, and a missing print stays unfinished. The completion table adds a Door column. Blank means the written doors. Otherwise the cell is "dip dropped" or "dip and EPS beat dropped."

If the retries still cannot make three finished entries, stop. Do not pad the table with fallbacks. Show the finished entries and the count of fallback rows held off the table. Then ask, and the ask states the plan. The entry list is short. Fallback rows are not entries. Fill the rest with the next stock that clears the same entry cut on a wider pass, keep this list, or open crypto. Crypto uses its own card and does not use the stock floor. Search only the side the user names. A stock fill stays on the entry cut. A crypto fill is a separate table. A fallback moves onto the table only if the user says that is the fill, and the row stays labeled fallback.

An empty completion is a correct empty. A universe with no slope that clears half the short print still returns no entry. Do not invent a lower gap to finish the three.

The final gate is the user. From the completion table the user passes one, several, or all, or loops back for a new list.

### Custom scout

Custom scout uses the style asked at the start. Unanswered is swing. The user names the door: price, size, sector, or a list they already have. A filter sifts the whole market. The first batch of 40 is an auto-scout limit. It does not cap a filtered search.

Fill the blanks the floor needs when the user did not name them. A bullish ask for an undervalued name fills a drop of at least 3% over the last five style candles and a short print under 3%. A bearish ask fills a rise of at least 3% over those five candles and a short print above the actual slope. An EPS beat or a miss is filled on a swing or a long hold only. A day trade does not fill an earnings sign. Aggressive pace uses 8% for the five-candle move. A blank the user already named is not replaced.

Gate 2 is skipped unless the user asked for the profit-path cut. Gate 3 is the entry cut. List completion runs after that cut when the finished entry list is under three. The floor is market cap times 1.mAts, divided by diluted shares times 1.(s/2). On a swing or a long hold, M on the row is the dividend, the halved and capped trend, and the EPS. A missing dividend fetch does not finish that row. On a day trade, M is mTs only. The user then picks which names open the target card.

A named ticker is not a custom scout. If the user asks for fair value or an eval on named stocks, skip the gates and give that card.

### Target card

A name passed from the gate 3 table gets the full eval, in the rank order the user picked.

The first table repeats the gate 3 row and adds the target: ticker, current price, FVP, gap percent, slope, EPS m, MFVP, and the gap from the current price to MFVP. The hit window follows the style. Swing is six months from the eval date. A long hold is twelve months from the eval date. A day trade runs through the close of the next trading day. On a swing or a long hold, the dividend is already in M and the eval adds the two news scores. On a day trade, M is mTs only. mTs equals mAts halved and capped at 0.10. Dividend, EPS, and both news lines are listed and labeled not charged.

The inputs table lists every fair-value number and its source: price, diluted shares, prior-quarter shares, revenue, operating cost, net revenue, prior-quarter net revenue, short interest, book value, mAts, 1.mAts, total apparent worth, apparent diluted shares, and FVP. Book value is shown here. It is not a gate.

The M table lists every contributor, the score, why it scored that way, and the source, then a sum row for M. Do not skip a line. A zero still gets a row and a reason: no dividend, yield above 10%, no second event, or a routine headline. A day-trade line that is not charged says not charged. It does not say 0. The why cell is not left blank. 1.mAts is not a row in that table.

Present a passed name in this shape.

| Ticker | Current price | FVP | Gap % | Slope | EPS m | M | MFVP | Low | High | MFVP gap % | Target window |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |  |  |  | Style window: six months, twelve months, or the next close |

FVP is the fair value price. MFVP is the modified fair value price. Swing targets six months. A long hold targets twelve months. A day trade targets the close of the next trading day. Low and high are that target minus and plus the 10-candle average true range on the style candles. On a day-trade M table, mTs is the only charged row. The other rows say not charged.

| Input | Value | Source |
| --- | --- | --- |
| Price |  | Live tape |
| Diluted shares |  |  |
| Prior-quarter shares |  |  |
| Revenue |  |  |
| Operating cost |  |  |
| Net revenue |  | Latest quarter, revenue minus operational cost |
| Prior-quarter net revenue |  |  |
| Net revenue quarter-to-quarter growth |  | Latest minus prior, divided by the absolute prior |
| Slope |  | Live tape, mAts, raw midpoint gap from the 60-candle and 30-candle closes. The candle is the style candle. |
| mAts |  | Raw midpoint gap. Same number as the slope. |
| 1.mAts |  | 1 + mAts. Floor multiplier only. Not added into M. |
| Short interest |  |  |
| Book value |  |  |
| Total apparent worth |  | Market cap times 1.mAts |
| Apparent diluted shares |  | Diluted shares times 1.(s/2) |
| FVP |  |  |

| Type | m | Score | Why | Source |
| --- | --- | --- | --- | --- |
| Sentiment | Trend |  |  |  |
| Sentiment | Dividend |  |  |  |
| Catalyst | EPS |  |  |  |
| Catalyst | News 1 |  |  |  |
| Catalyst | News 2 |  |  |  |
|  | M |  | Sum |  |

Advice paragraph. First the strategy of play. Then what is known about this name.

### Advice paragraph

The first part is the strategy of play. Entry is the current price only when the row is an entry. On a bullish card, an overvalued name is not an entry: do not enter. If the user enters anyway, wait until price hits fair value, then recalculate. On a bearish card, an undervalued name gets the same warning. Recalculate any eval when new price data, news, or a financial report comes out. On a swing or a long hold, a bullish entry watches the low band. If price reaches that band and turns back, sell before a cross back through fair value, so the gain is at least the gap. If price clears the mid, hold the continuation and trail 3% under the highest close. Exit only if it crosses back through the mid. If price never reaches the low band and falls from the entry, the gap is not locked. Bearish mirrors this off the high band and fair value: hold the continuation down, and exit on a close back through the mid. A day-trade card does not use that trail. The day-trade play is the 10-hour band. A value-gap row is the entry. A fallback is not an entry. Do not buy or short it. Exit at the next trading day's close, or earlier on a cross back through fair value. If the user named a take-profit amount, that amount is the exit and the trade does not roll. If no take-profit was named and price is still going in the trade's direction at the next close, the advice may say the day trade can continue as a swing. That sentence is advice only. It does not change the window, recompute M, or open a swing card unless the user asks.

The rest of the paragraph is stock-specific: the filing, the two news events, and any tape tip that did not qualify as an m score. If short interest is 15% or higher, the advice names it and points to the squeeze finder. This search is not a squeeze search.

After the evals are complete, the AI asks three things. Whether the user wants the style-window odds on any of the passed names. Whether they want more detail on a subset of that list. Whether they want a new auto-scout list, the same list kept, or a custom list with a replaced gate 1 door, such as mid and small with the conservative pace. The odds are not computed until that ask is yes. A Word file of the tables is written only if the user asks for it.

### Squeeze finder

A scout option, asked only if the user asks for squeeze plays. It is a preset custom search. It does not use fair value. A missing days-to-cover print does not stop the table. That cell stays blank and the name still ranks on short interest. Borrow fee and gamma stay research lines.

| Gate | Keep | Output |
| --- | --- | --- |
| 1 | Short interest at least 15% of float. Price above $5. Dollar volume above $20M. Up over the last five daily candles into the current price. No pending cash deal at or above the tape. Squeeze stays on daily candles. | Long list |
| 2 | Days to cover at least 5, or short interest higher than the prior print. Latest quarter was a beat or in line within 1%. | Shorter list |
| 3 | Rank by short interest, then days to cover. | Ticker, price, short interest %, days to cover, five-candle change |

| Ticker | Price | Short interest % | Days to cover | Five-candle change |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

```python
def squeeze_rank(rows):
    kept = []
    for r in rows:
        if r.get("short_interest") is None or r["short_interest"] < 0.15:
            continue
        move = r.get("five_candle", r.get("five_session"))
        if r.get("price", 0) <= 5 or r.get("dollar_volume", 0) < 20_000_000 or move is None or move <= 0 or r.get("cash_deal"):
            continue
        if r.get("days_to_cover") is not None and r["days_to_cover"] < 5 and not r.get("short_rose"):
            continue
        if r.get("eps_surprise") is not None and r["eps_surprise"] < -0.01:
            continue
        kept.append(r)
    return sorted(kept, key=lambda r: (r["short_interest"], r.get("days_to_cover") or 0), reverse=True)
```

## Greeks

Run only after the evals, and only for names the user picks. A bullish target is treated as a call struck at the style target. A bearish target is treated as a put struck at the style target. Swing expires in six months. A long hold expires in twelve months. A day trade expires at the next trading day's close. The odds say how likely the tape is to reach that strike if the volatility used is right. They do not say the system is right.

Use implied volatility if a print exists. Otherwise use realized volatility from the style candles. Label which one was used. T follows the hit window. Swing is 0.5 year. A long hold is 1.0 year. A day trade is 2/252 year, the eval day and the next session. The day-trade strike uses the mTs target. The odds are on that strike, not on the 10-hour band. If the band is wider than the gap, the advice says the gap is not lockable.

```
d = ln(MFVP / P) / (σ × √T)
std_devs = d
finish = 1 − Φ(d)          bullish, chance of finishing beyond MFVP
touch  = 2 × (1 − Φ(d))    bullish, chance of touching MFVP inside the style window
```

A bearish card uses ln(P / MFVP) in place of ln(MFVP / P). Touch is capped at 1. Φ is the standard normal cumulative. Delta, gamma, theta, and vega may be listed beside the odds, using the same strike, expiry, and volatility. The odds are a volatility sketch, not a broker price. They assume no drift. Say that on the card.

## Back-test

Back-test is a user option. It runs the same gates on a past day, using only the filings and the tape that existed on that day.

The entry is the price on that day. Fair value is what would have prompted the buy or the short. The modified fair value from that day is the prediction. The band and the advice are the same ones given on a live card. The slope on that card uses the 60-candle and 30-candle closes that existed on that day. The candle is the style candle.

A back-test card uses the true M for that style, not the gate-row M. On a swing or a long hold, find the two news events inside the 30 days before the start date. Score them the same way as a live card, within ±0.03, and label the source. No second event scores 0 and is labeled. A headline after the start date is not used. True M is the dividend, the halved and capped slope, the EPS, and those two news scores. On a day trade, M is mTs only. News, the dividend, and the EPS are not charged. The modified target uses that style sum.

The path after that day is already known, so the back-test card adds a hit table and a hindsight paragraph under the advice.

| Rail | Hit date | Price | After the hit |
| --- | --- | --- | --- |
| Low |  |  | Continued, or turned back |
| Mid |  |  | Continued, or turned back |
| High |  |  | Continued, or turned back |

A blank rail was not hit from the eval date through the current date. The After column says whether the tape kept going in the trade's direction or turned back through that rail. Bullish direction is up. Bearish direction is down.

The hindsight paragraph uses that table. It says whether the band was hit, how long from the entry to the first rail, and what the written advice would have done. On a swing or a long hold that is sell before a cross back through fair value, trail after the mid, or leave the watch unfilled. On a day trade that is exit at the next close, exit earlier on a cross back through fair value, take the named take-profit, or note that a continuation could have rolled into a swing. It then says what the later tape did, and whether that play would have locked the gap. It does not change the advice that would have been given on the eval date.

## Crypto

A coin can swing, long hold, or day trade. Unanswered style is swing. Crypto uses the price times (1 + M). It does not use 1.mAts. 1.mAts is a stock-floor multiplier. The tape pull is the same function, with the coin symbol and the style candle.

```
target = price × (1 + M)
```

Swing and long hold:

```
M = mTrend + mFlow + mYield + mRegulation + mSupply
```

Day trade:

```
M = mTs
```

mTs is mAts halved and capped at 0.10. It is the only line charged on a day-trade coin. Flow, yield, regulation, and supply are listed and labeled not charged. A missing print does not keep that card incomplete.

Swing uses 60 and 30 daily candles, a five-daily-candle move, a 10-day band, and a six-month target. A long hold uses 60 and 30 weekly candles, a five-weekly-candle move, a 10-week band, and a twelve-month target. A day trade uses 60 and 30 hourly candles, a five-hourly-candle move, a 10-hour band, and a target through the next trading day's close. The five-candle projection is the slope, not the target window. Sixty hourly candles are more than one session. Say that on the card.

Conservative caps the trend line at ±0.10. Aggressive removes that cap on a swing or a long hold only. A day-trade mTs stays capped. The other caps stay. Flow and regulation are written from the source named in the row. A missing flow or regulation print scores 0 and is labeled not found. It does not stop a swing or a long-hold card. Event lines still look back 30 days on every style. Do not stretch that lookback to the target window.

| Style | Candle | M charged | Target window |
| --- | --- | --- | --- |
| Swing | Daily | Trend, flow, yield, regulation, supply | Six months |
| Long hold | Weekly | Trend, flow, yield, regulation, supply | Twelve months |
| Day trade | Hourly | mTs only | Next trading day's close |

| Type | m | Required | How scored | Cap |
| --- | --- | --- | --- | --- |
| Sentiment | Trend | Yes, except a day trade uses mTs | Same midpoint gap as the stock slope, halved and capped. The candle matches the style. Aggressive removes the cap on a swing or a long hold only. | ±0.10, or none if aggressive and not a day trade |
| Sentiment | Flow | Swing and long hold only | 8-hour funding rate or exchange premium, annualized as rate times 3 times 365. Positive funding scores negative. No print, no score. Not charged on a day trade. | ±0.05 |
| Sentiment | Yield | Swing and long hold only | Staking yield if one exists. No yield, no score. Yield above 10% scores 0. Not charged on a day trade. | ±0.05 |
| Regulatory | Regulation | Swing and long hold only | Approval, ban, or enforcement inside 30 days. Scored by impact. Not charged on a day trade. | ±0.05 |
| Regulatory | Supply | Swing and long hold only | Unlock or burn inside 30 days. An unlock scores negative. Not charged on a day trade. | ±0.03 |

## Scripts

These scripts compute numbers the card already defines. They do not change a gate. News scores, eval reasons, and the advice stay written.

### EDGAR pull

Cut at an as-of date. Returns the latest quarter net revenue, the prior quarter net revenue, diluted shares, and the filed date. Those two quarters feed the profit-path cut and the inputs table. The floor uses 1.mAts. EDGAR wins on the filing figures.

```python
import json
import urllib.request

SEC = {"User-Agent": "MarketScoutMentor research contact@example.com"}

def edgar_quarter(cik, asof):
    cik = str(cik).zfill(10)
    url = f"https://data.sec.gov/api/xbrl/companyfacts/CIK{cik}.json"
    facts = json.loads(urllib.request.urlopen(
        urllib.request.Request(url, headers=SEC), timeout=40).read())
    gaap = facts.get("facts", {}).get("us-gaap", {})

    def rows(tag, unit):
        node = gaap.get(tag) or {}
        out = []
        for r in node.get("units", {}).get(unit, []):
            if r.get("form") not in ("10-Q", "10-K"):
                continue
            if (r.get("filed") or "") > asof:
                continue
            start, end = r.get("start") or "", r.get("end") or ""
            span = 0
            if start and end:
                from datetime import date
                span = (date.fromisoformat(end) - date.fromisoformat(start)).days
            # Quarterly fact. 60 to 120 days covers a short quarter and a long one. A 10-K annual fact is left out.
            if not (60 <= span <= 120):
                continue
            out.append(r)
        out.sort(key=lambda r: r.get("end") or "")
        seen, clean = set(), []
        for r in out:
            if r["end"] in seen:
                continue
            seen.add(r["end"])
            clean.append(r)
        return clean

    rev = rows("Revenues", "USD") or rows("RevenueFromContractWithCustomerExcludingAssessedTax", "USD")
    def add_q4(quarterly, tag):
        node = gaap.get(tag) or {}
        annual = []
        nine = []
        for r in node.get("units", {}).get("USD", []):
            if (r.get("filed") or "") > asof or r.get("form") not in ("10-Q", "10-K"):
                continue
            start, end = r.get("start") or "", r.get("end") or ""
            if not start or not end:
                continue
            span = (date.fromisoformat(end) - date.fromisoformat(start)).days
            if 300 <= span <= 380:
                annual.append(r)
            elif 240 <= span <= 290:
                nine.append(r)
        for a in annual:
            if any(q["end"] == a["end"] for q in quarterly):
                continue
            base = next((n for n in nine if n["end"] < a["end"] and (date.fromisoformat(a["end"]) - date.fromisoformat(n["end"])).days <= 120), None)
            if base is None:
                continue
            quarterly.append({"end": a["end"], "filed": a["filed"], "val": a["val"] - base["val"], "form": "10-K"})
        quarterly.sort(key=lambda r: r.get("end") or "")
        return quarterly
    from datetime import date
    rev = add_q4(rev, "Revenues") or add_q4(rev, "RevenueFromContractWithCustomerExcludingAssessedTax")
    cost = rows("CostsAndExpenses", "USD")
    opinc = rows("OperatingIncomeLoss", "USD")
    shares = rows("WeightedAverageNumberOfDilutedSharesOutstanding", "shares")
    if not rev or not shares or len(rev) < 2:
        return {"incomplete": True}
    q = rev[-1]
    prior = rev[-2]
    sh = [s for s in shares if s["end"] <= q["end"]]
    prior_sh = sh[-2]["val"] if len(sh) >= 2 else None
    def cost_at(end):
        return next((c["val"] for c in cost if c["end"] == end), None)
    q_cost = cost_at(q["end"])
    p_cost = cost_at(prior["end"])
    if q_cost is None or p_cost is None:
        q_op = next((c["val"] for c in opinc if c["end"] == q["end"]), None)
        p_op = next((c["val"] for c in opinc if c["end"] == prior["end"]), None)
        if q_op is None or p_op is None:
            return {"incomplete": True}
        quarter_nr, prior_nr = q_op, p_op
    else:
        quarter_nr = q["val"] - q_cost
        prior_nr = prior["val"] - p_cost
    if not prior_nr:
        return {"incomplete": True, "reason": "prior quarter is zero"}
    nrd = (quarter_nr - prior_nr) / abs(prior_nr)
    return {
        "quarter_nr": quarter_nr,
        "prior_nr": prior_nr,
        "nrd": nrd,
        "shares": sh[-1]["val"],
        "prior_shares": prior_sh,
        "period_end": q["end"],
        "filed": q["filed"],
        "source": url,
    }
```

### Tape pull

Cut at the same as-of date. Swing uses daily candles. A long hold uses weekly candles. A day trade uses hourly candles. Hourly history covers about 60 days. An older day-trade as-of returns incomplete instead of using a later candle. Returns the current price, the last five candles into that price, session dollar volume, the 60-candle and 30-candle closes, and the 10-candle average true range. On a stock, hourly volume is scaled by 6.5 so the size door still means a session, and weekly volume is scaled by 1/5 for the same door. A coin uses this same pull and is not scaled. Pass coin=True. A hyphen in a stock symbol is not a coin.

```python
from datetime import datetime

def tape_asof(symbol, asof, style="swing", coin=False):
    """style candles: swing daily, long hold weekly, day trade hourly. Counts stay 60, 30, and 5."""
    interval = {"swing": "1d", "hold": "1wk", "long hold": "1wk", "day": "1h", "day trade": "1h"}[style]
    span = "60d" if interval == "1h" else "5y"
    url = f"https://query1.finance.yahoo.com/v8/finance/chart/{symbol}?range={span}&interval={interval}"
    raw = json.loads(urllib.request.urlopen(
        urllib.request.Request(url, headers={"User-Agent": "Mozilla/5.0"}), timeout=25).read())
    res = raw["chart"]["result"][0]
    q = res["indicators"]["quote"][0]
    rows = []
    hourly = interval == "1h"
    for t, h, l, c, v in zip(res["timestamp"], q["high"], q["low"], q["close"], q["volume"]):
        if h and l and c:
            stamp = datetime.utcfromtimestamp(t)
            key = stamp.strftime("%Y-%m-%d %H:%M") if hourly else stamp.date().isoformat()
            rows.append((key, h, l, c, v or 0))
    stamp = str(asof)
    if len(stamp) == 10:
        w = [r for r in rows if r[0][:10] <= stamp]
    else:
        w = [r for r in rows if r[0] <= stamp]
    if not w or len(w) < 61:
        reason = "fewer than 61 candles"
        if hourly:
            reason = "hourly tape covers about 60 days; this as-of is outside that window or the pull is short"
        return {"incomplete": True, "reason": reason}
    price = w[-1][3]
    trs = []
    for i in range(1, len(w)):
        h, l, c, pc = w[i][1], w[i][2], w[i][3], w[i - 1][3]
        trs.append(max(h - l, abs(h - pc), abs(l - pc)))
    window = {"swing": "six months", "hold": "twelve months", "long hold": "twelve months", "day": "next close", "day trade": "next close"}[style]
    return {
        "price": price,
        "date": w[-1][0],
        "style": style,
        "candle": interval,
        "close_5_ago": w[-6][3],
        "close_30_ago": w[-31][3],
        "close_60_ago": w[-61][3],
        "five_candle": (price - w[-6][3]) / w[-6][3],
        "dollar_volume": price * sum(r[4] for r in w[-10:]) / 10 * (1 if coin else {"1d": 1, "1wk": 1 / 5, "1h": 6.5}[interval]),
        "atr10": sum(trs[-10:]) / 10,
        "target_window": window,
        "source": url,
    }
```

### Gate runner

Applies the thresholds already written. Pace picks the move floor. Size picks the cap and volume door. A custom door replaces only the size test the user named. Returns the ranked table with M on each row.

```python
def run_gates(rows, side, pace="conservative", size="large", style="swing", profit_path=None, require_dip=True, require_eps=True):
    """style picks the candle already stored on the row. It does not change the 3% or 8% floor.
    A day trade skips the profit path unless the caller passes profit_path=True. Dividend and EPS are not added.
    require_dip and require_eps are completion flags. A miss still fails when the beat is dropped. A missing print does not finish the row."""
    if profit_path is None:
        profit_path = style not in ("day", "day trade")
    move_floor = 0.03 if pace == "conservative" else 0.08
    kept = []
    skipped = []
    for r in rows:
        move = r.get("five_candle", r.get("five_session"))
        if move is None:
            move = 0.0
        if size == "large":
            if r.get("dollar_volume", 0) < 20_000_000 or r.get("market_cap", 0) < 10_000_000_000:
                continue
        elif size == "mid_small":
            if r.get("dollar_volume", 0) < 300_000 or r.get("price", 0) < 2:
                continue
            if r.get("sector") in ("bank", "broker", "mortgage_reit"):
                continue
        elif size != "custom":
            continue
        if side == "bullish":
            if require_dip and move > -move_floor:
                if style in ("day", "day trade"):
                    r["reject"] = "dip not met"
                    skipped.append(r)
                continue
            if style not in ("day", "day trade") and r.get("eps_surprise") is not None and r["eps_surprise"] < -0.01:
                continue
            if require_eps and style not in ("day", "day trade") and r.get("eps_surprise") is None:
                continue
            if profit_path and (not r.get("prior_nr") or (r["quarter_nr"] - r["prior_nr"]) / abs(r["prior_nr"]) <= 0.01):
                continue
            if profit_path and r.get("prior_shares") and (r["shares"] - r["prior_shares"]) / r["prior_shares"] > 0.05:
                continue
        else:
            if require_dip and move < move_floor:
                if style in ("day", "day trade"):
                    r["reject"] = "rise not met"
                    skipped.append(r)
                continue
            if style not in ("day", "day trade") and r.get("eps_surprise") is not None and r["eps_surprise"] < -0.01:
                continue
            if style not in ("day", "day trade") and r.get("eps_surprise") is not None and r["eps_surprise"] > 0.01:
                continue
            if require_eps and style not in ("day", "day trade") and r.get("eps_surprise") is None:
                continue
            if profit_path and (not r.get("prior_nr") or (r["quarter_nr"] - r["prior_nr"]) / abs(r["prior_nr"]) > 0.01):
                continue
        if style not in ("day", "day trade"):
            if not r.get("latest_quarter") or r.get("cash_deal"):
                continue
        if r.get("short_interest") is None:
            if style in ("day", "day trade"):
                r["reject"] = "no short print"
                skipped.append(r)
            continue
        if r.get("mats") is None or not r.get("price") or not r.get("shares"):
            continue
        mats = r["mats"]
        fv = fair_value(r["price"], r["shares"], mats, r["short_interest"])
        if r.get("m_eps") is None and style not in ("day", "day trade"):
            continue
        eps = r.get("m_eps")
        trend = r.get("m_trend")
        if trend is None and style not in ("day", "day trade"):
            continue
        if style in ("day", "day trade"):
            gate_m = day_trade_m(r["mats"])["M"]
            dividend = None
            eps = None
        else:
            if r.get("m_dividend") is None:
                continue
            dividend = r["m_dividend"]
            gate_m = dividend + trend + eps
        r["M"] = gate_m
        gap = fv["gap"]
        if side == "bullish":
            if gap >= 0.02:
                kind = "value"
            elif abs(gap) < 0.005 and gate_m >= 0.02:
                kind = "fair plus M"
            elif gap >= 0.005 and gate_m >= 0.01:
                kind = "gap plus M"
            else:
                r["reject"] = "entry not met"
                skipped.append(r)
                continue
        else:
            if gap <= -0.02:
                kind = "value"
            elif abs(gap) < 0.005 and gate_m <= -0.02:
                kind = "fair plus M"
            elif gap <= -0.005 and gate_m <= -0.01:
                kind = "gap plus M"
            else:
                r["reject"] = "entry not met"
                skipped.append(r)
                continue
        r.update(fv)
        r["slope"] = mats
        r["eps_m"] = eps
        r["entry"] = kind
        r["finished_entry"] = True
        r["door"] = r.get("door") or "written"
        kept.append(r)
    passed = rank_gate3(kept, side)
    fails = [r for r in rows if id(r) not in {id(k) for k in kept} and r.get("M") is not None]
    fails.sort(key=lambda r: r["M"], reverse=(side == "bullish"))
    if style in ("day", "day trade"):
        value = [r for r in passed if r["entry"] == "value"]
        other = [r for r in passed if r["entry"] != "value"]
        out = value + other
        seen = {id(r) for r in out}
        pool = fails + skipped
        for r in pool:
            if len(out) >= 10 or id(r) in seen:
                continue
            short = 0.0 if r.get("short_interest") is None else r["short_interest"]
            if r.get("fvp") is None and r.get("price") and r.get("shares") and r.get("mats") is not None:
                fv = fair_value(r["price"], r["shares"], r["mats"], short)
                r.update(fv)
                if r.get("short_interest") is None:
                    r["gap_label"] = "unadjusted"
            r["entry"] = "volatility fallback"
            r["reject"] = r.get("reject") or "entry not met"
            r["finished_entry"] = False
            seen.add(id(r))
            out.append(r)
        return out[:10]
    return passed[:10]


def complete_list(primary, wider_rows, side, pace="conservative", size="large", style="swing", profit_path=None, accept_fallbacks=False):
    """After the gates or the custom filters. Fills toward 3 finished entries. Does not invent an entry cut.
    wider_rows is the next universe. Day trade returns its own table. Fallbacks stay off unless accept_fallbacks is true."""
    if style in ("day", "day trade"):
        return {"entries": primary[:10], "note": None, "ask": None, "fallback_count": 0}
    entries = [r for r in primary if r.get("finished_entry")]
    notes = []
    seen = {r.get("ticker") for r in entries}
    if len(entries) < 3:
        second = run_gates(wider_rows, side, pace, size, style, profit_path, require_dip=False, require_eps=True)
        added = False
        for r in second:
            if not r.get("finished_entry") or r.get("ticker") in seen:
                continue
            r["door"] = "dip dropped"
            entries.append(r)
            seen.add(r.get("ticker"))
            added = True
            if len(entries) >= 3:
                break
        if added:
            notes.append("The first pass was short. The five-candle dip was dropped to fill the entry list.")
    if len(entries) < 3:
        third = run_gates(wider_rows, side, pace, size, style, profit_path, require_dip=False, require_eps=False)
        added = False
        for r in third:
            if not r.get("finished_entry") or r.get("ticker") in seen:
                continue
            r["door"] = "dip and EPS beat dropped"
            entries.append(r)
            seen.add(r.get("ticker"))
            added = True
            if len(entries) >= 3:
                break
        if added:
            notes.append("The EPS beat was dropped on the next pass. A miss still fails. A missing print stays unfinished.")
    entries = rank_gate3(entries, side)[:10]
    held = [r for r in wider_rows if r.get("ticker") not in seen and r.get("M") is not None]
    ask = None
    if not entries:
        ask = "The entry list has no finished entry. Fallback rows are not entries. Do not buy or short them. Search wider for a name that still clears the entry cut, keep this list, or open crypto. Crypto uses its own card and does not use the stock floor."
    elif len(entries) < 3:
        ask = "The entry list is short. Fallback rows are not entries. Do not buy or short them. Fill the rest from a wider pass that still clears the entry cut, keep this list, or open crypto."
    if accept_fallbacks and len(entries) < 3:
        held.sort(key=lambda r: r.get("M") or 0, reverse=(side == "bullish"))
        for r in held:
            if len(entries) >= 3:
                break
            r["entry"] = "fallback"
            r["finished_entry"] = False
            r["door"] = "fallback, user fill"
            entries.append(r)
        ask = "Fallback rows were added because you asked. They are not entries. Do not buy or short them."
    return {"entries": entries, "note": " ".join(notes) or None, "ask": ask, "fallback_count": len(held)}
```

### Card filler

Writes the numbers and the source of each number. It does not write the news scores, the eval reasons, or the advice.

```python
def fill_card(row, m_parts):
    if row.get("fvp") is None and row.get("price") and row.get("shares") and row.get("mats") is not None:
        short = 0.0 if row.get("short_interest") is None else row["short_interest"]
        row.update(fair_value(row["price"], row["shares"], row["mats"], short))
        if row.get("short_interest") is None:
            row["gap_label"] = "unadjusted"
    if row.get("fvp") is None:
        return {"ticker": row.get("ticker"), "fvp": None, "gap": None, "note": "not computed", "entry": row.get("entry")}
    if row.get("style") in ("day", "day trade"):
        scored = day_trade_m(row["mats"])
        m = scored["M"]
        m_parts = {"mTs": scored["mTs"], "dividend": "not charged", "trend": "not charged", "eps": "not charged", "news1": "not charged", "news2": "not charged"}
    else:
        if None in (m_parts.get("dividend"), m_parts.get("trend"), m_parts.get("eps")):
            return {"ticker": row.get("ticker"), "note": "incomplete", "entry": row.get("entry")}
        m = true_m(m_parts.get("dividend"), m_parts.get("trend"), m_parts.get("eps"), m_parts.get("news1") or 0, m_parts.get("news2") or 0)
    if row.get("atr10") is None:
        return {"ticker": row.get("ticker"), "fvp": row.get("fvp"), "note": "band not computed", "entry": row.get("entry")}
    b = band(row["fvp"], m, row["atr10"])
    return {
        "ticker": row["ticker"],
        "M": m,
        "price": row["price"],
        "fvp": row["fvp"],
        "fvp_gap": row["gap"],
        "entry": row.get("entry"),
        "mats": row["mats"],
        "one_mats": row["one_mats"],
        "mfvp": b["mfvp"],
        "mfvp_gap": (b["mfvp"] - row["price"]) / row["price"],
        "low": b["low"],
        "mid": b["mid"],
        "high": b["high"],
        "m": m_parts,
        "sources": row.get("sources", {}),
    }

def fill_crypto_card(row, parts):
    """row is a tape_asof result plus mats. parts are the crypto contributors. Day trade ignores every part but the slope."""
    clock = style_clock(row.get("style", "swing"))
    if row.get("mats") is None or row.get("price") is None or row.get("atr10") is None:
        return {"symbol": row.get("symbol"), "note": "not computed"}
    scored = crypto_m(row["mats"], parts.get("flow"), parts.get("yield"), parts.get("regulation"), parts.get("supply"), clock["style"], parts.get("pace", "conservative"))
    band = crypto_target(row["price"], scored["M"], row["atr10"])
    return {"symbol": row.get("symbol"), "style": clock["style"], "window": clock["window"], "T": clock["T"], "M": scored["M"], "m": scored, **band}
```
