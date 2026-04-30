# CheckFree & Metavante — Billing analysis

**Source file:** `prod_files/BillingCollector_i-doxsBilling_202601.csv`  
**Column definitions:** `column-headers.md`

---

## Column mapping

| Product | Primary metric column | Related payment columns |
|--------|------------------------|-------------------------|
| **CheckFree** | `IX1401` | `IX1208`, `IX1708`, `IX1758` (CheckFree_Payments) |
| **Metavante** | `IX1403` | `IX1209`, `IX1709`, `IX1759` (Metavante_Payments) |

---

## CheckFree (`IX1401` > 0)

**Client count: 52**

| Account | IX1401 value |
|---------|--------------|
| AnaheimPUC | 2542 |
| Anchorage | 549 |
| Ashland | 512 |
| AuburnPlacer | 5896 |
| BangorHydro | 3197 |
| Casella | 2529 |
| CentralHudson | 2546 |
| CityOfCharlotte | 23171 |
| CityOfFortCollins | 2376 |
| CityOfOklahoma | 3446 |
| CityofRichmondDPU | 14046 |
| CityOfSacramento | 9758 |
| cmpco | 15826 |
| cng | 7106 |
| CommerceInsurance | 79 |
| CPP | 902 |
| CWATER | 24736 |
| Dakota | 4974 |
| DelNorte | 150 |
| DukeEnergyCorporation | 120534 |
| DukeEnergyPiedmont | 54140 |
| EMWD | 5363 |
| Eureka | 588 |
| Eversource | 97430 |
| Florida | 6824 |
| GoldenGate | 979 |
| IdahoPower | 1 |
| Jackson | 141 |
| JEA | 3075 |
| LakelandElectric | 4359 |
| LibertyMutual | 822 |
| LosAltos | 44 |
| MidContinent | 6986 |
| nyseg | 10619 |
| PGWorks | 17021 |
| rge | 4153 |
| Riverside | 1899 |
| Roanoke | 3479 |
| ROTC | 366 |
| SanMateoCounty | 4172 |
| scg | 6966 |
| SFPUC | 14499 |
| SMUD | 39518 |
| snopud | 20189 |
| SouthValley | 2192 |
| StevensCreek | 13 |
| SunsetScavenger | 3602 |
| UINet | 9716 |
| Unisource | 27802 |
| Unitil | 10996 |
| WasteConnections | 33694 |
| WaterOne | 8248 |

---

## Metavante (`IX1403` > 0)

**Client count: 35**

| Account | IX1403 value |
|---------|---------------|
| AnaheimPUC | 2 |
| Anchorage | 60 |
| Ashland | 1 |
| AuburnPlacer | 96 |
| Casella | 304 |
| CentralHudson | 849 |
| CityOfCharlotte | 649 |
| CityOfFortCollins | 268 |
| CityOfOklahoma | 189 |
| CityOfSacramento | 25 |
| cmpco | 813 |
| CommerceInsurance | 2 |
| CPP | 153 |
| Dakota | 13 |
| DukeEnergyCorporation | 4667 |
| EMWD | 102 |
| Eureka | 17 |
| GoldenGate | 3 |
| IPLPower | 370 |
| LibertyMutual | 82 |
| MariposaCounty | 1 |
| MidContinent | 619 |
| nyseg | 1675 |
| PGE | 2930 |
| rge | 2910 |
| Riverside | 23 |
| Roanoke | 73 |
| SanMateoCounty | 31 |
| SantaRosaCounty | 11 |
| SouthJerseyGas | 315 |
| SouthValley | 21 |
| SunsetScavenger | 40 |
| UINet | 310 |
| WaterOne | 482 |
| WesternOregon | 47 |

---

## Payment-volume columns (supplementary)

Clients where the **sum** of payment columns is greater than zero can differ from the primary flag columns.

### CheckFree_Payments (`IX1208` + `IX1708` + `IX1758` > 0)

**Count: 24**

| Account | Sum |
|---------|-----|
| AnaheimPUC | 9402 |
| Anchorage | 4932 |
| Casella | 22500 |
| CentralHudson | 26898 |
| CityOfFortCollins | 13407 |
| CityOfOklahoma | 26622 |
| cng | 50019 |
| CPP | 9561 |
| CWATER | 129861 |
| Florida | 38448 |
| LakelandElectric | 29286 |
| LUBBOCK | 4272 |
| MidContinent | 33555 |
| nyseg | 79614 |
| Riverside | 19470 |
| Roanoke | 19914 |
| SAntonio | 690 |
| scg | 47547 |
| snopud | 88173 |
| TEP | 28551 |
| UESElectric | 5448 |
| UESGAS | 4602 |
| UINet | 90837 |
| Unitil | 34209 |

### Metavante_Payments (`IX1209` + `IX1709` + `IX1759` > 0)

**Count: 24**

| Account | Sum |
|---------|-----|
| AnaheimPUC | 63 |
| Anchorage | 1182 |
| Casella | 4371 |
| CentralHudson | 23211 |
| CityOfFortCollins | 1482 |
| CityOfOklahoma | 7704 |
| ClevelandWater | 25533 |
| CPP | 54 |
| Dakota | 501 |
| Epcor | 3864 |
| Florida | 2622 |
| IPLPower | 6987 |
| LakelandElectric | 9750 |
| LUBBOCK | 291 |
| MidContinent | 114 |
| MSD | 258 |
| nyseg | 1722 |
| Riverside | 924 |
| Roanoke | 1461 |
| snopud | 144 |
| UINet | 36132 |
| Unitil | 2034 |
| UPPCO | 627 |
| VERTEXLEECOUNTY | 339 |

**Note:** Some accounts show payment activity without a matching nonzero primary flag in this extract (e.g. ClevelandWater with Metavante payment sum but `IX1403` = 0). Treat payment sums as an additional signal, not a replacement for `IX1401` / `IX1403` unless your billing process defines otherwise.

---

## Method

- Parsed CSV rows; `Account` = client name.
- Numeric cells parsed as integers; blank or invalid treated as 0.
- “Uses” for main sections: primary columns `IX1401` / `IX1403` strictly greater than zero.
