# EU Tenders Scraper – TED Public Procurement Notices

EU tenders scraper for TED (Tenders Electronic Daily), the EU's official procurement journal: every new public tender, prior information notice and contract award across the EU/EEA. Filter by country, CPV code, keyword, value and deadline. Official TED Search API, no key. Pay per result.

**[Run it on Apify →](https://apify.com/devteamdrew/eu-ted-tenders?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=hero)** (pay per result, free Apify account to start)


**EU Tenders Scraper (TED)** by Moxie: fast, reliable and polite, built on official/public data sources.

## What can it do?

- Bid teams: a daily feed of new EU public tenders in your sector and countries (schedule with incremental mode)
- Market entry research: which EU buyers buy what, by CPV code and country
- Competitor intelligence: who won which EU contracts and for how much (award stage)
- Lead generation for suppliers selling to European public bodies
- Feeding tender notices into an LLM for bid/no-bid triage

## Data source

The official TED Search API v3 (`api.ted.europa.eu`) run by the Publications Office of the European Union. TED notices may be reused for commercial or non-commercial purposes under Commission Decision 2011/833/EU (source: TED, ted.europa.eu). Used within TED's fair-use limits. No login, no key.

## Features

- **Pay only for results** (pay-per-event pricing, no monthly rental)
- **Incremental mode**: scheduled runs return only items you haven't received before
- **LLM-ready output**: optional compact Markdown per item for RAG / AI agents
- **Polite rate limiting** with automatic retries and backoff
- Clean, flat JSON you can export as CSV, Excel, JSON or via API


## Quick start

1. Create a free account at [apify.com](https://apify.com/devteamdrew/eu-ted-tenders?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=quickstart) and copy your API token.
2. `export APIFY_TOKEN=...`
3. Run one of the examples:

```bash
bash examples/run.sh          # curl
node examples/run.js          # JavaScript (apify-client)
python examples/run.py        # Python (apify-client)
```

Example input ([examples/input.json](examples/input.json)):

```json
{
  "stages": [
    "tender"
  ],
  "cpvPrefixes": [
    "72"
  ],
  "lastDays": 7,
  "maxItems": 20
}
```

## FAQ

**What is TED?**
Tenders Electronic Daily is the online version of the Supplement to the Official Journal of the EU. Public buyers in the EU/EEA must publish tenders above the EU thresholds there, so it is the single best source for European public contracts.

**Do I need an account or API key?**
No. The TED Search API is open and anonymous.

**Can I use the data commercially?**
Yes. TED notices can be reused for commercial or non-commercial purposes under Commission Decision 2011/833/EU, as long as you acknowledge the source and don't distort the notices.

**Can I get winners and award values?**
Yes. Set the notice stage to `award`; `winners`, `winnerCountries` and `awardValue` are filled in.

**Are UK tenders included?**
Since 2021 UK buyers publish on Find a Tender instead. Use our UK Public Tenders actor for those.

## Use with AI agents (MCP)

Add `https://mcp.apify.com/?actors=devteamdrew/eu-ted-tenders` as an MCP server in Claude, Cursor or any MCP client.

## Pricing

See the [Apify Store page](https://apify.com/devteamdrew/eu-ted-tenders?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=pricing) for current pay-per-result pricing.

## Sample data

Browse real sample rows, download a free CSV sample and see ready-made feeds at [rowsift.co.uk](https://rowsift.co.uk/feeds/eu-ted-tenders/?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=sample-data).

## More data actors

- [Bluesky Scraper – Posts, Profiles & Search](https://apify.com/devteamdrew/bluesky-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [UK Companies House Scraper – Companies & Directors](https://apify.com/devteamdrew/companies-house-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [UK Planning Applications Scraper – 400+ Councils & Postcodes](https://apify.com/devteamdrew/uk-planning-applications?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [Hacker News Scraper – Stories, Comments & Jobs](https://apify.com/devteamdrew/hacker-news-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [npm Package Scraper – Downloads & Dependencies](https://apify.com/devteamdrew/npm-package-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [GitHub Trending Scraper – Repos, Stars & Developers](https://apify.com/devteamdrew/github-trending-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [Mastodon Scraper – Fediverse Hashtags, Accounts & Trends](https://apify.com/devteamdrew/mastodon-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [Lemmy Scraper – Posts, Comments & Communities (Fediverse)](https://apify.com/devteamdrew/lemmy-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [SEC EDGAR Scraper – 10-K, 8-K & Form D Funding Filings](https://apify.com/devteamdrew/sec-edgar-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [arXiv Scraper – Paper Search, Abstracts & Authors](https://apify.com/devteamdrew/arxiv-scraper?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [UK Government Tenders Scraper – Contracts Finder, Find a Tender](https://apify.com/devteamdrew/uk-public-tenders?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [UK CQC Care Homes & Providers Scraper – Ratings & Care Leads](https://apify.com/devteamdrew/uk-cqc-care-providers?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [SAM.gov Scraper – Federal Contract Opportunities, No API Key](https://apify.com/devteamdrew/sam-gov-opportunities?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [UK Operator Licence Scraper – HGV & Bus Operators (DVSA VOL)](https://apify.com/devteamdrew/uk-operator-licences?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)
- [USAspending Federal Awards Scraper – Contracts & Grants](https://apify.com/devteamdrew/usaspending-awards?utm_source=github&utm_medium=readme&utm_campaign=eu-ted-tenders&utm_content=more)

## License

Examples in this repository are MIT licensed. The actor itself runs on the Apify platform.
