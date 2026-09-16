# Cheche M-Pesa Statement Converter

Turns Safaricom M-Pesa PDF statements into clean, analysed Excel workbooks.

**Live:** [chechetech.co.ke](https://chechetech.co.ke)  ·  **Infrastructure:** [cheche-infrastructure](https://github.com/Fred-Munyao/cheche-infrastructure)

## What it does

- Extracts transactions from M-Pesa PDF statements, including password-protected files
- Handles 10,000+ transactions (tested on a 2-year, 4.4 MB statement)
- Produces an Excel workbook with transaction, summary, payee, category, top-transaction, and monthly sheets
- Separates Fuliza (overdraft) from real cash flow across all sheets
- Optional formatted export adds a dashboard sheet with charts

## Privacy by design

PDF parsing runs entirely in the browser with PDF.js. Statements are never uploaded for extraction. Only the extracted data is sent to the formatting service when a user requests the formatted export.

## Architecture

```
Browser (PDF.js extraction)
   │
   ▼
CloudFront ──► S3 (static site)
   │
   ▼
API Gateway ──► Lambda (Python 3.12, openpyxl) ──► Formatted Excel
```

Payments use the M-Pesa Daraja STK Push API via API Gateway, Lambda, and DynamoDB (sandbox-tested; go-live pending Paybill approval).

All AWS resources are defined in Terraform in [cheche-infrastructure](https://github.com/Fred-Munyao/cheche-infrastructure).

## Tech stack

HTML, JavaScript, PDF.js · Python, openpyxl · AWS S3, CloudFront, API Gateway, Lambda, DynamoDB · Terraform

## Roadmap

- [ ] Daraja go-live after Paybill approval
- [ ] Phone OTP sign-in (Amazon Cognito)
- [ ] Usage tracking and free-tier enforcement
- [ ] Containerised formatter (Docker/ECS)

---

Built by [Fredrick Wambua](https://github.com/Fred-Munyao) · Cheche Technologies · Nairobi
