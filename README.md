# Central Bank of Uzbekistan Exchange Rates API — cbu-exchange-rate

[![npm version](https://img.shields.io/npm/v/cbu-exchange-rate.svg)](https://www.npmjs.com/package/cbu-exchange-rate)
[![license](https://img.shields.io/npm/l/cbu-exchange-rate.svg)](https://github.com/AllRates-Today/cbu-exchange-rate/blob/main/LICENSE)
[![zero dependencies](https://img.shields.io/badge/dependencies-0-brightgreen.svg)](https://www.npmjs.com/package/cbu-exchange-rate)
[![TypeScript](https://img.shields.io/badge/TypeScript-types%20included-3178C6.svg)](https://www.typescriptlang.org/)
[![USD/UZS today](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbu%3Fsource%3DUSD%26target%3DUZS&query=%24.rate&label=USD%2FUZS%20published%20by%20Central%20Bank%20of%20Uzbekistan&color=0A7E8C&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbu/)
[![rate date](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fallratestoday.com%2Fapi%2Fopen%2Fcentral-bank%2Fcbu%3Fsource%3DUSD%26target%3DUZS&query=%24.rate_date&label=rate%20date&color=555&cacheSeconds=3600)](https://allratestoday.com/central-bank-rates-api/cbu/)

**Official Central Bank of Uzbekistan (Uzbekistan) daily exchange rates for Node.js and TypeScript. The published central bank rates behind tax filings, customs valuations, audits, and compliant invoicing — not market estimates, but the numbers Central Bank of Uzbekistan itself prints, every business day.**

## 🚀 Why this client?

- 🏛️ **Official published rates** — Central Bank of Uzbekistan's own table, with the publisher's own `rate_date` on every response
- 📅 **History back to 2016** — point-in-time tables and daily series for any past date
- 🔀 **Published vs derived, always flagged** — computed inverse/cross pairs carry `derived: true`, never mixed with official prints
- ⚡ **Zero dependencies** — pure ESM + CJS over global `fetch`; Node 18+, Bun, Deno, and edge runtimes
- 🔷 **Type-safe** — full TypeScript definitions shipped with the package
- 🧾 **Compliance-grade metadata** — `rate_type`, publication date, and source disclaimer on every response

> **Official rate, not mid-market:** every value here is a number Central Bank of Uzbekistan itself published, fixed once printed and carrying the central bank's own `rate_date` — what filings and audits require. Need the live mid-market rate for pricing or display instead? Use the [mid-market API](https://allratestoday.com/docs/) or [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk). The two can diverge by several percent.

## ⚡ Try it without a key

The latest Central Bank of Uzbekistan table is also served keyless, CORS-open and edge-cached, for evaluation, embeds and AI agents:

```bash
curl "https://allratestoday.com/api/open/central-bank/cbu?source=USD&target=UZS"
```

```js
const r = await fetch('https://allratestoday.com/api/open/central-bank/cbu').then((x) => x.json());
console.log(r.rate_date, r.rates.length); // the central bank's latest published table, no key
```

The open endpoint serves the *latest* table only and asks for a visible attribution link. The client below uses the keyed API, which adds point-in-time tables, history, and CSV/XML/Excel output.

## 📈 Latest published table

Today's full Central Bank of Uzbekistan table, straight from the central bank's latest publication. On GitHub it is refreshed by [a daily Action](.github/workflows/daily-table.yml) that reads the keyless endpoint above and commits only when the central bank publishes a new table; the copy on npm is as of the package's publish date.

<!-- daily-table:start -->
Published **2026-10-09** by Central Bank of Uzbekistan — 73 rates, first 60 shown. Updated 2026-10-09.

| Base | Quote | Type | Rate |
| --- | --- | --- | ---: |
| AED | UZS | reference | 3225.22 |
| AFN | UZS | reference | 182.65 |
| AMD | UZS | reference | 32.73 |
| ARS | UZS | reference | 7.81 |
| AUD | UZS | reference | 8217.97 |
| AZN | UZS | reference | 6968.57 |
| BDT | UZS | reference | 96.08 |
| BHD | UZS | reference | 31406.6 |
| BND | UZS | reference | 9237.81 |
| BRL | UZS | reference | 2359.17 |
| BYN | UZS | reference | 3876.37 |
| CAD | UZS | reference | 8299.99 |
| CHF | UZS | reference | 14209.63 |
| CNY | UZS | reference | 1767.54 |
| CUP | UZS | reference | 493.61 |
| CZK | UZS | reference | 542.5 |
| DKK | UZS | reference | 1771.69 |
| DZD | UZS | reference | 88.03 |
| EGP | UZS | reference | 226.08 |
| EUR | UZS | reference | 13240.91 |
| GBP | UZS | reference | 15631.55 |
| GEL | UZS | reference | 4565.15 |
| HKD | UZS | reference | 1509.54 |
| HUF | UZS | reference | 36.15 |
| IDR | UZS | reference | 0.662 |
| ILS | UZS | reference | 3848.04 |
| INR | UZS | reference | 122.4 |
| IRR | UZS | reference | 0.007 |
| ISK | UZS | reference | 96.65 |
| JOD | UZS | reference | 16708.84 |
| JPY | UZS | reference | 74.85 |
| KGS | UZS | reference | 135.42 |
| KHR | UZS | reference | 2.91 |
| KRW | UZS | reference | 8.82 |
| KWD | UZS | reference | 38437.93 |
| KZT | UZS | reference | 26.27 |
| LAK | UZS | reference | 0.53 |
| LBP | UZS | reference | 0.13 |
| LYD | UZS | reference | 1842.73 |
| MAD | UZS | reference | 1189.53 |
| MDL | UZS | reference | 662.37 |
| MMK | UZS | reference | 5.64 |
| MNT | UZS | reference | 3.29 |
| MXN | UZS | reference | 657.31 |
| MYR | UZS | reference | 2895.41 |
| NOK | UZS | reference | 1235.28 |
| NZD | UZS | reference | 6616.31 |
| OMR | UZS | reference | 30770.31 |
| PHP | UZS | reference | 188.05 |
| PKR | UZS | reference | 42.78 |
| PLN | UZS | reference | 3025.87 |
| QAR | UZS | reference | 3249.91 |
| RON | UZS | reference | 2477.79 |
| RSD | UZS | reference | 112.81 |
| RUB | UZS | reference | 138.95 |
| SAR | UZS | reference | 3155.38 |
| SDG | UZS | reference | 19.74 |
| SEK | UZS | reference | 1183 |
| SGD | UZS | reference | 9237.81 |
| SYP | UZS | reference | 97.09 |

[Full table on the Central Bank of Uzbekistan rates page](https://allratestoday.com/central-bank-rates-api/cbu/) · Source: [Official rates published by CBU, served by AllRatesToday](https://allratestoday.com/central-bank-rates-api/cbu/). Rates are as printed by the central bank; AllRatesToday is not affiliated with it.
<!-- daily-table:end -->

## 🔑 Get your API key

Get a free API key at [allratestoday.com/register](https://allratestoday.com/register) — no credit card required. Latest rates are on every plan, including free.

## 📦 Installation

```bash
npm install cbu-exchange-rate
```

```bash
yarn add cbu-exchange-rate
```

```bash
pnpm add cbu-exchange-rate
```

Requires Node 18+ (global `fetch`); also runs on Bun, Deno and edge runtimes. Also published under the org scope as [`@allratestoday/cbu-exchange-rate`](https://www.npmjs.com/package/@allratestoday/cbu-exchange-rate) — same code, same versions.

## 🏁 Quick start

```js
import { getRate } from 'cbu-exchange-rate';

const pair = await getRate('USD', 'UZS', { apiKey: 'art_live_...' });
console.log(pair.rate, pair.rate_date); // the official Central Bank of Uzbekistan rate, on the central bank's own date
```

## 📚 API reference

- [Latest pair rate](#latest-pair-rate) — one pair from the latest published table
- [Full published table](#full-published-table) — everything the central bank printed, in one call
- [Table for a date](#table-for-a-date) — the official table for an invoice or filing date
- [Daily time series](#daily-time-series) — one pair across a date range

---

### Latest pair rate

Free plan and up. Pairs the central bank does not print directly are resolved from its table and flagged (see *Published vs derived rates* below).

```js
const pair = await getRate('USD', 'UZS', { apiKey: 'art_live_...' });
```

**Response:**

```javascript
{
  bank: 'cbu',
  name: 'Central Bank of Uzbekistan',
  rate_date: '2026-10-08',   // Central Bank of Uzbekistan's own publication date
  source: 'USD',
  target: 'UZS',
  rate: 11809.19,
  rate_type: 'reference',
  derived: false,
  method: 'published',
  disclaimer: 'Official rates as published by the named central bank. On weekends/holidays the most recent published rate_date is returned.'
}
```

### Full published table

Free plan and up. The complete table for the latest publication date.

```js
import { getLatestRates } from 'cbu-exchange-rate';

const table = await getLatestRates({ apiKey: 'art_live_...' });
console.log(table.rate_date, table.rates.length);
```

**Response:**

```javascript
{
  bank: 'cbu',
  name: 'Central Bank of Uzbekistan',
  rate_date: '2026-10-08',
  rates: [
    { "base": "USD", "quote": "UZS", "type": "reference", "value": 11809.19 },
    // … the rest of the published table (75 currencies vs UZS)
  ],
  disclaimer: '…'
}
```

### Table for a date

Paid plans. The official table for any date since 2016 — weekends and holidays return the most recent published date, flagged via `published_on_requested_date`, which is exactly the in-force rate a filing needs.

```js
import { getRatesForDate } from 'cbu-exchange-rate';

const day = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...' });
// Optionally narrow to one pair:
const one = await getRatesForDate('2026-06-30', { apiKey: 'art_live_...', source: 'USD', target: 'UZS' });
```

**Response:**

```javascript
{
  bank: 'cbu',
  requested_date: '2026-06-30',
  rate_date: '2026-06-30',                // the date actually published
  published_on_requested_date: true,      // false when a weekend/holiday fell back
  rates: [ /* the full table for that date */ ],
  disclaimer: '…'
}
```

### Daily time series

Paid plans. One resolved rate per publication date — ready for charting, revaluation runs, or audit workpapers.

```js
import { getHistory } from 'cbu-exchange-rate';

const series = await getHistory(
  { source: 'USD', target: 'UZS', from: '2026-01-01', to: '2026-10-08' },
  { apiKey: 'art_live_...' }
);
```

**Response:**

```javascript
{
  bank: 'cbu',
  source: 'USD',
  target: 'UZS',
  from: '2026-01-01',
  to: '2026-10-08',
  count: 152,
  rates: [
    // one entry per publication date
    { date: '2026-10-08', rate: 11809.19, rate_type: 'reference', derived: false, method: 'published' },
    // …
  ],
  disclaimer: '…'
}
```

Pass `{ symbol: 'USD' }` instead of `source`/`target` to get the raw published rows for one currency (all rate types, no pair resolution).

---

## 🗺️ Currencies covered

Central Bank of Uzbekistan currently publishes rates covering **75 currencies** against the UZS (as of the latest table):

🇦🇪 `AED` · 🇦🇫 `AFN` · 🇦🇲 `AMD` · 🇦🇷 `ARS` · 🇦🇺 `AUD` · 🇦🇿 `AZN` · 🇧🇩 `BDT` · 🇧🇬 `BGN` · 🇧🇭 `BHD` · 🇧🇳 `BND` · 🇧🇷 `BRL` · 🇧🇾 `BYN` · 🇨🇦 `CAD` · 🇨🇭 `CHF` · 🇨🇳 `CNY` · 🇨🇺 `CUP` · 🇨🇿 `CZK` · 🇩🇰 `DKK` · 🇩🇿 `DZD` · 🇪🇬 `EGP` · 🇪🇺 `EUR` · 🇬🇧 `GBP` · 🇬🇪 `GEL` · 🇭🇰 `HKD` · 🇭🇺 `HUF` · 🇮🇩 `IDR` · 🇮🇱 `ILS` · 🇮🇳 `INR` · 🇮🇶 `IQD` · 🇮🇷 `IRR` · 🇮🇸 `ISK` · 🇯🇴 `JOD` · 🇯🇵 `JPY` · 🇰🇬 `KGS` · 🇰🇭 `KHR` · 🇰🇷 `KRW` · 🇰🇼 `KWD` · 🇰🇿 `KZT` · 🇱🇦 `LAK` · 🇱🇧 `LBP` · 🇱🇾 `LYD` · 🇲🇦 `MAD` · 🇲🇩 `MDL` · 🇲🇲 `MMK` · 🇲🇳 `MNT` · 🇲🇽 `MXN` · 🇲🇾 `MYR` · 🇳🇴 `NOK` · 🇳🇿 `NZD` · 🇴🇲 `OMR` · 🇵🇭 `PHP` · 🇵🇰 `PKR` · 🇵🇱 `PLN` · 🇶🇦 `QAR` · 🇷🇴 `RON` · 🇷🇸 `RSD` · 🇷🇺 `RUB` · 🇸🇦 `SAR` · 🇸🇩 `SDG` · 🇸🇪 `SEK` · 🇸🇬 `SGD` · 🇸🇾 `SYP` · 🇹🇭 `THB` · 🇹🇯 `TJS` · 🇹🇲 `TMT` · 🇹🇳 `TND` · 🇹🇷 `TRY` · 🇺🇦 `UAH` · 🇺🇸 `USD` · 🇺🇾 `UYU` · 🇻🇪 `VES` · 🇻🇳 `VND` · `XDR` · 🇾🇪 `YER` · 🇿🇦 `ZAR`

## 🏛️ Source

The Central Bank of the Republic of Uzbekistan sets official som exchange rates for around 75 currencies, used for mandatory accounting and customs valuation in Uzbekistan. The bank publishes rates daily with a full open JSON archive.

- Publisher's own page: [Exchange rate archive](https://cbu.uz/en/arkhiv-kursov-valyut/) · [cbu.uz](https://cbu.uz)
- Publication: every business day; the exact schedule, freshness status and any current delay are on the [Central Bank of Uzbekistan rates page](https://allratestoday.com/central-bank-rates-api/cbu/)
- Values are stored unmodified, with the publisher's own `rate_date` on every row — see the [methodology](https://allratestoday.com/official-rates-methodology/)

## 🧭 Reading the numbers

- `value` is always **quote currency per 1 unit of base currency** (`base: "EUR", quote: "USD", value: 1.15` means 1 EUR = 1.15 USD).
- Central Bank of Uzbekistan quotes **UZS per 1 unit of foreign currency** (e.g. `base: "USD", quote: "UZS"` means UZS per one US dollar).
- Need the other way round? Ask `getRate(target, source)` and the API inverts or crosses for you, flagged `derived: true` — never divide a published rate yourself in a compliance workflow.
- `rate_type` tells you which of the central bank's series a row belongs to (`reference` here); some publishers print buy/sell or several fixings for the same pair.

## 🧩 ERP & accounting systems

Loading the official Central Bank of Uzbekistan rate into an accounting system is a supported workflow, not a hack. Step-by-step guides with the direction each system expects:

- [Dynamics 365 Business Central](https://allratestoday.com/docs/integrations/business-central/) — built-in Currency Exchange Rate Service, no code
- [Xero](https://allratestoday.com/docs/integrations/xero/) · [QuickBooks Online](https://allratestoday.com/docs/integrations/quickbooks/) · [SAP S/4HANA and ECC](https://allratestoday.com/docs/integrations/sap/) · [Odoo](https://allratestoday.com/docs/integrations/odoo/)

The same keyed endpoints return `?format=csv`, `?format=xml` and `?format=xlsx`, and accept the key as `?api_key=` on the URL for importers that cannot send headers:

```bash
curl "https://allratestoday.com/api/v1/central-bank/cbu/latest?format=xml&api_key=art_live_..."
```

## 🤖 AI agents

- MCP server: `npx -y @allratestoday/central-bank-mcp` (stdio) or the hosted endpoint `https://allratestoday.com/api/mcp` — tools for official rates, history, cross-bank comparison and publication calendars
- Already using the general SDK or MCP server? Since 2026-10-01 [`@allratestoday/sdk`](https://www.npmjs.com/package/@allratestoday/sdk) 1.4+ has `officialRates('cbu')` and [`@allratestoday/mcp-server`](https://www.npmjs.com/package/@allratestoday/mcp-server) 0.6+ has a `get_official_rates` tool — both return this source's latest table with no key, so you can add it without a second dependency
- Claude Code plugin (no key): `/plugin marketplace add AllRates-Today/claude-code-plugin` then `/plugin install allratestoday@allratestoday` — bundles both MCP servers plus an `/official-rate cbu ...` command
- Machine-readable site guide: [llms.txt](https://allratestoday.com/llms.txt) · [for-ai-agents](https://allratestoday.com/for-ai-agents/)

## ⚖️ Published vs derived rates

If Central Bank of Uzbekistan does not print a pair directly, the API resolves it from the central bank's own table and says so — official and computed values are never confused:

| `method` | `derived` | Meaning |
| --- | --- | --- |
| `published` | `false` | The central bank printed this pair directly |
| `inverse` | `true` | Computed as 1 ÷ the published opposite direction |
| `cross` | `true` | Computed via UZS from two published rates |

## 🛡️ Error handling

Errors are thrown as `Error` with `status` (HTTP code) and `body` (the API's JSON error) attached:

```js
try {
  const pair = await getRate('USD', 'XXX', { apiKey: 'art_live_...' });
} catch (err) {
  console.log(err.message); // human-readable reason
  console.log(err.status);  // e.g. 404
}
```

| Status | Meaning |
| ------ | ------- |
| — | Missing `apiKey` (thrown before any request) |
| `400` | Malformed date or parameters |
| `401` | Invalid API key |
| `403` | Endpoint needs a [paid plan](https://allratestoday.com/pricing/) (historical dates & series) |
| `404` | Pair or date range not covered by Central Bank of Uzbekistan |
| `429` | Monthly quota exceeded |

## 🔷 TypeScript

Full definitions ship with the package — no `@types` install:

```ts
import type { LatestRates, PairRate, DatedRates, RateEntry, HistoryQuery, RequestOptions } from 'cbu-exchange-rate';
```

## 📦 CommonJS

```javascript
const { getRate } = require('cbu-exchange-rate');

getRate('USD', 'UZS', { apiKey: 'art_live_...' }).then((pair) => console.log(pair.rate));
```

## 💡 Quota tips

- Rates change once per business day — cache the published table locally and a small monthly quota goes a long way.
- Every request counts toward your AllRatesToday quota, shared across all AllRatesToday endpoints on your key.

## 📖 Methods reference

| Method | Plan | Description |
| ------ | ---- | ----------- |
| `getRate(source, target, { apiKey })` | Free | Latest rate for one pair, resolved from the published table |
| `getLatestRates({ apiKey })` | Free | The central bank's full latest published table |
| `getRatesForDate(date, { apiKey, source?, target? })` | Paid | The official table (or one pair) for a YYYY-MM-DD date |
| `getHistory({ symbol \| source+target, from?, to? }, { apiKey })` | Paid | Daily series since 2016 |

## 📥 Bulk data (no key)

Need the whole archive rather than an API call? The same published tables are mirrored daily as open data:

- Hugging Face: [AllRates/central-bank-exchange-rates](https://huggingface.co/datasets/AllRates/central-bank-exchange-rates) — one CSV per institution (`rates/cbu.csv`)
- Kaggle: [allratestoday/central-bank-exchange-rates](https://www.kaggle.com/datasets/allratestoday/central-bank-exchange-rates)
- CDN JSON: `https://cdn.jsdelivr.net/gh/AllRates-Today/central-bank-exchange-rates@main/data/cbu/latest.json`

## 🔗 Links

- [Central Bank of Uzbekistan rates page](https://allratestoday.com/central-bank-rates-api/cbu/) — live table, publication cadence, FAQ
- [All central bank sources](https://allratestoday.com/central-bank-rates-api/)
- [Package docs on the site](https://allratestoday.com/docs/sdk/cbu-exchange-rate/) · [ERP integration guides](https://allratestoday.com/docs/integrations/)
- [API documentation](https://allratestoday.com/docs/#central-bank) · [Interactive reference](https://allratestoday.com/api-reference/) · [Methodology](https://allratestoday.com/official-rates-methodology/)
- [Register (free)](https://allratestoday.com/register) · [Pricing](https://allratestoday.com/pricing/)
- [GitHub](https://github.com/AllRates-Today/cbu-exchange-rate)

## 📜 License

MIT
