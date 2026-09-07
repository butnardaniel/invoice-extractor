# Invoice Extractor

A folder of PDF invoices → a clean spreadsheet with monthly totals and anomaly flags.

## The problem

A bookkeeper types 200 invoices a month by hand: vendor, date, amount, line items, one PDF at a time. It is slow, and the mistakes it produces are the expensive kind — a transposed figure nobody notices until the quarter closes.

## What it does

- Reads every PDF in a folder, including scans, with an OCR fallback
- Extracts vendor, invoice number, date, net, VAT, total and line items
- Writes one tidy spreadsheet row per invoice, linked back to the source file
- Flags anomalies: duplicate invoice numbers, totals that do not sum, VAT rates outside the expected set, amounts far outside a vendor's usual range
- Produces monthly totals per vendor

## The result

An afternoon of typing becomes a few minutes of review, and the flags catch what tired eyes miss.

## How it works

Folder → parse (text layer, OCR fallback) → extract fields → validate → spreadsheet + flags

## Stack

Python (pdfplumber, Tesseract for scans, pandas), openpyxl.

## Demo

90-second video: _link to follow_

## Notes

Built as a working demonstration on 20 synthetic invoices — not from a client engagement.

Extraction is never 100 percent accurate. Anything below the confidence threshold is flagged for a human rather than quietly guessed.

---

**Daniel Butnar** — automation for marketing agencies · [butnardaniel.github.io](https://butnardaniel.github.io)

_Status: build in progress, started 7 September 2026._
# invoice-extractor
A folder of PDF invoices → a clean spreadsheet with monthly totals and anomaly flags. No retyping.
