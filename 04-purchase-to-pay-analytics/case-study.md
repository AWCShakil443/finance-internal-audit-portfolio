# Case Study: Purchase-to-Pay Cycle Analytics

## Objective

Identify delays and quantity mismatches across the PR → PO → GRN process.

## Core Measures

**PR-to-PO Days** = PO Date − PR Date

**PO-to-GRN Days** = GRN Date − PO Date

**Quantity Variance** = PO Quantity − GRN Quantity

## Example Excel formulas

```excel
=[@[PO_Date]]-[@[PR_Date]]
```

```excel
=[@[GRN_Date]]-[@[PO_Date]]
```

```excel
=[@[PO_Qty]]-[@[GRN_Qty]]
```

## Exception Rules

| Test | Example Flag |
|---|---|
| PR-to-PO > 30 days | Procurement delay |
| PO-to-GRN > 60 days | Receiving / supplier delay |
| GRN Qty < PO Qty | Quantity short receipt |
| Unusual date sequence | Data quality exception |

## Audit Interpretation

Cycle-time exceptions should be investigated by separating internal processing delays from supplier or logistics delays. Quantity differences should be reconciled with purchase orders, delivery documents and receiving records before concluding that a control failure exists.

## Management Dashboard

Recommended metrics include median cycle time, average cycle time, percentage exceeding threshold, open transactions, supplier comparison and quantity variance.