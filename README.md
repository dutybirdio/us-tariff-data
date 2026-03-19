# US Tariff Data

Daily-updated US tariff data from 8 government 
sources. Free to use. No API key required.

Data is collected and maintained by 
[DutyBird](https://dutybird.io) — tariff 
monitoring for US importers.

---

## What's in here

### `data/treasury-collections.json`
Monthly customs duty collections from the US 
Treasury Monthly Treasury Statement.

**Latest:** $26.6B collected in February 2026 
— up 308% year-over-year.
```json
{
  "period": "2026-02",
  "collections_billions": 26.6,
  "fytd_billions": 144.3,
  "yoy_change_pct": 308,
  "source": "US Treasury Monthly Treasury Statement"
}
```

---

### `data/section-301-rates.json`
Current Section 301 tariff rates by country 
and legal authority. Source: USITC Harmonized 
Tariff Schedule and Federal Register.
```json
{
  "country": "China",
  "rate_range_min": 30,
  "rate_range_max": 145,
  "legal_authority": "Section 301 Trade Action",
  "effective_date": "2018-07-06",
  "updated_at": "2026-03-19"
}
```

---

### `data/active-exclusions.json`
All 178 active Section 301 product exclusions 
with HTS codes, chapter 99 headings, and 
expiry dates. Updated nightly from USTR 
Federal Register notices.

**Next mass expiry:** November 10, 2026
```json
{
  "hts_code": "8473.30.1180",
  "ch99_heading": "9903.88.69",
  "description": "Printed circuit assemblies 
    for rendering images onto computer screens",
  "list_number": 3,
  "expires_at": "2026-11-10",
  "status": "active",
  "source_doc": "FR Doc 2025-21671"
}
```

---

### `data/federal-register-notices.json`
Recent USTR and CBP Federal Register notices 
affecting tariff rates, with effective dates 
and HTS codes impacted.

---

## Update frequency

| Source | Frequency |
|--------|-----------|
| Federal Register | Every 6 hours |
| USITC HTS | Daily |
| Census Bureau Trade Data | Daily |
| US Treasury Collections | Monthly |
| Penn Wharton Budget Model | Monthly |
| CBP CSMS | Every 6 hours |

Last updated: see commit timestamp above.

---

## Usage

All data is in JSON format. No authentication 
required. MIT licensed — use freely.
```bash
# Fetch active exclusions
curl https://raw.githubusercontent.com/dutybirdio/us-tariff-data/main/data/active-exclusions.json

# Fetch Treasury collections
curl https://raw.githubusercontent.com/dutybirdio/us-tariff-data/main/data/treasury-collections.json
```

---

## Need product-specific monitoring?

DutyBird monitors your specific HTS codes 
and alerts you when tariff costs change.

- Match your products against 178 active 
  Section 301 exclusions
- Get alerted before Federal Register 
  notices affect your shipments
- Track your actual duty exposure by 
  HTS code and origin country

**→ [dutybird.io](https://dutybird.io)**  
7-day free trial. No credit card required.

---

## Data sources

See [SOURCES.md](SOURCES.md) for full 
source documentation.

## License

MIT — see [LICENSE](LICENSE)

Data sourced from US government publications. 
Not legal or financial advice. Always verify 
with a licensed customs broker.
