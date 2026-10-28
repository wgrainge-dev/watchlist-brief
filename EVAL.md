# Evaluation test set

Fill this in after every refresh, before you publish. The agent is the system under test.
You are the grader. Nothing here is automated on purpose: the point is to decide, with a
source you trust, whether the agent told you the truth.

**Ground truth sources.** Pick one and use the same one every time, so your scores are
comparable week to week:

- Prices: Google Finance (google.com/finance), Yahoo Finance, or your brokerage app.
  **Chosen: Yahoo Finance history page** (`https://finance.yahoo.com/quote/TICKER/history/`),
  from 2026-10-28 on. Google Finance served no prices to the `number-checker` agent and
  shows no past daily closes.
- News: the article itself. Open the link. Check the date on the page.
- Calendar: the company's investor relations page (search "TICKER investor relations
  events"), or the Fed's own meeting calendar for FOMC dates.

Refresh date: 2026-10-28    Grader: number-checker agent (2026-10-28)

## A. Prices (one row per ticker)

Pass if the dashboard's last price is within $0.10 of the ground truth for the same day
and the same price type (close vs intraday). If the agent recorded an intraday price,
compare against the intraday price at about the same time; do not compare it to a close.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | 2026-10-21 | Close | 221.97 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ (also tried ?hl=en&gl=us&window=5D) | Fail. Unverified: Google Finance returned "Your device isn't supported" with no prices |
| NVDA | 2026-10-22 | Close | 212.21 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| NVDA | 2026-10-23 | Close | 210.96 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| NVDA | 2026-10-26 | Close | 216.00 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| NVDA | 2026-10-27 | Close | 217.94 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| NVDA | 2026-10-28 11:33 AM | Intraday | 217.50 | Not available | https://www.google.com/finance/quote/NVDA:NASDAQ | Fail. Unverified: intraday price at 11:33 AM cannot be reproduced (time has passed; market still open at grading). Google Finance also served no prices |
| JPM | 2026-10-21 | Close | 335.19 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: Google Finance returned "Your device isn't supported" with no prices |
| JPM | 2026-10-22 | Close | 336.54 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| JPM | 2026-10-23 | Close | 331.58 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| JPM | 2026-10-26 | Close | 334.04 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| JPM | 2026-10-27 | Close | 335.79 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| JPM | 2026-10-28 11:44 AM | Intraday | 339.55 | Not available | https://www.google.com/finance/quote/JPM:NYSE?hl=en | Fail. Unverified: intraday price at 11:44 AM cannot be reproduced (time has passed; market still open at grading). Google Finance also served no prices. Note: this latest came from Yahoo, while priceSource still points at stockanalysis |
| ACN | 2026-10-21 | Close | 240.26 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: Google Finance returned "Your device isn't supported" with no prices |
| ACN | 2026-10-22 | Close | 258.74 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| ACN | 2026-10-23 | Close | 249.37 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| ACN | 2026-10-26 | Close | 247.23 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| ACN | 2026-10-27 | Close | 235.16 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| ACN | 2026-10-28 11:31 AM | Intraday | 245.16 | Not available | https://www.google.com/finance/quote/ACN:NYSE?hl=en&window=5D | Fail. Unverified: intraday price at 11:31 AM cannot be reproduced (time has passed; market still open at grading). Google Finance also served no prices |
| KO | 2026-10-21 | Close | 92.68 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: Google Finance returned "Your device isn't supported" with no prices |
| KO | 2026-10-22 | Close | 95.34 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| KO | 2026-10-23 | Close | 92.71 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| KO | 2026-10-26 | Close | 92.70 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| KO | 2026-10-27 | Close | 91.18 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| KO | 2026-10-28 11:33 AM | Intraday | 92.19 | Not available | https://www.google.com/finance/quote/KO:NYSE | Fail. Unverified: intraday price at 11:33 AM cannot be reproduced (time has passed; market still open at grading). Google Finance also served no prices |
| LLY | 2026-10-21 | Close | 1270.75 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: Google Finance returned "Your device isn't supported" with no prices |
| LLY | 2026-10-22 | Close | 1306.69 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| LLY | 2026-10-23 | Close | 1273.46 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| LLY | 2026-10-26 | Close | 1279.14 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| LLY | 2026-10-27 | Close | 1281.91 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: Google Finance "device isn't supported", no prices served |
| LLY | 2026-10-28 11:31 AM | Intraday | 1298.40 | Not available | https://www.google.com/finance/quote/LLY:NYSE?hl=en | Fail. Unverified: intraday price at 11:31 AM cannot be reproduced (time has passed; market still open at grading). Google Finance also served no prices |

## B. Weekly change (one row per ticker)

The page computes this from the five closes. Pass if it is within 0.3 percentage points of
your own calculation: (last price minus the close five trading days earlier) divided by
that earlier close.

| Ticker | Dashboard weekly change | Your calculation | Pass / Fail |
|---|---|---|---|
| NVDA | -2.0% ((217.50 - 221.97) / 221.97, Oct 21 close to Oct 28 11:33 AM intraday) | Unverified | Fail. Unverified: Oct 21 close and Oct 28 latest were Unverified in A (Google Finance served no prices) |
| JPM | +1.3% ((339.55 - 335.19) / 335.19, Oct 21 close to Oct 28 11:44 AM intraday) | Unverified | Fail. Unverified: Oct 21 close and Oct 28 latest were Unverified in A (Google Finance served no prices) |
| ACN | +2.0% ((245.16 - 240.26) / 240.26, Oct 21 close to Oct 28 11:31 AM intraday) | Unverified | Fail. Unverified: Oct 21 close and Oct 28 latest were Unverified in A (Google Finance served no prices) |
| KO | -0.5% ((92.19 - 92.68) / 92.68, Oct 21 close to Oct 28 11:33 AM intraday) | Unverified | Fail. Unverified: Oct 21 close and Oct 28 latest were Unverified in A (Google Finance served no prices) |
| LLY | +2.2% ((1298.40 - 1270.75) / 1270.75, Oct 21 close to Oct 28 11:31 AM intraday) | Unverified | Fail. Unverified: Oct 21 close and Oct 28 latest were Unverified in A (Google Finance served no prices) |

## C. News grounding (one row per news item, three per ticker)

Open every link. Pass only if all four are true: the link opens, the headline matches the
article, the article date is within the last seven days, and the "why it matters" line is
supported by the article (not just plausible).

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | "Voice AI in vogue: Nvidia releases new open transcription model" https://techcrunch.com/2026/10/28/voice-ai-in-vogue-nvidia-releases-new-open-transcription-model/ | Yes | Yes (exact) | Yes (Oct 28, 2026 8:00 AM PDT; brief says Oct 28) | Yes: article calls Nemotron 3.5 Transcribe "a free, open-weight model", says it targets developers, and says it runs on Nvidia chips from Jetson to Blackwell. "Widens ecosystem" is a reasonable reading, not a quote | Pass |
| NVDA | "Nvidia to invest $3B in Meta's planned equity offering" https://stockanalysis.com/news/nvidia-3-billion-meta-offering/ | Yes | Yes (exact) | Yes (Oct 27, 2026 10:39 AM ET; brief says Oct 27) | Yes: "Meta plans to deepen the collaboration by increasing the deployment of Nvidia infrastructure" | Pass |
| NVDA | "Nvidia, Oracle expand NVIDIA Vera Rubin to multi-gigawatt scale" https://www.tipranks.com/news/the-fly/nvidia-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-thefly-news | Yes | Yes (exact) | Yes (structured-data datePublished 2026-10-27 16:06 UTC; visible page shows relative times only; brief says Oct 27) | Yes: plans to expand OCI Superclusters on Vera Rubin NVL72 to multi-gigawatt scale, "supporting growing customer demand for AI training, inference and agentic applications" (the scale-up is a plan, not built capacity) | Pass |
| JPM | "J.P. Morgan Asset Management Expands Access to Its Tokenized Money Market Funds on Solana" https://www.prnewswire.com/news-releases/jp-morgan-asset-management-expands-access-to-its-tokenized-money-market-funds-on-solana-302917188.html | Yes | Yes (exact) | Yes (Oct 22, 2026 12:00 ET; brief says Oct 22) | No: the public-blockchain cash-product push and "continued growth" of the tokenized platform are supported, but the release gives no size for the tokenized business and never calls it "small"; the only AUM figure ($4.8T) is firm-wide | Fail. "Small" is not supported by the article |
| ACN | "Accenture awarded $151.46M Air Force task order" https://www.tipranks.com/news/the-fly/accenture-awarded-151-46m-air-force-task-order-thefly-news | Yes | Yes (exact) | Yes (structured-data datePublished 2026-10-27 21:30 UTC; brief says Oct 27) | Yes: GSA Alliant 2 task order for Air Force Nuclear Weapons Center work, "expected to be completed by June 30, 2030" | Pass |
| ACN | "Accenture price target raised to $252 from $210 at Wells Fargo" https://www.tipranks.com/news/the-fly/accenture-price-target-raised-to-252-from-210-at-wells-fargo-thefly-news | Yes | Yes (exact) | Yes (structured-data datePublished 2026-10-26 10:31 UTC; brief says Oct 26) | Yes: "keeps an Equal Weight rating"; "until organic revs accelerate materially, it may be challenging to convince the Street that Accenture is an AI winner" | Pass |
| ACN | "Accenture downgraded to Neutral from Outperform at Baird" https://www.tipranks.com/news/the-fly/accenture-downgraded-to-neutral-from-outperform-at-baird-thefly-news | Yes | Yes (exact) | Yes (structured-data datePublished 2026-10-21 08:55 UTC = Oct 21 ET, the first day of the 7-day window; brief says Oct 21) | Yes: "The firm cites valuation for the downgrade following the stock's recent rally"; shares "over doubled since June". "Easy gains may be behind it" is the brief's own reading, not Baird's words | Pass |
| KO | "Coca-Cola Reports Third Quarter 2026 Results and Raises Full Year Guidance" https://www.sec.gov/Archives/edgar/data/0000021344/000162828026067403/a2026q3earningsreleaseex-9.htm | Yes | Yes (exact) | Yes (Oct 27, 2026; brief says Oct 27) | Yes: "Unit case volume grew 5%", "Net revenues grew 7% to $13.4 billion", full-year organic revenue and comparable EPS guidance raised | Pass |
| KO | "Coca-Cola Stock (KO) Falls After Beat-and-Raise Print. Here's Why" https://www.tipranks.com/news/coca-cola-stock-ko-falls-after-beat-and-raise-print-heres-why | Yes | Yes (exact) | Yes (Oct 27, 2026; datePublished 2026-10-27 15:20 UTC; brief says Oct 27) | Yes: "Management stressed that sales in the U.S. and Canada remain weak", and the article ties the dip to sluggish North American sales | Pass |
| KO | "Coca-Cola price target raised to $104 from $100 at TD Cowen" https://www.tipranks.com/news/the-fly/coca-cola-price-target-raised-to-104-from-100-at-td-cowen-thefly-news | Yes | Yes (exact) | Yes (structured-data datePublished 2026-10-28 12:35 UTC; brief says Oct 28) | Yes: "keeps a Buy rating"; "it remains their top pick after a high-quality 3Q beat" | Pass |
| LLY | "Lilly's retatrutide delivered greater A1C reduction and more than double the weight loss of Ozempic's..." https://www.prnewswire.com/news-releases/lillys-retatrutide-delivered-greater-a1c-reduction-and-more-than-double-the-weight-loss-of-ozempics-highest-approved-dose-in-head-to-head-trial-302921328.html | Yes | Yes (exact) | Yes (Oct 28, 2026 06:45 ET; brief says Oct 28) | Yes: Phase 3 head-to-head vs Ozempic 2 mg met primary and key secondary endpoints, in type 2 diabetes with weight loss as a key secondary. The release does not name Novo; "Novo's Ozempic" is general knowledge, not from the article | Pass |
| LLY | "Patrik Jonsson to retire after 36 years; Ilya Yuffa named president, Lilly Global Markets" https://www.prnewswire.com/news-releases/patrik-jonsson-to-retire-after-36-years-ilya-yuffa-named-president-lilly-global-markets-302921191.html | Yes | Yes (exact) | Yes (Oct 27, 2026 16:03 ET; brief says Oct 27) | Yes: "Effective Jan. 1, 2027, Lilly's U.S. and international businesses will come together as Lilly Global Markets", led by Yuffa | Pass |
| LLY | "Lilly declares fourth-quarter 2026 dividend" https://www.prnewswire.com/news-releases/lilly-declares-fourth-quarter-2026-dividend-302919496.html | Yes | Yes (exact) | Yes (Oct 26, 2026 11:19 ET; brief says Oct 26) | Yes: $1.73 per share, payable Dec 10, 2026, record Nov 13, 2026 | Pass |

(Add rows as needed. Fifteen items is normal for five tickers.)

## D. Calendar (one row per event)

Pass if the event and its date appear on the source linked, and the date is in the future
relative to the refresh date.

| Ticker | Event | Date shown | Confirmed on source | Pass / Fail |
|---|---|---|---|---|
| JPM | FOMC rate decision at the end of the Oct 27 to 28 meeting (market-wide) | 2026-10-28 | Yes. https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm lists the 2026 meeting "October 27-28" with no asterisk (no SEP); the 2026 schedule is not marked tentative. The decision day equals asOf, so it is not before it | Pass |
| LLY | Q3 2026 results; conference call at 10 a.m. ET | 2026-10-29 | Not on the IR page. https://investor.lilly.com/node/55096, https://investor.lilly.com/events-and-presentations, and https://lilly.gcs-web.com/news-releases/news-release-details/lilly-confirms-date-and-conference-call-third-quarter-2026 all returned HTTP 403. The third-party copy at https://finviz.com/news/403165/lilly-confirms-date-and-conference-call-for-third-quarter-2026-financial-results-announcement (Oct 15, 2026 release) says "will announce its third-quarter 2026 financial results on October 29, 2026" with the call at 10 a.m. ET, and the headline says "confirms". That copy agrees with the brief but is not the IR page | Fail. Unverified: Lilly IR site returned 403, and a Finviz repost does not count as a Pass |

## E. Omissions

Did the agent miss something a human analyst would have included? List anything you found
in the ground-truth sources that the brief does not mention (a big headline, an earnings
date inside the window). Each one counts as a Fail in the score below.

- 
- 

## F. Your own test cases

Write two tests of your own that none of the sections above cover. Examples students have
used: "the as-of date on the page matches the changelog date", "no ticker shows a flat
sparkline when the real stock moved", "the page still renders if I delete one ticker's
news list in the data". Write the test, run it, record the result.

| Test | How you checked | Pass / Fail |
|---|---|---|
| | | |
| | | |

## Score

| Section | Passes | Total | Rate |
|---|---|---|---|
| A. Prices | | | |
| B. Weekly change | | | |
| C. News | | | |
| D. Calendar | | | |
| E. Omissions (fails only) | 0 | | |
| F. Your own | | | |
| **Overall** | | | |

Publish only if A and B are 100% and C is at least 80% after fixes. If a row failed, tell
Claude exactly which row and what the correct value is, let it fix only that, rerun the
`qa-reviewer` agent, and regrade that row. Keep the original Fail in this file: a record of
what the agent got wrong is more useful than a clean sheet.
