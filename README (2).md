# 📊 Monthly Release Defect Dashboard — Ecommerce QA Intelligence

> **A production-grade, interactive defect analytics dashboard built for Ecommerce Business Analysts and QA Teams.**  
> Built from raw Excel defect data · Zero dependencies · Pure HTML/CSS/JS · Opens in any browser.

---

## 🔗 Live Demo

👉 **[Open Dashboard](defect_dashboard.html)** *(download and open locally)*

---

## 📸 Dashboard Preview

> *Screenshot or GIF of your dashboard goes here*

```
Replace this block with your actual screenshot:
![Defect Dashboard Preview](assets/dashboard-preview.gif)
```

---

## 📁 Project Structure

```
defects-dashboard/
│
├── defect_dashboard.html        # 🎯 Main dashboard (single-file, no dependencies)
├── Ecommerce_Defect_List.xlsx   # 📂 Source data — 12 defects, March 2025
├── assets/
│   └── dashboard-preview.gif   # 📸 Preview GIF (add after recording)
└── README.md                   # 📖 You are here
```

---

## 🧾 Data Source

| Field | Details |
|---|---|
| **File** | `Ecommerce_Defect_List.xlsx` |
| **Sprint Period** | March 01–18, 2025 |
| **Releases** | R01, R02, R03 |
| **Total Defects** | 12 |
| **Platforms** | Flipkart · Meesho · Myntra · Amazon IN · Nykaa |
| **Columns** | Defect ID, Title, Priority, Severity, Status, Release, Module, Platform, Assigned To, Reported By, Start Date, Due Date, Resolved Date, Environment, Detection Phase, Defect Type, Description, Remarks |

---

## 📋 Dashboard Sections

### 1️⃣ Executive Summary

| Metric | Value | Status |
|---|---|---|
| Total Defects | 12 | R01×6, R02×5, R03×1 |
| Open / Active | 5 | 🔴 Needs attention |
| Closed / Resolved | 7 | ✅ 58.3% closure rate |
| Defect Density | 2.4 per module | Across 5 modules |
| MTTR | 4.2 days | Based on 5 closed defects |
| Reopen Rate | 8.3% | 1 of 12 defects reopened |
| ⚠ Critical Alert | DEF-011 | RBI compliance risk — Refund stuck in Production |

---

### 2️⃣ Defect Categories

#### By Severity

| Severity | Count | % | Risk |
|---|---|---|---|
| 🔴 Critical | 3 | 25% | P1 open — escalate immediately |
| 🟠 High | 4 | 33% | 50% closure rate |
| 🟡 Medium | 3 | 25% | 1 reopened (DEF-008) |
| 🟢 Low | 2 | 17% | 100% closed |
| **Total** | **12** | **100%** | **Critical+High = 58%** |

#### By Priority

| Priority | Label | Count | % |
|---|---|---|---|
| P1 | Blocker | 3 | 25% |
| P2 | Major | 4 | 33% |
| P3 | Normal | 4 | 33% |
| P4 | Minor | 2 | 17% |

> ⚡ **P1 open:** DEF-011 (Refund Engine, Flipkart, Production) — **ESCALATE**

---

### 3️⃣ Lifecycle Insights

```
Newly Reported  ──► 12  (Full sprint intake)
                     │
         ┌───────────┼───────────┐
         ▼           ▼           ▼
      Closed (5)  Resolved (1)  In Progress (2)
                                    │
                               Reopened (1)
                                    │
                                 Open (3)
```

| Lifecycle State | Count | Defect IDs |
|---|---|---|
| 🆕 Newly Reported | 12 | DEF-001 to DEF-012 |
| ✅ Closed | 5 | DEF-001, DEF-002, DEF-005, DEF-006, DEF-012 |
| 🔵 Resolved | 1 | DEF-003 |
| 🟡 In Progress | 2 | DEF-007, DEF-010 |
| 🟠 Reopened | 1 | DEF-008 (iOS Safari — OTP session) |
| 🔴 Open | 3 | DEF-004, DEF-009, DEF-011 |
| ⏸ Deferred | 0 | — |
| ❌ Rejected | 0 | — |

---

### 4️⃣ Distribution

#### By Module / Feature

| Module | Defects | Severity | Status |
|---|---|---|---|
| Payment Module | 1 | Critical | Closed |
| OMS | 1 | High | Closed |
| Inventory Service | 1 | High | Resolved |
| Returns Module | 1 | High | Open |
| Promotions Engine | 1 | Critical | Closed |
| Logistics Engine | 1 | Medium | Closed |
| Notification Service | 1 | Medium | In Progress |
| User Profile Service | 1 | Medium | Reopened |
| Search Service | 1 | Low | Open |
| Checkout Service | 1 | High | In Progress |
| Refund Engine | 1 | Critical | Open ⚠ |
| Analytics Dashboard | 1 | Low | Closed |

#### By Environment

| Environment | Count | % | Insight |
|---|---|---|---|
| 🔴 Production | 5 | 42% | ⚠ Leakage — UAT coverage gap |
| 🟡 Staging | 4 | 33% | Integration issues dominant |
| 🔵 UAT | 2 | 17% | Business logic gaps |
| 🟢 QA / SIT | 1 | 8% | Low exploratory coverage |

> ⚠ **42% of defects leaked to Production** — critical signal to strengthen pre-prod testing coverage for Payment, Refund, and Promotions modules.

---

### 5️⃣ Root Cause Analysis

| # | Root Cause | Count | % | Key Defects |
|---|---|---|---|---|
| 1 | 🐛 Code / Functional Issues | 5 | 41.7% | DEF-001, DEF-002, DEF-005, DEF-008, DEF-011 |
| 2 | 🔄 Data Sync / Quality | 2 | 16.7% | DEF-003, DEF-006 |
| 3 | 📋 Requirement / Business Logic | 2 | 16.7% | DEF-004, DEF-009 |
| 4 | 🔗 Integration Issues | 2 | 16.7% | DEF-007, DEF-010 |
| 5 | ⚙️ Configuration | 1 | 8.3% | DEF-012 |
| 6 | 🖥️ Performance / Environment | 1 | 8.3% | DEF-007 |

> 🔑 **Code issues = 41.7% of all defects.** Dev-side unit testing and peer code review practices need strengthening. Data sync gaps (DEF-003, DEF-006) indicate WMS ↔ portal integration SLA issues.

---

### 6️⃣ Defect Aging (Open Defects Only)

| Aging Bucket | Count | % | Defect IDs | Action |
|---|---|---|---|---|
| 🔴 > 30 days | 3 | 60% | DEF-004 (42d), DEF-007 (37d), DEF-010 (33d) | Immediate PM escalation |
| 🟡 15–30 days | 1 | 20% | DEF-009 (34d, R03) | Next sprint planned |
| 🟢 < 15 days | 1 | 20% | DEF-011 (32d, P1) | Active escalation in progress |

> ⚡ **60% of open defects are aged >30 days.** Triage required for DEF-004, DEF-007, DEF-010, DEF-011.

---

### 7️⃣ Trends

#### Weekly Defect Arrival vs Closure

| Week | Period | Arrivals | Closures | Net Backlog |
|---|---|---|---|---|
| Week 1 | Mar 01–07 | 5 | 4 | +1 |
| Week 2 | Mar 08–14 | 4 | 2 | +2 |
| Week 3 | Mar 15–18 | 3 | 1 | +2 |
| **Total** | | **12** | **7** | **+5** |

```
Arrival  █████ ████ ███
Closure  ████  ██   █
         W1    W2   W3
```

#### Key Trend Metrics

| Metric | Value | Signal |
|---|---|---|
| Avg Weekly Arrival Rate | 4.0 / week | Steady |
| Avg Weekly Closure Rate | 2.3 / week | ⚠ Slowing |
| Backlog Growth Rate | +1.7 / week | 🔴 Growing |
| Reopen Rate | 8.3% | ✅ Within target (<10%) |
| Defect Leakage to Production | 41.7% | 🔴 High |

> ⚠ **Closure rate (2.3/wk) is lagging behind arrival rate (4.0/wk).** Defect backlog growing by ~1.7/week. Immediate team bandwidth review required.

---

### 8️⃣ Leadership Metrics

| KPI | Value | Benchmark | Status |
|---|---|---|---|
| MTTR (Mean Time to Resolve) | 4.2 days | < 5 days | ✅ On track |
| Fix Quality (Reopen %) | 8.3% | < 10% | ✅ Acceptable |
| Overall Closure Rate | 58.3% | > 70% | 🔴 Below target |
| Defect Leakage to Prod | 41.7% | < 20% | 🔴 Critical |
| P1 Open Count | 1 | 0 | 🔴 Escalate |

#### Closure % by Severity

| Severity | Total | Closed | Closure % | Status |
|---|---|---|---|---|
| 🔴 Critical | 3 | 2 | 67% | ⚠ 1 P1 open |
| 🟠 High | 4 | 2 | 50% | 🔴 Low |
| 🟡 Medium | 3 | 2 | 67% | ⚠ 1 reopened |
| 🟢 Low | 2 | 2 | 100% | ✅ Complete |

#### 🏆 Top 3 Modules with Highest Defect Risk

| Rank | Module | Defects | Open | Severity | Revenue Impact |
|---|---|---|---|---|---|
| 🥇 1st | Payment + Refund Engine | 2 | 1 (P1) | Critical | RBI compliance risk |
| 🥈 2nd | OMS + Checkout Service | 2 | 1 | High | Cross-platform (12% users) |
| 🥉 3rd | Promotions + Inventory | 2 | 0 | Critical+High | ₹1.2L revenue impacted |

---

## 📌 Full Defect Register

| Defect ID | Title | Priority | Severity | Status | Release | Module | Platform | Environment | Start | Resolved |
|---|---|---|---|---|---|---|---|---|---|---|
| DEF-001 | Payment gateway charges customer twice | P1 | Critical | ✅ Closed | R01 | Payment Module | Flipkart | Production | Mar 01 | Mar 03 |
| DEF-002 | Order status stuck at Processing 72h | P2 | High | ✅ Closed | R01 | OMS | Meesho | Staging | Mar 03 | Mar 06 |
| DEF-003 | Out-of-stock item allowed at checkout | P2 | High | 🔵 Resolved | R01 | Inventory Service | Myntra | Production | Mar 05 | Mar 08 |
| DEF-004 | Return window expired incorrectly | P2 | High | 🔴 Open | R02 | Returns Module | Amazon IN | UAT | Mar 07 | — |
| DEF-005 | Double discount — flash sale + coupon | P1 | Critical | ✅ Closed | R01 | Promotions Engine | Nykaa | Production | Mar 09 | Mar 10 |
| DEF-006 | Order routed to wrong logistics hub | P3 | Medium | ✅ Closed | R01 | Logistics Engine | Flipkart | Production | Mar 10 | Mar 13 |
| DEF-007 | Order confirmation email not sent (COD) | P3 | Medium | 🟡 In Progress | R02 | Notification Service | Meesho | Staging | Mar 12 | — |
| DEF-008 | OTP update not saved — session timeout | P3 | Medium | 🟠 Reopened | R02 | User Profile Service | Myntra | UAT | Mar 14 | Mar 18 |
| DEF-009 | Sponsored products in Newly Launched | P4 | Low | 🔴 Open | R03 | Search Service | Amazon IN | QA | Mar 15 | — |
| DEF-010 | Saved address lost on app ↔ mobile web | P2 | High | 🟡 In Progress | R02 | Checkout Service | Nykaa | Staging | Mar 16 | — |
| DEF-011 | Refund ₹4,999 stuck — RBI risk ⚠ | P1 | Critical | 🔴 Open | R01 | Refund Engine | Flipkart | Production | Mar 17 | — |
| DEF-012 | Seller dashboard GMV showing stale data | P4 | Low | ✅ Closed | R02 | Analytics Dashboard | Meesho | Production | Mar 18 | Mar 19 |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Dashboard | Pure HTML5 + CSS3 + Vanilla JS |
| Data Source | Microsoft Excel (.xlsx) |
| Data Processing | Python · pandas |
| Fonts | IBM Plex Mono · IBM Plex Sans (Google Fonts) |
| Charts | Custom SVG + CSS bar charts |
| Hosting | Local / GitHub Pages |
| Dependencies | **Zero** — single HTML file |

---

## 🚀 How to Use

```bash
# 1. Clone the repo
git clone https://github.com/mohamedshameem-dev/defect-dashboard.git

# 2. Open the dashboard
cd defect-dashboard
open defect_dashboard.html        # macOS
start defect_dashboard.html       # Windows
xdg-open defect_dashboard.html    # Linux
```

> No server needed. No npm install. No Python required. Just open in any browser.

---

## 💡 Skills Demonstrated

```
✅ Ecommerce QA Domain Knowledge     — defect lifecycle, severity triage, leakage analysis
✅ Business Analysis                  — executive summaries, KPI selection, stakeholder-ready output
✅ Data Analysis with Python/pandas   — Excel ingestion, metric derivation, trend calculation
✅ Dashboard Design                   — dark-theme UI, section hierarchy, visual encoding
✅ Root Cause Structuring             — RCA categorization aligned to BA frameworks
✅ Leadership Communication           — MTTR, reopen%, closure rate framed for PM/PO audience
```

---

## 👤 Author

**Mohamed Shameem**  
Business Analyst · QA Lead · Ecommerce Analytics  
📍 Chennai, India

[![GitHub](https://img.shields.io/badge/GitHub-mohamedshameem--dev-181717?style=flat&logo=github)](https://github.com/mohamedshameem-dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/your-linkedin-handle)

---

## 📄 License

MIT License — free to use, adapt, and share with attribution.

---

*Built as part of the **2026 Ecommerce BA Projects** portfolio series.*
