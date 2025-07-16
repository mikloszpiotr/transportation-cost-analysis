# Power Query Steps – Transportation Cost Analysis

This document details all data cleaning and transformation logic applied in Power Query for the Transportation Cost Analysis project. It covers three Excel files: Shipments.xlsx, CarrierRates.xlsx, and RouteTargets.xlsx.

---

## 🔹 Shipments.xlsx (Query: Shipments_raw)

### 🧹 Data Quality Issues:
- Mixed date formats (e.g., "03/12/2023", "30-12-2023")
- Extra spaces in Route names
- Comma used as decimal separator in some cost values
- Some rows missing shipment cost or weight

### 🔧 Power Query Steps:
1. **Remove Empty Rows**
2. **Trim Route Column**
3. **Standardize and Parse Date Column**
4. **Convert and Clean Shipment Cost Format**

---

## 🔹 CarrierRates.xlsx (Query: CarrierRates_raw)

### 🔧 Power Query Steps:
- Remove null `Standard Rate per Kg`
- Convert to decimal
- Trim Route values
- Remove duplicates on `Carrier + Route`

---

## 🔹 RouteTargets.xlsx (Query: RouteTargets_raw)

### 🔧 Power Query Steps:
- Remove first row
- Promote headers
- Remove Notes column
- Convert `Target Cost per Kg` to number

---

## 🔗 Data Model Integration

Relationships created in the model:
- `Shipments_raw[Route]` → `RouteTargets_raw[Route]`
- `Shipments_raw[Carrier]` → `CarrierRates_raw[Carrier]`

This enables filtering, aggregation, and benchmarking by route and carrier.