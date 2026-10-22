# structure.md

## Folders (target)
```
/app                 routes: /, /wrapped, /privacy, /how-to-export-phonepe-statement
/components          UI: cards/, upload/, ui/
/lib
  /parse             pdf worker + phonepe parser (+ csv later)
  /categorize        merchant normalization + rules
  /stats             pure stat functions
  /share             card -> PNG export
  /sample            fake data generator
/public              og images, icons
/tests               vitest specs + fake fixtures
```

## Data flow
File (PDF) -> Web Worker (pdf.js text + positions) -> parser -> Transaction[] -> categorizer -> stats engine -> Wrapped cards -> share PNG.
Nothing leaves the browser.

## Core contract
```
Transaction {
  id: string
  date: string        // ISO
  amountPaise: number // integer
  direction: 'debit' | 'credit'
  counterparty: string
  rawDescription: string
  category: string
  source: 'phonepe' | 'gpay' | 'paytm' | 'csv'
}
```

## Module rules
- parse: input File, output Transaction[] or typed error (WRONG_FILE, PASSWORD_REQUIRED, UNSUPPORTED_LAYOUT)
- categorize: pure, keyword map in one data file, easy to extend
- stats: pure, takes Transaction[], returns plain objects the cards render
- UI never parses; parsers never touch the DOM

## SEO routes
/ (main intent), /how-to-export-phonepe-statement, /privacy. Later: GPay, Paytm guides. /wrapped is noindex. Add sitemap, robots, OG image, JSON-LD (FAQ, WebApplication).

## Testing
Vitest for lib/*. Playwright MCP for upload -> cards flow with fake PDF.
