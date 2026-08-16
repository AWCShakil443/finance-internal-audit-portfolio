# Case Study: Inventory Risk Analytics

## Business Question

Which inventory items require management attention because of low utilisation, long ageing or excess stock exposure?

## Approach

The sample dataset is intentionally synthetic. It demonstrates how an auditor or finance analyst can combine quantity, value and utilisation indicators.

### Key calculations

**Closing Value** = Closing Qty × Unit Cost

**Issue Ratio** = Issue Qty ÷ (Opening Qty + Purchase Qty)

**Non-Moving Flag** = Days Since Last Issue > 180

## Example Excel formulas

```excel
=[@[Closing_Qty]]*[@[Unit_Cost]]
```

```excel
=IFERROR([@[Issue_Qty]]/([@[Opening_Qty]]+[@[Purchase_Qty]]),0)
```

```excel
=IF([@[Days_Since_Last_Issue]]>180,"Non-moving","Active")
```

## Audit Interpretation

An item should not be classified as excess solely because it has a high closing quantity. The analysis should consider operational criticality, historical consumption, lead time, minimum stock requirements and future demand.

## Management Actions

- Review non-moving items individually
- Validate whether safety stock is justified
- Investigate purchases made despite existing stock
- Establish minimum/maximum or reorder parameters where appropriate
- Monitor ageing and utilisation monthly

## Portfolio Value

This demonstrates practical ability to move from **raw ERP-style data → analytical indicators → risk prioritisation → management action**.