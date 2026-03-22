# stellar-ngo-tracker
Transparent, on-chain donation and spending tracker for NGOs built on Stellar
> A public, immutable donation and spending tracker for NGOs — built on Stellar. Every naira, every dollar, every cent — publicly verifiable on-chain.

![Stellar](https://img.shields.io/badge/Stellar-Network-blue?logo=stellar)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📌 Overview

Donor trust in NGOs has declined globally due to opacity in fund management. This platform leverages Stellar's public ledger to create an irrefutable, real-time record of every donation received and every expenditure made — empowering NGOs to prove their integrity.

### Key Features
- **Public Donation Ledger** — Every incoming donation visible to the world
- **Spending Transparency** — Categorized expenditures with on-chain proof
- **Impact Metrics** — See exactly what your donation funded
- **Donor Profiles** — Optional public/anonymous donation tracking
- **Multi-Signatory Withdrawals** — Require multiple approvals before spending
- **Audit Export** — Download full financial reports for regulators
- **Embeddable Widget** — NGOs can embed tracker on their own website

---

## 📁 Folder Structure

```
stellar-ngo-tracker/
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── donations.js       # Incoming donation endpoints
│   │   │   ├── expenditures.js    # Spending tracking
│   │   │   ├── campaigns.js       # Fundraising campaigns
│   │   │   ├── reports.js         # Audit report generation
│   │   │   └── public.js          # Public-facing read endpoints
│   │   ├── services/
│   │   │   ├── stellarService.js  # On-chain transaction reading
│   │   │   ├── ledgerSync.js      # Sync Stellar ledger to DB
│   │   │   ├── reportService.js   # PDF/CSV report generation
│   │   │   └── alertService.js    # Anomaly/threshold alerts
│   │   ├── models/
│   │   │   ├── Donation.js
│   │   │   ├── Expenditure.js
│   │   │   ├── Campaign.js
│   │   │   ├── NGO.js
│   │   │   └── Signatory.js
│   │   └── middleware/
│   │       ├── ngoAuth.js
│   │       └── multisig.js        # Multi-approval logic
│   └── config/
│
├── frontend/
│   └── src/
│       ├── components/
│       │   ├── DonationFeed/      # Live donation stream
│       │   ├── SpendingChart/     # Categorized spending visuals
│       │   ├── CampaignProgress/ 
│       │   ├── TransactionProof/  # Link to Stellar explorer
│       │   └── ImpactSummary/
│       ├── pages/
│       │   ├── PublicDashboard.jsx  # Publicly accessible
│       │   ├── NGOAdmin.jsx
│       │   ├── CampaignPage.jsx
│       │   └── AuditReport.jsx
│       └── hooks/
│           ├── useLedgerStream.js
│           └── useCampaign.js
│
├── blockchain/
│   ├── transactions/
│   │   └── multiSigTransaction.js  # Multi-approval payment builder
│   └── verification/
│       └── verifyTxHash.js         # Verify any tx on Stellar
│
├── docs/
│   ├── NGO_ONBOARDING.md
│   ├── DONOR_GUIDE.md
│   └── MULTI_SIG_SETUP.md
│
└── tests/
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/your-org/stellar-ngo-tracker.git
cd stellar-ngo-tracker && npm install
cp .env.example .env && npm run dev
```

---

## 🔐 Multi-Signatory Spending

All expenditures above a configurable threshold require M-of-N signatories before funds are released — enforced at the Stellar protocol level using multi-signature accounts.

---

## 📄 License

MIT © 2025 — Built on the Stellar Network
