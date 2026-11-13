# AION Sentinel

**Financial-statement preparation, corporate relationship analysis, and evidence-led review of listed Indian companies.**

AION Sentinel is a proprietary, hosted corporate-analysis system. It does more than assign a screening tier: it prepares financial and relationship evidence, runs accounting and governance checks, and generates dated company-review outputs. Relative rankings help analysts decide what to examine next; they are not conclusions about misconduct.

The product is designed to support qualified human research. It does **not** establish fraud, predict default probabilities, provide investment advice, issue credit ratings, or make lending or investment decisions.

> **Product boundary:** This is public capability documentation, not a repository of executable Sentinel code or model weights. Features below have different levels of input coverage, computation, reporting and client delivery. An internal result should not be assumed to exist in every client-facing response.

## What Sentinel actually prepares

The following analytical work was examined in an internal capability review dated **3 November 2026**. It is not a statement that every calculation is complete, current, or exposed in the standard public demo.

| Layer | Existing analytical work | What an analyst can examine | Important boundary |
| --- | --- | --- | --- |
| Financial records | Retains annual accounts, borrowing and interest fields, tax, working capital, cash-flow information, reporting basis and source context | Reported performance and balance-sheet history, with visible data gaps | Available fields and financial years vary by company |
| Cash reconstruction | Reconstructs annual cash movement from available financial-statement information and compares it with disclosed balances | Cash-versus-earnings differences and reconciliation questions | Statement-based analysis, **not** a bank transaction ledger; cumulative-history coverage is incomplete |
| Earnings and accounting quality | Computes accrual measures, profit/cash comparisons, working-capital measures and selected earnings-quality indicators | Questions about earnings sustainability, collections, inventory and non-cash items | Ratios may be unavailable, stale or affected by reporting definitions |
| Ownership and governance | Evaluates available promoter holdings and changes, pledge evidence and related governance context | Changes in control, encumbrance and financing exposure requiring explanation | A pledge, holding change or missing field does not imply wrongdoing |
| Related parties and subsidiaries | Retains group, counterparty, related-party and subsidiary records for checks | Connections relevant to the reporting perimeter and transaction review | A disclosed relationship is not inherently improper |
| Director relationships | Connects available active-director and related-party transaction evidence | Potential interlocks requiring source-document review | Shared names or positions alone do not establish collusion |
| External events | Qualifies available regulatory and credit events, with reasons for included and excluded evidence | Context alongside financial records and historical concerns | Event availability and classification are limited by coverage and source dates |
| Prepared reports and history | Generates dated company reports, review reasons, classifications, flag history and change records | A repeatable review file rather than only a rank | The standard report does not expose every intermediate calculation |

These layers are related but distinct. **Retaining data**, **computing an indicator**, **triggering a review flag**, and **delivering a field to an external client** are four different states. This README does not collapse them into one capability claim.

## Dated implementation evidence

The numbers below describe specific **3 November 2026** local outputs, not a current service-level guarantee or a prospective validation study.

| Observed result | Scope and interpretation |
| --- | --- |
| **1,698 populated annual cash-reconciliation values** across **1,582 companies** | Company-year observations across multiple financial years, concentrated in FY2024. This is **not** 1,582 fresh FY2026 reconciliations. |
| **130 company reports generated in text and PDF** | Prepared reports with financial facts, triggered reasons and context. Text and PDF are two formats of the report, not 260 different companies. |
| Annual cash-reconstruction computation exists | The inspected standard report can explain a triggered cash concern but does **not** contain a complete annual cash-reconstruction table. |
| Separate model and rule-based review perspectives | Differences between perspectives can be informative for human review; agreement is not proof of statistical independence or predictive reliability. |

The public demo showed **3,008 listed-company entries** and a **4 November 2026** snapshot in an anonymous readback on **7 November 2026**. That is a separate, dated presentation view; it should not be treated as the population of every internal table or compared directly with differently filtered radar totals. Always check the dates and coverage displayed in the current product interface.

### Separate 8 November 2026 output layers

The **8 November 2026 daily scoring output** contained **2,856 company scoring rows** within Sentinel's covered NSE-listed-company pipeline universe, not necessarily every NSE-listed issuer. The **source-radar file** retains **up to 500 ranked records** as an intermediate output; the **subscriber-facing dashboard feed** publishes **up to 200 ranked records**. These are different publication layers, not subscriber counts, independent populations, or evidence that all computed fields reach clients. The separately dated **3,008-entry public-demo snapshot** is not the same as the 8 November scoring run.

[Read the dated public-safe coverage receipt](https://aionanalytics.in/data/sentinel-coverage/2026-11-08.json). The covered-universe pipeline runs daily, but financial-statement periods and source-fetch dates vary. A quarterly filing not yet due is not by itself an adverse signal.

**Coverage is not correctness.** Populated fields can refer to older periods, and some constructed checks lack the historical inputs needed for a usable result. Missing, not scored, zero and no flag are not interchangeable.


### 13 November 2026 full-universe on-demand search

Sentinel's authenticated search now addresses the **2,856 searchable company identities** in the covered 13 November 2026 output. **2,583 identities** have company score details available, while **273** return identity/publication status only under the existing rules. These are not 2,856 identical full-detail reports, and "full universe" refers to this dated covered population, not all NSE-listed issuers.

The on-demand lookup is **separate from the daily Top 200 radar**. A company outside the Top 200 is not thereby classified as ROUTINE or cleared of possible concerns. Status-only, unscored, missing and no adverse flag remain distinct outcomes. Search has no result-count cap, but normal plan allowances and authorization still govern access to company details.

**Authenticated public API paths:**

- `GET /api/v1/sentinel/search/universe?q=...` searches the covered identity universe.
- `GET /api/v1/sentinel/company/{identifier}` requests the available company detail or identity/publication status for an identifier.
- Both require the `X-API-Key` request header. The public gateway does **not** expose equivalent `/v1/...` aliases.

**Validation boundary:** The 13 November release report records exhaustive local API checks for 2,856 tickers and 2,856 exact company names, with a broad query returning 2,490 matches. An isolated frontend browser test found ASTRAL. Requests without a key returned HTTP 401. **A successful authenticated production lookup using a valid subscriber key was not tested**, so positive authenticated production access remains unconfirmed by that release's evidence. Do not equate route publication or HTTP 401 with proof of successful subscriber access.

[Read the public route and access reference](docs/SENTINEL_UNIVERSE_SEARCH.md). These capabilities are distinct from the older 8 November scoring and publication snapshots above.

## What questions can this help an analyst investigate?

Sentinel helps prepare evidence and organize review. It does not answer these questions conclusively.

1. **Earnings and cash:** Is the direction of reported profit consistent with operating cash movement, working capital and non-cash adjustments on comparable reporting bases?
2. **Balance-sheet quality:** Do changes in receivables, inventory, debt or other financial fields warrant a closer reading of the relevant notes?
3. **Ownership and governance:** What does the available evidence show about promoter ownership, pledges or changes over time?
4. **Group relationships:** Are related-party transactions, subsidiaries or director connections relevant to a financial-reporting question?
5. **Dated external context:** Do qualified public regulatory or credit events provide context for the period being reviewed?
6. **Conflicting screening perspectives:** Why might a model-derived rank and a rule-derived rank disagree, and what evidence should the analyst inspect before drawing a conclusion?
7. **Persistence:** Is a concern new to the latest source record, a repeated historical observation, or a change caused by updated inputs or peer context?

A properly closed review may conclude that an apparent anomaly has a legitimate explanation. Sentinel does not treat every unusual measure as an adverse finding.

## Institutional review workflow

A potential institutional workflow is:

1. **Define the universe.** Select listed Indian issuers covered by the available snapshot and establish the relevant financial periods.
2. **Check coverage.** Identify populated, missing, stale and unscored information before interpreting any flags.
3. **Inspect prepared analysis.** Review financial measures, cash-reconciliation concerns, ownership and relationships, and qualifying events where available.
4. **Read the screening perspective.** Treat tiers and separate model/rule information as priorities for examination, not calibrated probabilities.
5. **Review the evidence.** Validate company identity, source filings, reporting basis, alternative explanations and materiality.
6. **Record a decision.** An authorized analyst documents resolved questions, unresolved concerns or additional evidence required.

This describes an **evaluation pattern**, not an existing integration with a particular bank or fund. Sentinel does not presently claim to ingest institutional holdings, borrower records or customer data automatically. Portfolio matching, institution-specific alerts, workflow integration, entitlements, and decision controls would require a separately scoped implementation and verification.

### Potential users and the question they bring

| Audience | Research question supported by available public-company analysis | What Sentinel does not replace |
| --- | --- | --- |
| Wealth and asset managers | Which covered holdings or watchlist issuers deserve closer accounting and governance review? | Portfolio construction, manager ratings or buy/sell decisions |
| Investment research teams | What dated financial and relationship evidence should be reconciled before issuing a research view? | Independent analyst judgment and source verification |
| Bank and NBFC corporate-credit teams | What public-filing concerns should be checked for a covered **listed** counterparty? | Borrower-authorized data, covenant monitoring, underwriting or credit decisions |
| Forensic and governance researchers | Which source-backed accounting or relationship questions merit investigation? | Audit evidence, legal findings, fraud determinations or assurance |
| Financial-data and fintech platforms | Could defined Sentinel outputs supplement a governed research workflow? | A ready-made connector, verified integration or unrestricted API entitlement |

The application to a specific institution must be evaluated against its actual company universe and existing tools. A possible use case is not a confirmed customer deployment.

## How to evaluate practical value

Claims such as "saves analyst hours", "detects more wrongdoing" or "outperforms existing systems" require a comparison that has **not yet been established**. A controlled study should use the same covered issuers and dates as the existing process, then measure:

- Usable issuer and financial-period coverage, including missing or unscored cases
- Source support, materiality and novelty of proposed review questions
- Analyst time to verify, resolve or escalate a concern
- False positives, missed issues and a sample of low-ranked cases
- Stability of findings as filings and coverage change
- Prospective outcomes only after observations, event definitions and horizons are frozen in advance

Providers of credit early warning, forensic research and corporate-governance scoring solve adjacent problems. No claim of equal scope or superior accuracy against Accumn, Ambit or other providers is established by this README.

## Reading Sentinel output safely

- A **percentile** is a relative rank within the stated universe and date. It is **not** the probability of fraud, default or future loss.
- A **flag** identifies a condition for review; multiple flags may use related evidence and are not necessarily independent confirmations.
- Two screening approaches may **disagree**. Preserve that disagreement rather than treating agreement as proof.
- A **historical flag** is not necessarily a new event. The underlying financial-year and publication dates matter.
- **Missing or unevaluated** information cannot be interpreted as a clean company.
- A source-backed company concern can still have a legitimate reporting or business explanation.
- False positives and missed issues are possible. No independently validated prospective accuracy or verified institutional loss prevention is claimed here.

Do not publish a ranked company list as a finding of misconduct. A qualified reviewer must examine the original public records and relevant explanations.

## Public demo and institutional access

- [Sentinel product page](https://aionanalytics.in/models/sentinel): public product description and limitations.
- [Public Sentinel demonstration](https://aionanalytics.in/demo/sentinel): limited access and examples; check the page for the currently displayed snapshot, masking and eligibility.
- [AION API catalogue](https://aionanalytics.in/apis): current access status. Programmatic use requires appropriate credentials and entitlement.
- [Sentinel authenticated full-universe lookup reference](docs/SENTINEL_UNIVERSE_SEARCH.md): coverage, public gateway paths, `X-API-Key` and validation limits.
- [Institutional contact](https://aionanalytics.in/contact): request a discussion about a defined evaluation universe, output contract, source periods and human-review criteria.

The public Sentinel universe and company-detail routes use `X-API-Key`; a request without a key returned HTTP 401 in the reported release checks. However, the 13 November release did not confirm a successful live lookup using a valid subscriber key. Route visibility is not proof of positive authenticated production access. Public documentation does not grant access to model inference, private datasets or third-party systems.

The [Hugging Face Sentinel card](https://huggingface.co/aion-analytics-india/aion-sentinel) is a discovery and documentation surface; Hugging Face does not host Sentinel model weights or inference for AION.

## Product access and limitations

AION Sentinel is a proprietary hosted product presented by **AION Analytics Private Limited (India)**. This repository provides public product documentation only. It does not contain executable Sentinel software, source code, model weights, private datasets or hosted inference, and is not an open-source release.

Sentinel provides research information only. It is not a credit rating, audit opinion, compliance finding, fraud allegation, regulatory determination, investment recommendation or instruction to transact.

## Canonical links

- [Website](https://aionanalytics.in/) | [Sentinel model page](https://aionanalytics.in/models/sentinel) | [Public demo](https://aionanalytics.in/demo/sentinel)
- [API catalogue](https://aionanalytics.in/apis) | [Contact](https://aionanalytics.in/contact) | [Email](mailto:contact@aionanalytics.in)
- [GitHub repository](https://github.com/AION-Analytics-India/aion-sentinel) | [GitLab documentation](https://gitlab.com/aion-analytics-india/aion-sentinel) | [Hugging Face card](https://huggingface.co/aion-analytics-india/aion-sentinel)
- [LinkedIn](https://www.linkedin.com/company/aion-analytics-india/) | [X](https://x.com/Aion_analytics_) | [YouTube](https://www.youtube.com/@aionanalytics)
- [Telegram](https://t.me/+VXWCiDgZjBI3ZjA1) | [Discord](https://discord.gg/Dk9Pjc9cVa) | [PyPI publisher](https://pypi.org/user/aion-analytics/)

**Status of this documentation:** Supported functions and counts refer to the dated evidence above, not a warranty that every output is current or available on every access tier.
