# KPI Definitions

Business definitions used across the four dashboard pages. Field names refer to the dataset in `data/`.

## Executive Overview
| KPI | Definition |
|-----|-----------|
| Total Orders | Count of `OrderID` in `Fact_Orders` |
| Revenue | Sum of `Revenue` |
| Inventory Value | Sum of `InventoryValue` in `Fact_InventorySnapshot` |
| OTIF % | Orders with `OTIFFlag = 1` / total orders |
| Avg Lead Time | Average `LeadTimeDays` |
| Stockout Rate | Share of snapshots with `StockoutFlag = 1` |
| Logistics Cost | Sum of `ShippingCost` in `Fact_Shipments` |
| Supplier Performance | Average supplier score (see weights below) |

## Inventory Intelligence
| KPI | Definition |
|-----|-----------|
| Avg Inventory | Average inventory value across snapshots |
| COGS | Sum of `COGS` |
| Inventory Turnover | COGS / Average Inventory |
| Days of Inventory | Average `DaysOfInventory` |
| Overstock Value | Sum of `OverstockValue` |
| Slow Moving % | Share of snapshots with `SlowMovingFlag = 1` |
| At Risk SKUs | Count of products with `AtRiskFlag = 1` |
| Reorder Needed | Count of products with `ReorderNeededFlag = 1` |

## Supplier Performance
| KPI | Definition |
|-----|-----------|
| On-Time Delivery | Purchase orders with `OnTimeFlag = 1` / total POs |
| Quality % | Purchase orders with `QualityPassFlag = 1` / total POs |
| Avg Lead Time | Average `ActualLeadDays` |
| Defect Rate | `QtyDefective` / `QtyReceived` |
| Fill Rate | `QtyReceived` / `QtyOrdered` |
| Total Spend | Sum of `POValue` |

**Supplier Score weights**

| Component | Weight |
|-----------|:------:|
| On-Time Delivery | 30% |
| Quality (Defect Rate) | 25% |
| Lead Time | 20% |
| Cost (Purchase Price) | 15% |
| Fill Rate | 10% |

## Logistics Performance
| KPI | Definition |
|-----|-----------|
| On-Time Delivery | Shipments with `OnTimeFlag = 1` / total shipments |
| Avg Transit Time | Average `TransitDays` |
| Avg Delivery Delay | Average `DelayDays` |
| Shipment Volume | Count of `ShipmentID` |
| Delayed Shipments | Count where `DelayedFlag = 1` |
| Cost per Shipment | Sum of `ShippingCost` / shipment count |

> These definitions describe the standard calculation for each KPI. If your Power BI DAX measures differ slightly, update this file to match.
