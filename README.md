# BD Financial Calculator

A single-file, self-contained web calculator for Bangladesh NBFI (Non-Bank Financial Institution) deposit and loan products — built to help finance, operations, and QA teams **understand and verify** interest, tax, and loan-classification calculations, not just compute a final number.

No build step, no dependencies, no backend — open `index.html` in any browser and it works.

---

## ✨ Features

| Module | What it does |
|---|---|
| 📄 **FDR** (Fixed Deposit Receipt) | Term deposit maturity value — simple or compound interest, configurable day-count convention (365/360), compounding & payout frequency, TDS, Excise Duty, and premature encashment rules |
| 📅 **DPS** (Deposit Pension Scheme) | Recurring/installment deposit — future value of annuity, independent installment vs. compounding frequency, missed-installment handling |
| 💸 **MIS** (Monthly Income Scheme) | Periodic interest payout with principal returned at maturity |
| 🏦 **Loan EMI** | Standard reducing-balance amortization schedule with full period-by-period breakdown |
| 📆 **Accrual (Month)** | Daily/monthly/quarterly/half-yearly/annual interest accrual for a single calendar month, linked to loan classification |
| 🗓️ **Accrual (Date Range)** | Interest accrual across any custom date range, split by month-end (deposits) or month-end + due-date (loans) — shows exactly how much becomes **Income** vs. **Interest Suspense** on a day-by-day basis |
| 🔍 **Loan Classification** | Fully **editable** classification policy (overdue-month cutoffs, provisioning %, and income/suspense treatment for UC / SMA / SS / DF / BL) — the same policy drives both the Classification tab and the Accrual (Date Range) tab, so the two can never disagree |

## 🎯 Why this exists

Most deposit/loan calculators just spit out a final number. This one is built to also **teach and verify the logic behind the number**:

- Every module shows the exact formula used, with your actual numbers plugged in (a visible "show your work" formula box).
- Loan classification thresholds and provisioning rules are **editable**, not hardcoded — so you can match your own institution's policy and immediately see how a classification change flows through to income recognition and interest suspense in the Accrual (Date Range) tab.
- Day-by-day and month-by-month breakdown tables let you trace every posting instead of trusting a black-box total.

## 📐 Regulatory basis

Default values and classification thresholds are aligned to:
- Bangladesh Bank BRPD Circular No. 15 (2024)
- DFIM Circulars
- Finance Company Act 2023

> These are editable defaults, not fixed rules — update them in the Classification tab to match your organization's actual policy.

## 🚀 Getting started

No installation required.

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
open index.html   # or just double-click the file
```

Or use GitHub Pages to host it live — see [Deployment](#-deployment) below.

## 🖥️ Deployment (GitHub Pages)

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Set **Source** to `main` branch, `/ (root)` folder.
4. Your calculator will be live at `https://<your-username>.github.io/<repo-name>/`.

## 🛠️ Tech stack

- Vanilla HTML, CSS, and JavaScript — zero dependencies, zero build tools
- CSS custom properties for theming, with automatic light/dark mode via `prefers-color-scheme`
- Fully responsive — usable on mobile, tablet, and desktop

## 📁 Project structure

```
├── index.html   # Everything — markup, styles, and logic in one file
└── README.md
```

## ⚠️ Disclaimer

This tool is intended for **educational and estimation purposes**. Excise Duty is entered manually (with a slab-based reference suggestion) rather than auto-derived, and all figures should be verified against your institution's core banking/finance system before being used for official reporting or customer communication.

## 📄 License

Add your preferred license here (e.g., MIT).

## 🤝 Contributing

Issues and pull requests are welcome — especially around edge-case handling (leap years, short-month due dates, premature encashment rules) and additional NBFI product types.
