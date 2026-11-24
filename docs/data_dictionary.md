# Data Dictionary

Source file: `data/SupplyChain_Dashboard_Dataset.xlsx`. Column names and types are read directly from the workbook.


## Dim_Date

*365 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `Date` | date | 2025-01-01 |
| `Year` | integer | 2025 |
| `MonthNum` | integer | 1 |
| `MonthName` | text | Jan |
| `MonthYear` | text | Jan 2025 |
| `Quarter` | text | Q1 |
| `WeekNum` | integer | 1 |
| `DayOfWeek` | text | Wed |
| `MonthEnd` | date | 2025-01-31 |

## Dim_Region

*5 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `RegionID` | integer | 1 |
| `Region` | text | North America |
| `RegionCode` | text | EU |

## Dim_Supplier

*320 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `SupplierID` | text | SUP001 |
| `SupplierName` | text | Supplier A |
| `Country` | text | Egypt |
| `RegionID` | integer | 5 |
| `SupplyCategory` | text | Automotive |
| `Status` | text | Active |
| `RiskStatus` | text | Normal |
| `OnboardDate` | date | 2020-11-03 |
| `CostIndex` | decimal | 92.3 |
| `OverallScore` | decimal | 94.2 |
| `Tier` | text | Strategic |

## Dim_Product

*3,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `ProductID` | integer | 101 |
| `ProductName` | text | Product 101 |
| `Category` | text | Furniture |
| `UnitCost` | decimal | 34.0344 |
| `UnitPrice` | decimal | 52.54 |
| `MaxStockLevel` | integer | 5260 |
| `ABC_Class` | text | A |
| `PrimarySupplierID` | text | SUP052 |

## Dim_Plant

*25 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `PlantID` | text | PL01 |
| `PlantName` | text | NA Plant 1 |
| `RegionID` | integer | 1 |
| `Country` | text | Canada |

## Dim_Warehouse

*18 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `WarehouseID` | text | DC01 |
| `WarehouseName` | text | NA Warehouse 1 |
| `RegionID` | integer | 1 |
| `Country` | text | USA |

## Dim_Hub

*52 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `HubID` | text | HB01 |
| `HubName` | text | NA Hub 1 |
| `RegionID` | integer | 1 |
| `Country` | text | Canada |

## Dim_Carrier

*5 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `CarrierID` | integer | 1 |
| `CarrierName` | text | Carrier A |
| `CarrierType` | text | Road & Rail |

## Dim_TransportMode

*4 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `TransportMode` | text | Road |
| `ModeSort` | integer | 1 |

## Fact_Orders

*48,752 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `OrderID` | text | ORD-000001 |
| `OrderDate` | date | 2025-01-01 |
| `DeliveryDate` | date | 2025-01-07 |
| `RegionID` | integer | 1 |
| `WarehouseID` | text | DC05 |
| `HubID` | text | HB13 |
| `Revenue` | decimal | 103.47 |
| `LeadTimeDays` | decimal | 5.8 |
| `PromisedLeadDays` | decimal | 6.6 |
| `OnTimeFlag` | integer | 1 |
| `InFullFlag` | integer | 1 |
| `OTIFFlag` | integer | 1 |

## Fact_Shipments

*18,752 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `ShipmentID` | text | SHP-000001 |
| `ShipDate` | date | 2025-01-01 |
| `DeliveryDate` | date | 2025-01-04 |
| `RegionID` | integer | 2 |
| `CarrierID` | integer | 1 |
| `TransportMode` | text | Road |
| `OriginWarehouseID` | text | DC09 |
| `ShippingCost` | decimal | 49.25 |
| `PlannedTransitDays` | decimal | 2.9 |
| `TransitDays` | decimal | 2.9 |
| `DelayDays` | decimal | 0.0 |
| `OnTimeFlag` | integer | 1 |
| `DelayedFlag` | integer | 0 |

## Fact_InventorySnapshot

*36,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `SnapshotDate` | date | 2025-01-31 |
| `ProductID` | integer | 101 |
| `OnHandQty` | integer | 5506 |
| `UnitCost` | decimal | 34.0344 |
| `InventoryValue` | decimal | 187393.41 |
| `UnitsIssued` | integer | 754 |
| `COGS` | decimal | 25661.94 |
| `DaysOfInventory` | decimal | 226.4 |
| `ReorderPoint` | integer | 2638 |
| `ReorderNeededFlag` | integer | 0 |
| `StockoutFlag` | integer | 0 |
| `ExcessQty` | integer | 246 |
| `OverstockFlag` | integer | 1 |
| `OverstockValue` | decimal | 8372.46 |
| `SlowMovingFlag` | integer | 1 |
| `AtRiskFlag` | integer | 0 |
| `ReorderQty` | decimal | 38.0 |
| `ETADays` | decimal | 4.0 |

## Fact_PurchaseOrders

*12,000 rows*

| Column | Data type | Example |
|--------|-----------|---------|
| `POID` | text | PO-000001 |
| `PODate` | date | 2025-01-01 |
| `ReceiptDate` | date | 2025-01-05 |
| `SupplierID` | text | SUP001 |
| `QtyOrdered` | integer | 149 |
| `QtyReceived` | integer | 149 |
| `QtyDefective` | integer | 3 |
| `PromisedLeadDays` | decimal | 4.2 |
| `ActualLeadDays` | decimal | 4.0 |
| `OnTimeFlag` | integer | 1 |
| `QualityPassFlag` | integer | 1 |
| `POValue` | decimal | 258.11 |
