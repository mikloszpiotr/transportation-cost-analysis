# 🚚 Transportation Cost Analysis – Route-Level Benchmarking and Savings Insights

This project is a Power BI portfolio piece built to simulate a real-world transportation cost analysis dashboard for supply chain and operations teams.

---

## 🔍 Who Can Use This Dashboard
- **Supply Chain Planners**: Monitor route performance and optimize shipment planning
- **Transportation Managers**: Evaluate carrier efficiency and identify over-budget lanes
- **Sourcing/Procurement Teams**: Support contract negotiations using cost performance metrics
- **Operations Executives**: Visualize transportation KPIs and track cost-saving initiatives

---

## ❓ Business Questions Answered
- Which routes exceed their cost-per-kg benchmarks?
- Which carriers deliver the most cost-effective shipments?
- Where are our greatest savings opportunities?
- What are our total shipping costs by route, carrier, and month?
- How does our cost-per-kg trend over time?

---

## 🧠 How This Report Supports the Team
- Quantifies cost overruns and potential savings
- Allows dynamic exploration of costs by route, carrier, or date
- Enables focused corrective actions on underperforming lanes
- Serves as a decision-support tool for strategic planning and vendor evaluation

---

## 🔗 Data Model: Joins & Relationships

To enable filtering and comparison across tables, the following relationships were created:

- `Shipments_raw[Route]` → `RouteTargets_raw[Route]` (One-to-Many)
- `Shipments_raw[Carrier]` → `CarrierRates_raw[Carrier]` (Optional; used in DAX/visuals)

> These joins enable the report to map actual shipment costs against target benchmarks for variance analysis.

---

## 📁 File Structure
```
/Transportation-Cost-Analysis
├── data/                # Excel source files
├── pbix/                # Final Power BI report file
├── screenshots/         # Layout image
├── documentation/       # Transformation and DAX logic
└── README.md            # This file
```

---

## 🎨 Design Inspiration
This report’s layout and visual storytelling approach were inspired by the [How to Power BI YouTube channel](https://www.youtube.com/@HowtoPowerBI).