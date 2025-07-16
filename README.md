# Transportation Cost Analysis – GitHub Portfolio Project

This project showcases a supply chain transportation cost analysis dashboard built in Power BI. It includes:
- Raw Excel data with realistic quality issues
- Data cleaning and transformation using Power Query
- Robust DAX measures for benchmarking and optimization
- An executive dashboard layout for carrier and route analysis

---

## 🔗 Data Model – Table Joins and Relationships

We created the following relationships to connect tables:

- `Shipments_raw[Route]` → `RouteTargets_raw[Route]`
- `Shipments_raw[Carrier]` → `CarrierRates_raw[Carrier]`

These relationships allow us to benchmark route-level performance, calculate potential savings, and filter across dimensions.

---

## 🎨 Design Inspiration

This dashboard’s layout and storytelling approach were inspired by the [How to Power BI YouTube channel](https://www.youtube.com/@HowtoPowerBI), which promotes clean, interactive, and insight-driven visual design.

---

See the `/documentation/` folder for full Power Query and DAX logic.