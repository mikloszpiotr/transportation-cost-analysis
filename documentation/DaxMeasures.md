# 📐 DAX Measures – Cleaned Version

These DAX measures were created in a separate "DAX Measures" table for modularity and clarity in the Power BI data model.

---

## 🔢 Aggregations & KPIs

### 1. Total Shipment Cost
```DAX
Total Shipment Cost = SUM(Shipments_raw[Shipment Cost])
```
> Measures total transportation spend.

### 2. Total Weight
```DAX
Total Weight = SUM(Shipments_raw[Weight (kg)])
```
> Sum of all shipped weight across all routes.

### 3. Cost per Kg
```DAX
Cost per Kg = DIVIDE([Total Shipment Cost], [Total Weight])
```
> Main KPI to monitor transportation cost efficiency per unit weight.

### 4. Avg Target Cost per Kg
```DAX
Avg Target Cost per Kg = AVERAGE(RouteTargets_raw[Target Cost per Kg])
```
> Company-defined average benchmark for acceptable transportation costs.

### 5. Cost Variance
```DAX
Cost Variance = [Cost per Kg] - [Avg Target Cost per Kg]
```
> Shows the gap between actual and target cost per kg. Positive = overrun.

### 6. Potential Savings
```DAX
Potential Savings = 
SUMX(
    Shipments_raw,
    Shipments_raw[Weight (kg)] *
    (
        [Cost per Kg] -
        LOOKUPVALUE(
            RouteTargets_raw[Target Cost per Kg],
            RouteTargets_raw[Route],
            Shipments_raw[Route]
        )
    )
)
```
> Total possible savings if every shipment met the target cost per kg.

### 7. Total Cost (Selected Route)
```DAX
Total Cost (Selected Route) =
CALCULATE(
    SUM(Shipments_raw[Shipment Cost]),
    Shipments_raw[Route] = SELECTEDVALUE(Shipments_raw[Route])
)
```
> Slicer-based cost aggregation, useful for drilldowns by route.

---

## ❓ Business Questions Answered:
- How much do we spend on transportation overall and per route?
- Are we shipping above or below our target cost per kg?
- Where is the largest opportunity for cost savings?
- What’s the impact of each route selection on total cost?