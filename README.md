# Cheche M-Pesa Statement Converter

A web-based tool that converts Safaricom M-Pesa PDF statements into clean, 
filterable Excel files instantly — built for Kenyan individuals, accountants, 
and financial institutions.

## Features

- 🔓 Unlocks password-protected M-Pesa PDFs (6-digit SMS code)
- 📝 Direct text extraction — 100% accurate on original Safaricom PDFs
- 🧹 Removes Safaricom approval stamp before processing
- ✂️ Preserves split charge + transfer rows correctly
- 🔍 Filter by name, business, or keyword (comma-separated)
- 📊 Full names and amounts on every row
- 🔐 Everything processed in browser — your data never leaves your device

## Live Demo

**[Launch Converter](http://cheche-converter-app-dev.s3-website-us-east-1.amazonaws.com)**

## Tech Stack

- Vanilla HTML, CSS, JavaScript
- PDF.js — PDF text extraction
- SheetJS (XLSX) — Excel file generation
- AWS S3 — static website hosting
- AWS CloudFront — CDN (coming soon)

## Pricing

| Plan | Price | Conversions |
|---|---|---|
| Free | KES 0 | 1 per month |
| Pro | KES 199/month | 10 per month |
| Business | KES 799/month | Unlimited |

## Author

**Fredrick Munyao Wambua**
AWS Certified Solutions Architect – Associate
Founder, Cheche Technologies | chechetech.co.ke