# 📣 Marketing Campaign Performance Dashboard (Power BI)

An interactive **Power BI** dashboard that tracks and evaluates multi-channel marketing campaigns —
measuring **ROI, conversion rates, and cost efficiency** across platforms to guide budget allocation.

Delivered as an open, source-control-friendly **`.pbip`** (Power BI Project).

---

## 🎯 Objective
Help a marketing / performance team answer: *Which campaigns and platforms deliver the best ROI?
Which audience segments convert? Where should we shift budget to improve customer acquisition?*

## 📦 Dataset
Synthetic, internally-consistent campaign data — **150 campaigns across 6 platforms, 2024**.
File: [`data/marketing_campaigns.csv`](data/marketing_campaigns.csv) (also embedded in the model).

Columns: Campaign ID/Name/Type, Platform (Google/Facebook/Instagram/LinkedIn/Email/YouTube),
Start/End Date, Region, Audience Segment, Impressions, Clicks, CTR %, Leads Generated, Conversions,
Conversion Rate %, Marketing Spend, Revenue Generated, ROI %, CPC, CPM, CAC. (CTR = Clicks/Impressions,
Conversions ≈ 1–5% of clicks, ROI = (Revenue−Spend)/Spend, etc.)

## 🧱 Model & DAX
Star schema: **Campaigns** fact + a **DateTable** (`List.Dates`) related on `Campaign Start Date → Date`.
Measures (named to avoid clashing with same-named columns): `Total Spend`, `Total Revenue`,
`Total Impressions/Clicks/Leads/Conversions`, `Total Campaigns`, `ROI`, `CTR`, `Conv Rate`,
`Cost per Click`, `Cost per Mille`, `Acquisition Cost`, `Revenue per Campaign`.

## 📊 Dashboard (3 pages)
1. **Campaign Overview** — KPI cards (Spend, Revenue, ROI, CTR, Conv Rate), revenue trend, Spend vs Revenue by Platform, ROI by Campaign Type, slicers.
2. **Platform & Funnel** — impression/click/lead/conversion KPIs, conversion funnel, CPC & CPM by platform, CTR/Conv trend.
3. **Audience & Region** — revenue map by region, conversions by audience segment, acquisition cost by segment, top-campaigns table.
A left slicer panel (Platform, Campaign Type, Audience Segment, Year) cross-filters every page.

## 💡 Key Insights (sample data)
- **Overall ROI ≈ 190%** on ₹1.48 Cr spend → ₹4.30 Cr revenue (19,562 conversions, avg CAC ≈ ₹891).
- **YouTube (247%) and Email (218%) lead ROI**; **Instagram (131%) lags** — a budget-reallocation signal.
- High-reach platforms aren’t always the most efficient — compare CTR and CAC, not just impressions.

## 🚀 Open it
Open [`dashboard/Marketing Campaign Performance Dashboard.pbip`](dashboard/Marketing%20Campaign%20Performance%20Dashboard.pbip)
in **Power BI Desktop (2026)**. Data is embedded (no path to fix). Allow Azure/Bing maps for the regional map.

## 📁 Structure
```
README.md
data/marketing_campaigns.csv
dashboard/  <.pbip + .SemanticModel + .Report>
```

## ✅ Conclusion
An end-to-end marketing-analytics BI build (modelling, DAX, multi-page design) that turns raw campaign
data into budget decisions. Future work: attribution modelling, CLV, and forecasted campaign performance.
