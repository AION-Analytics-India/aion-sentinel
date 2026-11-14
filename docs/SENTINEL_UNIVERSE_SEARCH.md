# Sentinel full-universe search and company detail API

Public product documentation. Scope: 13 November 2026 release report and 14 November 2026 published coverage.

Sentinel is a proprietary hosted forensic-accounting and company-analysis system for qualified human review. This document describes public request routes and reported release verification, not private scoring methodology, model weights, or a guaranteed subscriber integration.

## Latest dated searchable projection - 14 November 2026

The **Top 200 is not an on-demand search limit**. The published 14 November projection has **3,013 searchable identities**, with **2,740 score-detail identities** (2,738 convergently classified and 2 score-present but classification-unavailable), and **273 status-only identities**. The ranked proactive feed remains a separate view of up to 200 records. Any covered identity can be searched by an authorized subscriber; company-detail requests retain the existing plan allowance. There is no claim of complete NSE-listed issuer coverage or of unlimited request volume.

The public routes are `GET /api/v1/sentinel/search/universe?q=...` (ticker, company name or CIN) and `GET /api/v1/sentinel/company/{identifier}`, both requiring `X-API-Key`. A company outside the Top 200, or a status-only record, must not be interpreted as ROUTINE. A saved owner-key test for 157 Mainboard records does not establish valid subscriber-key production access, which remains unverified by the submitted evidence. At 07:39 IST on 14 November a **separate** Decision API readiness test returned HTTP 503; that result cannot be attributed to these lookup routes.

The 13 November release data below is retained as dated historical evidence, not the current 14 November denominator.

## Dated universe and response depth

| 13 November 2026 output | Count | Meaning |
| --- | ---: | --- |
| Searchable identities | 2,856 | Covered company identities searchable on demand |
| Identities with score details | 2,583 | Available company score details under existing access rules |
| Status-only identities | 273 | Identity and publication status without score details |
| Daily ranked radar | Up to 200 | Separate subscriber dashboard view, not the complete lookup universe |

The 2,856 searchable identities are Sentinel's covered dated population, not a claim of all NSE-listed issuers. The November 8 scoring output and the older 3,008-entry public demo snapshot are separate dated views.

Search has no arbitrary result-count cap. This does not mean unlimited request volume, unrestricted enumeration rights, or unlimited company-detail allowance. Company-detail requests retain the existing plan allowance.

Being outside the daily Top 200 does not mean ROUTINE. Status-only, missing information, unscored, no flagged concern, and cleared after independent human review are not interchangeable.

## Public gateway contract

| Method | Route | Function |
| --- | --- | --- |
| GET | `/api/v1/sentinel/search/universe?q=...` | Search the covered company identities |
| GET | `/api/v1/sentinel/company/{identifier}` | Request available company details or identity/publication status |

Both routes require an `X-API-Key` request header. The **public gateway does not expose `/v1/...` aliases** for these routes. Do not construct an alternative prefix from internal service documentation.

### Illustrative requests

The following examples demonstrate request construction only. They do not prove a valid subscriber key was accepted in production. Keep your key outside source code and public logs.

```sh
# Set SENTINEL_API_KEY through your secret manager or session environment.
curl --get 'https://aionanalytics.in/api/v1/sentinel/search/universe' \
  --data-urlencode 'q=ASTRAL' \
  -H "X-API-Key: ${SENTINEL_API_KEY}"
```

```sh
# Replace the placeholder with a valid identifier from an authorized lookup.
curl 'https://aionanalytics.in/api/v1/sentinel/company/IDENTIFIER' \
  -H "X-API-Key: ${SENTINEL_API_KEY}"
```

No response JSON shape, pagination scheme, rate-limit header, or status-code catalogue beyond the documented HTTP 401 check is asserted here. Confirm schemas and entitlements against the actual provisioned contract before integration.

## Verification and what remains unproven

The 13 November release report records:

- Exhaustive local API checks for 2,856 tickers and 2,856 exact company names
- A broad search yielding 2,490 matches
- An isolated browser search for ASTRAL with a displayed result
- HTTP 401 from the public routes when no API key was supplied
- Live Sentinel model page and sitemap HTTP 200, with deployment smoke checks 6/6 and focused deployment tests 20/20

**Important:** The release did not include a successful live lookup with a valid subscriber key. These checks demonstrate local coverage, an isolated user interface search, and negative authentication behavior; they do **not** yet confirm successful positive authenticated production access.

## Scope and responsible use

Sentinel surfaces dated public-company financial and relationship evidence for human research. Neither a ranking nor absence from a radar constitutes a fraud determination, credit rating, investment recommendation, indication of innocence, or conclusion about future performance. Source coverage and fiscal periods vary.

This documentation does not grant API credentials, access beyond a plan, permission to redistribute data, or access to proprietary models and methodology.

- Product and coverage: https://aionanalytics.in/models/sentinel
- Existing plans and access: https://aionanalytics.in/apis
- Repository overview: https://github.com/AION-Analytics-India/aion-sentinel
- Institutional enquiries: https://aionanalytics.in/contact
