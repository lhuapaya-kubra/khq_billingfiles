# July 2025 Billing File Map

This folder contains the 3 source files needed to map billing rows to customer names for July 2025.

## Relevant Files and Purpose

- `July 2025 - USA.csv`
  - **Role:** Original billing file (monthly source from Francis).
  - **Changes:** Replaced each month.
  - **Key field:** `Order No`
  - **What it entails:** Line-level billing details (part, description, quantity, price, dates, etc.).

- `July 2025 - USA - Sales Orders.csv`
  - **Role:** Sales orders bridge file for the month.
  - **Changes:** Replaced each month.
  - **Key fields:** `Order  #`, `Customer Code`
  - **What it entails:** Links each order number to a customer code.

- `July 2025 - USA - Customers.csv`
  - **Role:** Customer master file.
  - **Changes:** Mostly static; refresh only when new customers are added or names change.
  - **Key fields:** `Code`, `Customer Name`
  - **What it entails:** Lookup table that converts customer code to customer name.

## File-to-Role Mapping

- `July 2025 - USA.csv` -> Original billing file
- `July 2025 - USA - Sales Orders.csv` -> Sales orders file
- `July 2025 - USA - Customers.csv` -> Customer master file

## How They Fit Together

1. Join `July 2025 - USA.csv` to `July 2025 - USA - Sales Orders.csv`
   - Match `Order No` = `Order  #`
2. From that result, join to `July 2025 - USA - Customers.csv`
   - Match `Customer Code` = `Code`
3. Pull `Customer Name` into the final billing output.

## Join Flow (Simple)

`Original Billing (Order No)` -> `Sales Orders (Order  #, Customer Code)` -> `Customer Master (Code, Customer Name)`

