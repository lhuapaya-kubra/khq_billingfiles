# i-doxs billing review — findings (202601–202603)

**Sources:** `BillingCollector_i-doxsBilling_202601.csv`, `BillingCollector_i-doxsBilling_202602.csv`, `BillingCollector_i-doxsBilling_202603.csv` in this folder.

**Method:** Rows are keyed by the `Account` field (idoxs tenant code). “Active billing codes” here means any non-zero value in the metric columns (`IX####`, catalog fields, etc.) after `Account` and `Server`.

## Client mapping

| Organization              | `Account` in export |
| ------------------------- | ------------------- |
| City of Scottsdale        | `Scottsdale`        |
| City of Stamford          | `Stamford`          |
| Port of Long Beach        | `PortOfLongBeach`   |
| Lorain (City of Lorain)   | `LCPH`              |

Note: There is also a separate `LongBeach` account row in these files (distinct from `PortOfLongBeach`).

## Summary

| Client / account      | Any billing codes > 0? (all three files) |
| --------------------- | ------------------------------------------ |
| `Scottsdale`          | **No** — all zeros                         |
| `Stamford`            | **No** — all zeros                         |
| `PortOfLongBeach`     | **No** — all zeros                         |
| `LongBeach`           | **No** — all zeros                         |
| `LCPH` (Lorain)       | **No** — all zeros                         |

## Conclusion

Across January–March 2026 billing collector exports reviewed here, **none** of the organizations above show measurable billing activity: every numeric billing column is **0** for each matched `Account` in **202601**, **202602**, and **202603**.

Filenames (`202601`, `202602`, `202603`) reflect the export period or run identifiers used by the collector; conclusions are consistent across all three.
