# July 2025 Billing Audit - Join Notes

This document describes the joins performed to map billing codes to clients and lists the current unmatched records.

## Files Used

- `July 2025 - USA.csv` (billing detail; line-level rows with `Order No`, `Part No`, `Description`, `Ext Price`)
- `July 2025 - USA - Sales Orders.csv` (order-level bridge with `Order  #` and `Customer Code`)
- `July 2025 - USA - Customers.csv` (customer master with `Code` and `Customer Name`)
- `July 2025 - USA - Sales Orders - With Customers.csv` (intermediate file with customer names added)
- `July 2025 - USA - Billing With Customers.csv` (final audit output)

## Joins Performed

### Join 1: Sales Orders -> Customers

- **Purpose:** Attach customer names to each sales order.
- **Join keys:** `Sales Orders.Customer Code` = `Customers.Code`
- **Type:** Left join from Sales Orders.
- **Output column added:** `Customer Name (from master)`
- **Output file:** `July 2025 - USA - Sales Orders - With Customers.csv`

### Join 2: Billing -> Sales Orders (With Customers)

- **Purpose:** Attach client data to every billing line so billing codes can be audited by client.
- **Join keys:** `Billing.Order No` = `Sales Orders.Order  #`
- **Type:** Left join from Billing (keeps all billing rows).
- **Client columns added first in output:**
  - `Customer Code`
  - `Customer Name (from master)`
  - `Ship To`
  - `Ship To Name`
- **Output file:** `July 2025 - USA - Billing With Customers.csv`

## Result Summary (Current Run)

- Billing rows in source: `9320`
- Rows in final output: `9320`
- Unmatched billing rows (blank `Customer Code`): `39`
- Unmatched unique order numbers: `10`

## Missing/Unmatched Order Numbers

These order numbers exist in billing rows but did not find a match in `Sales Orders - With Customers` using `Order No` = `Order  #`:

- `1960879`
- `1964965`
- `1965509`
- `1966125`
- `1966164`
- `1966167`
- `1972596`
- `1972623`
- `1972879`
- `1972880`

## Notes for Audit Follow-Up

- Review the unmatched order numbers in the monthly Sales Orders extract to confirm whether they are missing, delayed, or use a different order identifier.
- If needed, run a stricter or alternative join (for example including extension fields) to test whether mismatches are due to key format differences.
