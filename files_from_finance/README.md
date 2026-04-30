# Finance source files (`files_from_finance`)

This folder holds **raw and derived CSVs** from Finance for KHQ billing work: monthly billing detail, sales-order extracts used to attach **customer codes** to orders, and a **customer master** used to resolve codes to names.

## The three file roles

| Role | What it is | How often it changes |
|------|------------|----------------------|
| **Original billing file** | The monthly billing extract Francis sends (line-level charges, parts, amounts, dates). | **Every month** — new file per billing period. |
| **Sales orders file** | Order-level extract with **order number** and **customer code** for that month. | **Every month** — matches the billing period you are closing. |
| **Customer master file** | Maps **customer code → customer name** (and related master fields as provided). | **Mostly static** — reuse until new customers are added or names change. |

### How they work together

1. **Billing** rows include an order identifier (e.g. `Order No`).
2. **Sales orders** link that order identifier to a **customer code**.
3. **Customer master** turns that code into a **customer name** for reporting and QA.

Typical join chain:

`Billing (Order No)` → `Sales Orders (Order #, Customer Code)` → `Customers (Code, Customer Name)`

## ItemID prefixes: iDoxs vs DocWeb (normalization for queries)

**Simple summary**

- **iDoxs** always sends **NYC-coded** billing data: ItemIDs use the **IX1** pattern (digit `1` after `IX`).
- **DocWeb** does **not** pass the file through unchanged. It **re-maps** billing items using the account’s **billing location** configured in DocWeb, then sends **one finalized file** to Epicor. That remap changes the regional digit in ItemIDs (e.g. **IX3** for LA).
- **Finance / Epicor extracts** in this folder can therefore show **IX1**, **IX2**, **IX3**, **IX6**, etc. on the same logical product family. For **queries that assume the iDoxs (NYC) shape**, normalize those identifiers **to IX1** (replace the regional digit with `1` after `IX`) so all rows compare consistently.

**ItemID prefix → region** (the digit immediately after `IX`)

| ItemID prefix (after `IX`) | Region |
|----------------------------|--------|
| 1 | NYC |
| 2 | MISS |
| 3 | LA |
| 6 | DAL |

Examples: `IX1…` = NYC, `IX2…` = MISS, `IX3…` = LA, `IX6…` = DAL.

Apply this normalization **before** joins or lookups that were built or tested against **IX1**-coded reference data.

## Customer master (key file)

The customer lookup file used for this workflow lives **at the root of `files_from_finance`** (not inside a month folder):

- **`July 2025 - USA - Customers.csv`** — customer key / master file.

Headers include **`Customer Name`** and **`Code`** (customer code). Use this file (or an updated export from the same source) unless Finance supplies a newer master.

## Folder layout by period

Each **billing period** usually has its own subfolder under `files_from_finance`, often with a `csv/` subfolder for extracts.

**Examples in this repo:**

| Folder | Notes |
|--------|--------|
| `Dec24-Jan25/csv/` | Example period: e.g. `Dec24-Jan25 - Sales orders.csv`, `Dec24-Jan25 - Sales orders detail.csv` (detail is an additional order-level extract when Finance sends it). |
| `June2024/csv/` | Example period: e.g. `Jun24 - Sales orders.csv`, `Jun24 - Sales orders detail.csv`. |
| `July2025/csv/` | **Reference month — completed end-to-end** (see below). |

Naming conventions (`Dec24-Jan25` vs `Jun24` vs `July 2025 - USA`) follow **whatever Finance names the files** for that month; the **roles** above stay the same.

## July 2025 — reference workflow (done correctly)

The **`July2025/csv/`** folder is the canonical example for how source files line up and what the final outputs look like.

**Inputs (same roles as the table above):**

- `July 2025 - USA.csv` — original monthly billing file.
- `July 2025 - USA - Sales Orders.csv` — sales orders bridge for the month.
- Customer master: **`../July 2025 - USA - Customers.csv`** (one level up, at `files_from_finance` root).

**More detail:** see [`July2025/csv/README.md`](July2025/csv/README.md) for file-to-field mapping and join order.

**Join / audit notes:** see [`July2025/csv/BILLING_AUDIT_JOIN_NOTES.md`](July2025/csv/BILLING_AUDIT_JOIN_NOTES.md) for exact join keys, intermediate outputs, and unmatched-row follow-up.

## Final file sent for QA

The file delivered to Ahmad for QA on the July 2025 run:

- **`July2025/csv/July 2025 - USA - Billing With Customers.csv`**

That file is the **billing lines enriched with customer code and customer name** (and related ship-to fields as produced in that run), suitable for client-level review and audit.

An intermediate output from the same pipeline (sales orders + customer names only) may also exist, e.g. `July 2025 - USA - Sales Orders - With Customers.csv` — see the join notes above.

**QA comparison workbook (Ahmad):** For the July 2025 Port of Long Beach review, Ahmad built an Excel workbook to **compare versions and surface differences** (side-by-side / diff-style analysis). It lives next to the July CSVs, not inside `csv/`:

- [`July2025/Port of Long Beach - KHQ Billing - Comparison July 2025.xlsx`](July2025/Port%20of%20Long%20Beach%20-%20KHQ%20Billing%20-%20Comparison%20July%202025.xlsx)

Use that file when you need to see **what changed** between billing sources or QA passes for that client and month.

## Starting a new month

1. Save the new **billing** and **sales orders** CSVs into a new period folder (or alongside prior months, consistent with your process).
2. Reuse or refresh **`July 2025 - USA - Customers.csv`** (or equivalent customer master) from Finance.
3. If your query or reference tables assume **IX1** (NYC) ItemIDs, normalize **IX2 / IX3 / IX6** (etc.) to **IX1** as described in **ItemID prefixes: iDoxs vs DocWeb** (earlier in this file).
4. Repeat the same joins as documented under `July2025/csv/`, then produce a new **`… Billing With Customers.csv`** for QA.

If Finance changes column names or adds files (e.g. “sales orders detail”), confirm which file is the **order → customer code** bridge before joining.
