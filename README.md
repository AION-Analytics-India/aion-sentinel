# AION Sentinel — Corporate Integrity and Forensic Financial Screening

**AION Sentinel is a proprietary corporate-integrity screening product for public financial reporting.** It helps a reviewer prioritize listed Indian companies and filing areas for further examination. It does not determine whether a company committed fraud or misconduct.

Sentinel is a hosted AION product. Its public Hugging Face page is documentation only; Hugging Face does not host Sentinel inference or model weights.

## What Sentinel analyzes

Sentinel screens public corporate filings and financial-reporting information for patterns and divergences that may merit human review. Results come from a dated coverage snapshot. An individual result can include a screening tier, review flags and explanations, peer context, and source or period details where those are available. The current public demo masks company identities in its worked examples.

The screen is intended to help answer **where should a qualified person look more closely?** It does not provide an audit opinion, verify every underlying fact, or replace examination of the source filings.

## Who can benefit

The verified product workflow is public-filing screening and research triage for analysts and institutional research teams: use the dated results to prioritize which available filings or reporting patterns to examine next. This describes a supported workflow, not a claim that any named institution is a customer, partner, evaluator, or endorser.

## Verified institutional use case

- **Research and due-diligence triage of covered listed Indian companies.** A user reviews a dated screening result, reads its stated reasons and available provenance, then checks the underlying filings and other evidence independently.

Sentinel produces screening information for that human-review workflow. It does not ingest an institution's portfolio or borrower list, make an investment or credit decision, or deliver an automated institutional monitoring system.

## Other possible applications require customer integration

These are downstream patterns to evaluate, not built-in Sentinel connectors, proven customer deployments, or claims of suitability for regulated decisions:

- **Banks and NBFCs:** add a public-information review prompt for a covered listed corporate counterparty. Sentinel does not screen a bank's full borrower book or calculate creditworthiness.
- **Asset managers and investment research desks:** join covered entities to a firm's own portfolio or watchlist and route dated results to analysts. Sentinel does not ingest holdings or generate portfolio recommendations.
- **Private equity and venture capital:** use only for covered listed entities; Sentinel does not screen private companies or replace private-company due diligence.
- **Credit rating agencies:** consider as a supplementary public-filing research input, not a rating or rating trigger.
- **Insurance:** consider for public-information review of covered listed corporate counterparties, not underwriting, claims, or solvency decisions.
- **Audit and forensic-accounting firms:** use as a way to prioritize source-document examination, not as an audit procedure, fraud finding, or assurance opinion.
- **Corporate compliance, boards, and audit committees:** consider as one input for further review of a covered listed entity, not a compliance verdict or third-party due-diligence conclusion.
- **Regulators and public-interest researchers:** inspect the public masked examples or seek authorized access for a defined research purpose. Sentinel is not a regulator service and does not establish a relationship with any regulator.

Every such workflow needs its own data joins, review controls, entitlement checks, and regulatory assessment. False positives and missed issues are possible.

## Representative output explanation

The sketch below uses placeholders. It is **not** a live result, an exact API schema, a named-company disclosure, or evidence of predictive accuracy.

```text
Snapshot date: <dated snapshot>
Screening tier: <relative review category>
Review reasons: <plain-language indicators to examine>
Peer context: <comparison, when available>
Source periods: <periods available for this record>
```

A tier or rank indicates relative screening priority in the stated snapshot and coverage universe. A flag is a reason to inspect source material. Peer divergence is context for that review. None is a probability of fraud, default, misconduct, or future loss.

## Public demonstration

Open the [public Sentinel demonstration](https://aionanalytics.in/demo/sentinel) to inspect its masked worked examples. At anonymous readback on **7 November 2026**, the page displayed a snapshot dated **4 November 2026** and a coverage count of **3,008 listed companies**. This is a dated observation, not a permanent coverage claim; use the demo page for its current displayed date and availability. The page's demo-key flow and access terms are described there.

The [Sentinel product page](https://aionanalytics.in/models/sentinel) explains the public examples, key access, interpretation, and limitations. The authenticated Sentinel radar is a separate gated interface and is not the public demo.

## Institutional API access

Sentinel's programmatic access is credentialed and entitlement-scoped. Review the current [AION API catalogue](https://aionanalytics.in/apis) and use the [official contact page](https://aionanalytics.in/contact) to ask about a controlled institutional evaluation. A public page or documentation link does not grant API access. Do not send sensitive company data unless the applicable access and privacy terms expressly permit it.

## Coverage, provenance, and limitations

- Sentinel covers listed Indian companies represented in the published snapshot; it is not a complete screen of every Indian entity, private company, or borrower.
- Results are based on available public financial-reporting records in a dated build. Snapshot dates, filing periods, and input completeness can differ by company. The latest underlying accounts can be months old; the tool is not a real-time feed.
- Review the record's displayed source, filing period, and coverage notes where available. Missing or unevaluated information is not a clean result.
- Public examples mask company identity. Access to additional identifying results is governed by current demo and institutional entitlements.
- Screening can produce false positives and false negatives. No prospective predictive performance, fraud-detection accuracy, or superiority claim is made here.
- Sentinel does not give legal, accounting, investment, credit, insurance, or compliance advice. A qualified person must verify source material and make any decision.

## Interpretation safeguards

Sentinel is a screening and research aid—not a fraud detector. A risk tier is not a probability of wrongdoing or default, an allegation, a regulatory conclusion, an investment recommendation, or an instruction to buy or sell. A flag does not establish misconduct. Absence of a flag does not establish that a company is free of risk or error.

## Proprietary rights and licensing

AION Sentinel, its model, scoring methods, weights, and implementation are proprietary intellectual property of AION Analytics Private Limited. This documentation does not grant rights to reproduce the model, obtain its source code or weights, redistribute outputs as a service, or use AION marks. Source materials remain subject to their own terms. Access is subject to the applicable AION terms and entitlement. No open-source license is offered for Sentinel.

## Official links and institutional contact

- [AION Sentinel product page](https://aionanalytics.in/models/sentinel)
- [Public Sentinel demonstration](https://aionanalytics.in/demo/sentinel)
- [API catalogue and access terms](https://aionanalytics.in/apis)
- [Official contact page](https://aionanalytics.in/contact) · [contact@aionanalytics.in](mailto:contact@aionanalytics.in)
- [Canonical GitHub documentation](https://github.com/AION-Analytics-India/aion-sentinel)
- [GitLab documentation copy](https://gitlab.com/aion-analytics-india/aion-sentinel)
- [Hugging Face documentation card](https://huggingface.co/aion-analytics-india/aion-sentinel)
- [AION website](https://aionanalytics.in/) · [GitHub organization](https://github.com/AION-Analytics-India) · [GitLab group](https://gitlab.com/groups/aion-analytics-india) · [Hugging Face organization](https://huggingface.co/aion-analytics-india)

**AION Analytics Private Limited (India).** Information for research and screening; not a finding, professional opinion, or advice.
