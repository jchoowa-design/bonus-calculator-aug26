# Commission Calculator

A single self-contained page that works out a week's fundraising commission under the
point system. Enter the week's sign-ups; it shows the points, the qualifying threshold,
the debit cap, the average gift and the resulting pay.

## What this repo may contain

**Only `index.html`, `robots.txt`, this README and `.gitignore`.**

If this site is served publicly, then everything committed here is public — including
anything committed once and deleted later, because it stays in the git history. Never add:

- signup, payroll, attendance or donor data (`.xlsx`, `.csv`, `.parquet`)
- employee names, employee numbers or fundraiser IDs
- company totals, cost figures or anyone's pay
- the analysis scripts or any memo, deck or report

The `.gitignore` blocks these file types as a safety net, but it is a backstop, not a
substitute for checking `git status` before you commit.

## Privacy

The page makes **no network requests of any kind** — no fonts, no scripts, no analytics,
no tracking. Everything typed into it stays on the device and is never transmitted or
stored. There is no login and no personal data is collected or processed.

It works fully offline once loaded, so it can also simply be sent as a file rather
than hosted.

## Publishing

Served as a static page from the repository root. `index.html` carries a
`noindex, nofollow` tag and `robots.txt` disallows crawlers, so the link works for anyone
who has it but will not appear in search results.

## Authority

This is an estimate, provided for convenience. Appendix 2 of the employment agreement is
the authority in all cases. Only approved sign-ups with a rehash recording count, and a
monthly pledge above ฿2,000 counts as ฿2,000.

## Updating

Edit `index.html` and commit. The point tables, thresholds and caps are declared together
at the top of the `<script>` block:

```js
const CC = {...};   // credit points by age band x site category
const DC = {...};   // debit points
const GATE = {FR:5.0, TL:7.5}, DC_CAP = 0.30, GIFT_CAP = 2000, UPFRONT = 0.70;
```

Change those constants and nothing else moves — the rest of the page reads from them.
