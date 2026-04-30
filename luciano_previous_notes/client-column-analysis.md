# Client Column Usage Analysis

Analysis of which billing columns have non-zero values for each client in the prod CSV files.
Data sources: `BillingCollector_i-doxsBilling_202512.csv` (Dec 2025) and `BillingCollector_i-doxsBilling_202601.csv` (Jan 2026).
Display names reference: `column-headers.md`.

> **Note:** "Region of Peel" was not found in either prod file.
BDS = Biller Direct Site

---

## 1. CARMA - US Billing Services

**Account code:** `CARMAUS` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |       7,248 |       7,196 | (pages loaded into KHQ -jobs)
| IX1102     | Documents                 |      38,000 |     113,834 | (pages loaded into KHQ)
| IX1103     | Views                     |         644 |         631 | (Billable Views)
| IX1201     | Payments                  |       1,086 |         903 |
| IX1202     | BDSPayments               |         892 |         759 | (all MyHQ+ consumer payments.) - steve question.
| IX1204     | IVRPayments               |          27 |          17 | (EZ-PAY+ IVR+ payments - notes, some clients are on entreprise IVR, but the goal is to move everyone from EZ-PAY IVR v5.1 and enterprise IVR to IVR+)
need to figure out which clients are on which IVR instance: EZ-PAY IVR v5.1 vs enterprise.


| IX1205     | ONEPayments               |         167 |         127 | (EZ-PAY+, web)
| IX1217     | Payment_IVR_ACH_ECP       |           2 |           3 |
| IX1219     | Payment_IVR_CC_DISC       |           1 |          -- |
| IX1220     | Payment_IVR_CC_MC         |           7 |           4 |
| IX1221     | Payment_IVR_CC_VISA       |           8 |           7 |
| IX1225     | Payment_IVR_PD_MC         |           2 |          -- |
| IX1226     | Payment_IVR_PD_VISA       |           7 |           3 |
| IX1237     | Payment_ONE_ACH_ECP       |          26 |          19 |
| IX1239     | Payment_ONE_CC_DISC       |           1 |           2 |
| IX1240     | Payment_ONE_CC_MC         |          37 |          32 |
| IX1241     | Payment_ONE_CC_VISA       |          77 |          53 |
| IX1244     | Payment_ONE_PD_DISC       |           1 |          -- |
| IX1245     | Payment_ONE_PD_MC         |           2 |           2 |
| IX1246     | Payment_ONE_PD_VISA       |          23 |          19 |
| IX1250     | Conv_Fee_Payments         |         166 |         142 |
| IX1267     | Payment_VBS_ACH_ECP       |         892 |         759 |
| IX1302     | BDSReturned               |           7 |           2 |
| IX1305     | ONEReturned               |           1 |          -- |
| IX1501     | SecureEmails              |         155 |         158 | (we dont support, 0.) (new document notification.)
| IX1502     | SecureEmail_Pdf_Pages     |         330 |         336 | (we dont support, 0)
| IX1600     | SMS_Notifications         |         138 |         122 | (todd - chat with todd)
| IX1700     | TotalRemit                |       1,086 |         903 |

---

## 2. CARMA

**Account code:** `CARMA` (CAN)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     243,695 |     234,938 |
| IX1102     | Documents                 |   9,267,260 |   8,791,168 |
| IX1103     | Views                     |      22,603 |      25,590 |
| IX1201     | Payments                  |      32,659 |      29,372 |
| IX1202     | BDSPayments               |      24,021 |      21,551 |
| IX1203     | CSRPayments               |         258 |         275 |
| IX1204     | IVRPayments               |         432 |         413 |
| IX1205     | ONEPayments               |       7,948 |       7,133 |
| IX1217     | Payment_IVR_ACH_ECP       |           8 |           9 |
| IX1220     | Payment_IVR_CC_MC         |         100 |          92 |
| IX1221     | Payment_IVR_CC_VISA       |         208 |         188 |
| IX1225     | Payment_IVR_PD_MC         |          13 |          17 |
| IX1226     | Payment_IVR_PD_VISA       |         103 |         106 |
| IX1237     | Payment_ONE_ACH_ECP       |         452 |         377 |
| IX1239     | Payment_ONE_CC_DISC       |           2 |           1 |
| IX1240     | Payment_ONE_CC_MC         |       1,751 |       1,544 |
| IX1241     | Payment_ONE_CC_VISA       |       3,568 |       3,438 |
| IX1245     | Payment_ONE_PD_MC         |         191 |         163 |
| IX1246     | Payment_ONE_PD_VISA       |       1,858 |       1,604 |
| IX1250     | Conv_Fee_Payments         |       7,239 |       6,743 |
| IX1267     | Payment_VBS_ACH_ECP       |      24,021 |      21,551 |
| IX1287     | Payment_CSR_ACH_ECP       |          11 |          -- |
| IX1290     | Payment_CSR_CC_MC         |          51 |          53 |
| IX1291     | Payment_CSR_CC_VISA       |         220 |         111 |
| IX1295     | Payment_CSR_PD_MC         |          13 |          11 |
| IX1296     | Payment_CSR_PD_VISA       |          77 |         100 |
| IX1302     | BDSReturned               |         373 |         310 |
| IX1304     | IVRReturned               |           3 |           3 |
| IX1305     | ONEReturned               |          33 |          29 |
| IX1501     | SecureEmails              |       6,062 |       6,085 |
| IX1502     | SecureEmail_Pdf_Pages     |      12,762 |      12,862 |
| IX1600     | SMS_Notifications         |       2,162 |       2,158 |
| IX1700     | TotalRemit                |      32,659 |      29,372 |

---

## 3. Casella Waste Systems

**Account codes:** `Casella` (CAN), `CasellaRCS` (US), `CasellaWaste` (US), `CasellaWSS` (US)

### Casella (CAN)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     210,238 |     259,213 |
| IX1102     | Documents                 |     205,644 |     233,256 |
| IX1103     | Views                     |      19,811 |      25,669 |
| IX1201     | Payments                  |     141,974 |     149,870 |
| IX1202     | BDSPayments               |      64,461 |      67,645 |
| IX1203     | CSRPayments               |      14,229 |      13,721 |
| IX1205     | ONEPayments               |      21,747 |      23,066 |
| IX1207     | EFTPayments               |      41,537 |      45,438 |
| IX1208     | CheckFree_Payments        |       8,028 |       7,500 |
| IX1209     | Metavante_Payments        |       1,529 |       1,457 |
| IX1237     | Payment_ONE_ACH_ECP       |       3,548 |       3,503 |
| IX1238     | Payment_ONE_CC_AMEX       |         484 |         493 |
| IX1239     | Payment_ONE_CC_DISC       |         255 |         277 |
| IX1240     | Payment_ONE_CC_MC         |      10,491 |      11,451 |
| IX1241     | Payment_ONE_CC_VISA       |       6,967 |       7,342 |
| IX1267     | Payment_VBS_ACH_ECP       |      27,935 |      28,262 |
| IX1268     | Payment_VBS_CC_AMEX       |       3,680 |       3,983 |
| IX1269     | Payment_VBS_CC_DISC       |       1,289 |       1,473 |
| IX1270     | Payment_VBS_CC_MC         |       9,946 |      10,454 |
| IX1271     | Payment_VBS_CC_VISA       |      21,611 |      23,473 |
| IX1287     | Payment_CSR_ACH_ECP       |       1,181 |       1,235 |
| IX1288     | Payment_CSR_CC_AMEX       |         615 |         484 |
| IX1289     | Payment_CSR_CC_DISC       |         194 |         256 |
| IX1290     | Payment_CSR_CC_MC         |       5,448 |       5,112 |
| IX1291     | Payment_CSR_CC_VISA       |       6,791 |       6,633 |
| IX1302     | BDSReturned               |         512 |         476 |
| IX1305     | ONEReturned               |         466 |         383 |
| IX1307     | EFTReturned               |         298 |         367 |
| IX1401     | CheckFree                 |       2,314 |       2,529 |
| IX1403     | Metavante                 |         262 |         304 |
| IX1427     | Payment_EFT_ACH_ECP       |      10,649 |      11,336 |
| IX1428     | Payment_EFT_CC_AMEX       |       2,385 |       2,593 |
| IX1429     | Payment_EFT_CC_DISC       |         908 |       1,057 |
| IX1430     | Payment_EFT_CC_MC         |       8,963 |       9,854 |
| IX1431     | Payment_EFT_CC_VISA       |      18,632 |      20,598 |
| IX1700     | TotalRemit                |     141,974 |     149,870 |

### CasellaRCS (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |      27,664 |      26,167 |
| IX1102     | Documents                 |   1,569,160 |   1,568,555 |
| IX1103     | Views                     |       4,393 |       4,511 |
| IX1201     | Payments                  |      16,177 |      15,713 |
| IX1202     | BDSPayments               |      11,237 |      10,784 |
| IX1203     | CSRPayments               |         861 |         807 |
| IX1204     | IVRPayments               |         682 |         730 |
| IX1205     | ONEPayments               |       1,588 |       1,649 |
| IX1207     | EFTPayments               |       1,809 |       1,743 |
| IX1217     | Payment_IVR_ACH_ECP       |         138 |         152 |
| IX1218     | Payment_IVR_CC_AMEX       |          13 |          29 |
| IX1219     | Payment_IVR_CC_DISC       |          26 |          24 |
| IX1220     | Payment_IVR_CC_MC         |         135 |         139 |
| IX1221     | Payment_IVR_CC_VISA       |         370 |         386 |
| IX1237     | Payment_ONE_ACH_ECP       |         430 |         447 |
| IX1238     | Payment_ONE_CC_AMEX       |          77 |          56 |
| IX1239     | Payment_ONE_CC_DISC       |          36 |          39 |
| IX1240     | Payment_ONE_CC_MC         |         237 |         260 |
| IX1241     | Payment_ONE_CC_VISA       |         804 |         843 |
| IX1267     | Payment_VBS_ACH_ECP       |       3,011 |       2,995 |
| IX1268     | Payment_VBS_CC_AMEX       |         772 |         767 |
| IX1269     | Payment_VBS_CC_DISC       |         349 |         312 |
| IX1270     | Payment_VBS_CC_MC         |       1,813 |       1,678 |
| IX1271     | Payment_VBS_CC_VISA       |       5,292 |       5,031 |
| IX1287     | Payment_CSR_ACH_ECP       |          53 |          53 |
| IX1288     | Payment_CSR_CC_AMEX       |          43 |          67 |
| IX1289     | Payment_CSR_CC_DISC       |          21 |          21 |
| IX1290     | Payment_CSR_CC_MC         |         225 |         217 |
| IX1291     | Payment_CSR_CC_VISA       |         519 |         452 |
| IX1302     | BDSReturned               |          35 |          60 |
| IX1304     | IVRReturned               |           2 |           6 |
| IX1305     | ONEReturned               |          12 |          25 |
| IX1307     | EFTReturned               |           5 |          10 |
| IX1427     | Payment_EFT_ACH_ECP       |         366 |         391 |
| IX1428     | Payment_EFT_CC_AMEX       |         156 |         129 |
| IX1429     | Payment_EFT_CC_DISC       |          50 |          45 |
| IX1430     | Payment_EFT_CC_MC         |         299 |         275 |
| IX1431     | Payment_EFT_CC_VISA       |         938 |         903 |
| IX1600     | SMS_Notifications         |       2,220 |       2,164 |
| IX1700     | TotalRemit                |      16,177 |      15,713 |

### CasellaWaste (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |      13,371 |      31,855 |
| IX1102     | Documents                 |   1,357,328 |   1,287,970 |
| IX1103     | Views                     |       1,533 |       2,961 |
| IX1201     | Payments                  |       5,777 |       8,312 |
| IX1202     | BDSPayments               |       2,912 |       4,787 |
| IX1203     | CSRPayments               |       1,036 |         772 |
| IX1204     | IVRPayments               |          96 |         199 |
| IX1205     | ONEPayments               |         839 |       1,395 |
| IX1207     | EFTPayments               |         894 |       1,159 |
| IX1217     | Payment_IVR_ACH_ECP       |          27 |          51 |
| IX1218     | Payment_IVR_CC_AMEX       |          -- |           5 |
| IX1219     | Payment_IVR_CC_DISC       |          -- |           2 |
| IX1220     | Payment_IVR_CC_MC         |          25 |          41 |
| IX1221     | Payment_IVR_CC_VISA       |          44 |         100 |
| IX1237     | Payment_ONE_ACH_ECP       |         168 |         260 |
| IX1238     | Payment_ONE_CC_AMEX       |          28 |          59 |
| IX1239     | Payment_ONE_CC_DISC       |          17 |          24 |
| IX1240     | Payment_ONE_CC_MC         |         249 |         342 |
| IX1241     | Payment_ONE_CC_VISA       |         377 |         710 |
| IX1267     | Payment_VBS_ACH_ECP       |       1,135 |       1,230 |
| IX1268     | Payment_VBS_CC_AMEX       |         145 |         249 |
| IX1269     | Payment_VBS_CC_DISC       |          83 |         158 |
| IX1270     | Payment_VBS_CC_MC         |         553 |         944 |
| IX1271     | Payment_VBS_CC_VISA       |         996 |       2,204 |
| IX1287     | Payment_CSR_ACH_ECP       |          56 |          53 |
| IX1288     | Payment_CSR_CC_AMEX       |          28 |          15 |
| IX1289     | Payment_CSR_CC_DISC       |          20 |          14 |
| IX1290     | Payment_CSR_CC_MC         |         349 |         271 |
| IX1291     | Payment_CSR_CC_VISA       |         583 |         418 |
| IX1302     | BDSReturned               |          25 |          24 |
| IX1305     | ONEReturned               |           5 |           7 |
| IX1307     | EFTReturned               |          10 |          11 |
| IX1427     | Payment_EFT_ACH_ECP       |         216 |         180 |
| IX1428     | Payment_EFT_CC_AMEX       |          36 |          58 |
| IX1429     | Payment_EFT_CC_DISC       |          21 |          27 |
| IX1430     | Payment_EFT_CC_MC         |         238 |         301 |
| IX1431     | Payment_EFT_CC_VISA       |         381 |         592 |
| IX1501     | SecureEmails              |          18 |          24 |
| IX1502     | SecureEmail_Pdf_Pages     |          23 |          39 |
| IX1600     | SMS_Notifications         |         769 |       1,338 |
| IX1700     | TotalRemit                |       5,777 |       8,312 |

### CasellaWSS (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |      12,544 |      12,375 |
| IX1102     | Documents                 |     616,133 |     616,295 |
| IX1103     | Views                     |       1,708 |       1,829 |
| IX1201     | Payments                  |       8,154 |       8,162 |
| IX1202     | BDSPayments               |       5,263 |       5,368 |
| IX1203     | CSRPayments               |         697 |         539 |
| IX1204     | IVRPayments               |         315 |         400 |
| IX1205     | ONEPayments               |         688 |         715 |
| IX1207     | EFTPayments               |       1,191 |       1,140 |
| IX1217     | Payment_IVR_ACH_ECP       |          77 |          99 |
| IX1218     | Payment_IVR_CC_AMEX       |          15 |          15 |
| IX1219     | Payment_IVR_CC_DISC       |           6 |           7 |
| IX1220     | Payment_IVR_CC_MC         |          74 |          84 |
| IX1221     | Payment_IVR_CC_VISA       |         143 |         195 |
| IX1237     | Payment_ONE_ACH_ECP       |         199 |         198 |
| IX1238     | Payment_ONE_CC_AMEX       |          37 |          28 |
| IX1239     | Payment_ONE_CC_DISC       |          15 |           8 |
| IX1240     | Payment_ONE_CC_MC         |         130 |         130 |
| IX1241     | Payment_ONE_CC_VISA       |         307 |         349 |
| IX1267     | Payment_VBS_ACH_ECP       |       1,374 |       1,408 |
| IX1268     | Payment_VBS_CC_AMEX       |         582 |         598 |
| IX1269     | Payment_VBS_CC_DISC       |         125 |         122 |
| IX1270     | Payment_VBS_CC_MC         |         872 |         926 |
| IX1271     | Payment_VBS_CC_VISA       |       2,310 |       2,314 |
| IX1287     | Payment_CSR_ACH_ECP       |          44 |          30 |
| IX1288     | Payment_CSR_CC_AMEX       |          19 |          17 |
| IX1289     | Payment_CSR_CC_DISC       |           7 |           5 |
| IX1290     | Payment_CSR_CC_MC         |         107 |          77 |
| IX1291     | Payment_CSR_CC_VISA       |         520 |         410 |
| IX1302     | BDSReturned               |          32 |          47 |
| IX1304     | IVRReturned               |           1 |           3 |
| IX1305     | ONEReturned               |           8 |          11 |
| IX1307     | EFTReturned               |          10 |           2 |
| IX1427     | Payment_EFT_ACH_ECP       |         189 |         189 |
| IX1428     | Payment_EFT_CC_AMEX       |         114 |         101 |
| IX1429     | Payment_EFT_CC_DISC       |          29 |          26 |
| IX1430     | Payment_EFT_CC_MC         |         238 |         214 |
| IX1431     | Payment_EFT_CC_VISA       |         621 |         610 |
| IX1600     | SMS_Notifications         |         972 |       1,011 |
| IX1700     | TotalRemit                |       8,154 |       8,162 |

---

## 4. City of Anaheim Public Utilities

**Account code:** `AnaheimPUC` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     158,870 |     150,136 |
| IX1102     | Documents                 |   5,883,879 |   5,882,607 |
| IX1103     | Views                     |         110 |         127 |
| IX1201     | Payments                  |      59,951 |      62,568 |
| IX1202     | BDSPayments               |      36,523 |      37,994 |
| IX1204     | IVRPayments               |      10,096 |      10,794 |
| IX1205     | ONEPayments               |      12,863 |      13,290 |
| IX1207     | EFTPayments               |         469 |         490 |
| IX1208     | CheckFree_Payments        |       2,677 |       3,134 |
| IX1209     | Metavante_Payments        |          27 |          21 |
| IX1217     | Payment_IVR_ACH_ECP       |         745 |         780 |
| IX1219     | Payment_IVR_CC_DISC       |         108 |         110 |
| IX1220     | Payment_IVR_CC_MC         |       2,617 |       2,732 |
| IX1221     | Payment_IVR_CC_VISA       |       6,599 |       7,145 |
| IX1237     | Payment_ONE_ACH_ECP       |       3,009 |       3,237 |
| IX1239     | Payment_ONE_CC_DISC       |         146 |         140 |
| IX1240     | Payment_ONE_CC_MC         |       3,231 |       3,473 |
| IX1241     | Payment_ONE_CC_VISA       |       6,456 |       6,417 |
| IX1267     | Payment_VBS_ACH_ECP       |      18,831 |      19,378 |
| IX1269     | Payment_VBS_CC_DISC       |         418 |         441 |
| IX1270     | Payment_VBS_CC_MC         |       4,576 |       4,567 |
| IX1271     | Payment_VBS_CC_VISA       |      12,697 |      13,608 |
| IX1302     | BDSReturned               |         114 |         137 |
| IX1305     | ONEReturned               |          59 |          52 |
| IX1307     | EFTReturned               |           5 |           5 |
| IX1401     | CheckFree                 |       3,198 |       2,542 |
| IX1403     | Metavante                 |           6 |           2 |
| IX1427     | Payment_EFT_ACH_ECP       |         469 |         490 |
| IX1600     | SMS_Notifications         |       6,857 |       7,275 |
| IX1700     | TotalRemit                |      59,951 |      62,568 |

---

## 5. City of Richmond

**Account codes:** `CityOfRichmond` (US), `CityofRichmondDPU` (CAN)

### CityOfRichmond (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     480,814 |     393,100 |
| IX1102     | Documents                 |  14,185,932 |  14,221,111 |
| IX1103     | Views                     |      46,499 |      49,270 |
| IX1201     | Payments                  |      58,121 |      58,388 |
| IX1202     | BDSPayments               |      21,873 |      23,318 |
| IX1203     | CSRPayments               |       1,104 |       1,087 |
| IX1204     | IVRPayments               |       6,578 |       6,276 |
| IX1205     | ONEPayments               |      28,566 |      27,707 |
| IX1217     | Payment_IVR_ACH_ECP       |         724 |         698 |
| IX1219     | Payment_IVR_CC_DISC       |          40 |          42 |
| IX1220     | Payment_IVR_CC_MC         |         903 |         734 |
| IX1221     | Payment_IVR_CC_VISA       |       2,568 |       2,478 |
| IX1224     | Payment_IVR_PD_DISC       |          32 |          38 |
| IX1225     | Payment_IVR_PD_MC         |         781 |         801 |
| IX1226     | Payment_IVR_PD_VISA       |       1,530 |       1,485 |
| IX1237     | Payment_ONE_ACH_ECP       |       6,518 |       6,308 |
| IX1239     | Payment_ONE_CC_DISC       |         619 |         597 |
| IX1240     | Payment_ONE_CC_MC         |       3,444 |       3,462 |
| IX1241     | Payment_ONE_CC_VISA       |      13,157 |      12,690 |
| IX1244     | Payment_ONE_PD_DISC       |         197 |         227 |
| IX1245     | Payment_ONE_PD_MC         |       1,445 |       1,369 |
| IX1246     | Payment_ONE_PD_VISA       |       3,166 |       3,042 |
| IX1267     | Payment_VBS_ACH_ECP       |      21,873 |      23,318 |
| IX1287     | Payment_CSR_ACH_ECP       |          90 |          88 |
| IX1289     | Payment_CSR_CC_DISC       |          13 |           4 |
| IX1290     | Payment_CSR_CC_MC         |         108 |         119 |
| IX1291     | Payment_CSR_CC_VISA       |         444 |         467 |
| IX1294     | Payment_CSR_PD_DISC       |           9 |           6 |
| IX1295     | Payment_CSR_PD_MC         |         157 |         139 |
| IX1296     | Payment_CSR_PD_VISA       |         265 |         257 |
| IX1304     | IVRReturned               |          21 |          15 |
| IX1305     | ONEReturned               |          61 |          42 |
| IX1501     | SecureEmails              |       1,892 |       1,932 |
| IX1502     | SecureEmail_Pdf_Pages     |       6,218 |       5,613 |
| IX1600     | SMS_Notifications         |      10,001 |      10,805 |
| IX1700     | TotalRemit                |      58,121 |      58,388 |

### CityofRichmondDPU (CAN)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     435,561 |     390,135 |
| IX1102     | Documents                 |     195,384 |     194,419 |
| IX1103     | Views                     |       5,291 |       7,563 |
| IX1401     | CheckFree                 |      14,211 |      14,046 |

> CityofRichmondDPU only uses Pages, Documents, Views, and CheckFree. No payments or other features.

---

## 6. Curi

**Account code:** `Curi` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |      15,680 |       7,993 |
| IX1102     | Documents                 |     168,267 |     163,076 |
| IX1103     | Views                     |         323 |         381 |
| IX1201     | Payments                  |       1,681 |       1,622 |
| IX1202     | BDSPayments               |       1,050 |       1,106 |
| IX1204     | IVRPayments               |          14 |          16 |
| IX1205     | ONEPayments               |         617 |         500 |
| IX1217     | Payment_IVR_ACH_ECP       |           5 |           4 |
| IX1218     | Payment_IVR_CC_AMEX       |           1 |           4 |
| IX1220     | Payment_IVR_CC_MC         |           5 |           2 |
| IX1221     | Payment_IVR_CC_VISA       |           3 |           5 |
| IX1226     | Payment_IVR_PD_VISA       |          -- |           1 |
| IX1237     | Payment_ONE_ACH_ECP       |         303 |         210 |
| IX1238     | Payment_ONE_CC_AMEX       |          92 |          69 |
| IX1239     | Payment_ONE_CC_DISC       |           1 |           3 |
| IX1240     | Payment_ONE_CC_MC         |          60 |          58 |
| IX1241     | Payment_ONE_CC_VISA       |         131 |         136 |
| IX1245     | Payment_ONE_PD_MC         |           6 |          12 |
| IX1246     | Payment_ONE_PD_VISA       |          24 |          12 |
| IX1267     | Payment_VBS_ACH_ECP       |         634 |         674 |
| IX1268     | Payment_VBS_CC_AMEX       |         115 |         124 |
| IX1269     | Payment_VBS_CC_DISC       |           3 |           2 |
| IX1270     | Payment_VBS_CC_MC         |          60 |          73 |
| IX1271     | Payment_VBS_CC_VISA       |         217 |         210 |
| IX1275     | Payment_VBS_PD_MC         |           4 |           8 |
| IX1276     | Payment_VBS_PD_VISA       |          17 |          15 |
| IX1302     | BDSReturned               |          16 |          -- |
| IX1305     | ONEReturned               |           2 |           4 |
| IX1501     | SecureEmails              |       2,208 |       1,247 |
| IX1502     | SecureEmail_Pdf_Pages     |      11,916 |       6,454 |
| IX1600     | SMS_Notifications         |         172 |         140 |
| IX1700     | TotalRemit                |       1,681 |       1,622 |

---

## 7. Greater Cincinnati Water Works

**Account codes:** `GCWW` (US), `GCWWSundry` (US)

### GCWW (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     662,229 |     558,362 |
| IX1102     | Documents                 |  22,572,387 |  21,536,047 |
| IX1103     | Views                     |      53,876 |      54,760 |
| IX1201     | Payments                  |     166,033 |     146,040 |
| IX1202     | BDSPayments               |     116,374 |     100,990 |
| IX1204     | IVRPayments               |      22,022 |      20,206 |
| IX1205     | ONEPayments               |      22,819 |      20,712 |
| IX1207     | EFTPayments               |       4,817 |       4,130 |
| IX1212     | SMS_Payments              |           1 |           2 |
| IX1217     | Payment_IVR_ACH_ECP       |       4,378 |       3,925 |
| IX1218     | Payment_IVR_CC_AMEX       |         404 |         347 |
| IX1219     | Payment_IVR_CC_DISC       |         184 |         142 |
| IX1220     | Payment_IVR_CC_MC         |       2,138 |       2,022 |
| IX1221     | Payment_IVR_CC_VISA       |       4,116 |       3,832 |
| IX1224     | Payment_IVR_PD_DISC       |          35 |          20 |
| IX1225     | Payment_IVR_PD_MC         |       4,815 |       4,464 |
| IX1226     | Payment_IVR_PD_VISA       |       5,862 |       5,387 |
| IX1237     | Payment_ONE_ACH_ECP       |       4,346 |       3,837 |
| IX1238     | Payment_ONE_CC_AMEX       |       1,123 |         873 |
| IX1239     | Payment_ONE_CC_DISC       |         390 |         364 |
| IX1240     | Payment_ONE_CC_MC         |       3,583 |       3,187 |
| IX1241     | Payment_ONE_CC_VISA       |       7,127 |       6,730 |
| IX1244     | Payment_ONE_PD_DISC       |          41 |          43 |
| IX1245     | Payment_ONE_PD_MC         |       2,212 |       2,060 |
| IX1246     | Payment_ONE_PD_VISA       |       2,931 |       2,756 |
| IX1250     | Conv_Fee_Payments         |      41,351 |      41,484 |
| IX1267     | Payment_VBS_ACH_ECP       |     116,375 |     100,992 |
| IX1287     | Payment_CSR_ACH_ECP       |          37 |          -- |
| IX1302     | BDSReturned               |         840 |         771 |
| IX1304     | IVRReturned               |          77 |          72 |
| IX1305     | ONEReturned               |          54 |          72 |
| IX1307     | EFTReturned               |          23 |          24 |
| IX1427     | Payment_EFT_ACH_ECP       |       4,817 |       4,130 |
| IX1501     | SecureEmails              |       2,382 |       2,120 |
| IX1502     | SecureEmail_Pdf_Pages     |      11,082 |       9,324 |
| IX1600     | SMS_Notifications         |      13,444 |      13,059 |
| IX1700     | TotalRemit                |     166,033 |     146,040 |

### GCWWSundry (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1102     | Documents                 |      11,423 |       9,781 |
| IX1201     | Payments                  |          32 |          25 |
| IX1205     | ONEPayments               |          32 |          25 |
| IX1237     | Payment_ONE_ACH_ECP       |          27 |          17 |
| IX1238     | Payment_ONE_CC_AMEX       |          -- |           2 |
| IX1241     | Payment_ONE_CC_VISA       |           5 |           6 |
| IX1250     | Conv_Fee_Payments         |           5 |           8 |
| IX1600     | SMS_Notifications         |           4 |          -- |
| IX1700     | TotalRemit                |          32 |          25 |

---

## 8. Lakeland Electric

**Account code:** `LakelandElectric` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     312,880 |     308,558 |
| IX1102     | Documents                 |     157,342 |     155,820 |
| IX1103     | Views                     |      45,758 |      46,282 |
| IX1201     | Payments                  |      97,379 |      87,391 |
| IX1202     | BDSPayments               |      50,593 |      44,624 |
| IX1203     | CSRPayments               |          58 |          76 |
| IX1204     | IVRPayments               |      10,502 |       9,749 |
| IX1205     | ONEPayments               |      36,226 |      32,942 |
| IX1206     | Online_Resources_Payments |       3,193 |       2,877 |
| IX1208     | CheckFree_Payments        |      10,949 |       9,762 |
| IX1209     | Metavante_Payments        |       3,759 |       3,250 |
| IX1217     | Payment_IVR_ACH_ECP       |       1,091 |         971 |
| IX1218     | Payment_IVR_CC_AMEX       |         122 |         102 |
| IX1219     | Payment_IVR_CC_DISC       |          65 |          50 |
| IX1220     | Payment_IVR_CC_MC         |         540 |         731 |
| IX1221     | Payment_IVR_CC_VISA       |       3,734 |       3,335 |
| IX1224     | Payment_IVR_PD_DISC       |          22 |          36 |
| IX1225     | Payment_IVR_PD_MC         |       1,175 |       1,034 |
| IX1226     | Payment_IVR_PD_VISA       |       3,753 |       3,490 |
| IX1237     | Payment_ONE_ACH_ECP       |       3,304 |       3,198 |
| IX1238     | Payment_ONE_CC_AMEX       |         702 |         616 |
| IX1239     | Payment_ONE_CC_DISC       |         334 |         322 |
| IX1240     | Payment_ONE_CC_MC         |       4,059 |       3,399 |
| IX1241     | Payment_ONE_CC_VISA       |      16,217 |      14,786 |
| IX1244     | Payment_ONE_PD_DISC       |         151 |         141 |
| IX1245     | Payment_ONE_PD_MC         |       2,320 |       2,065 |
| IX1246     | Payment_ONE_PD_VISA       |       7,636 |       7,001 |
| IX1250     | Conv_Fee_Payments         |      41,538 |      39,821 |
| IX1267     | Payment_VBS_ACH_ECP       |      50,593 |      44,624 |
| IX1287     | Payment_CSR_ACH_ECP       |           3 |           2 |
| IX1288     | Payment_CSR_CC_AMEX       |          -- |           2 |
| IX1289     | Payment_CSR_CC_DISC       |           1 |           3 |
| IX1290     | Payment_CSR_CC_MC         |           4 |          12 |
| IX1291     | Payment_CSR_CC_VISA       |          33 |          28 |
| IX1294     | Payment_CSR_PD_DISC       |          -- |           1 |
| IX1295     | Payment_CSR_PD_MC         |           4 |           4 |
| IX1296     | Payment_CSR_PD_VISA       |          12 |          24 |
| IX1302     | BDSReturned               |         596 |         596 |
| IX1304     | IVRReturned               |         100 |          78 |
| IX1305     | ONEReturned               |         254 |         233 |
| IX1401     | CheckFree                 |       4,443 |       4,359 |
| IX1501     | SecureEmails              |       3,212 |       3,116 |
| IX1502     | SecureEmail_Pdf_Pages     |       7,413 |       7,243 |
| IX1600     | SMS_Notifications         |      70,676 |      69,201 |
| IX1700     | TotalRemit                |      97,379 |      87,391 |

---

## 9. Midwest Energy

**Account code:** `MidWest` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |     147,842 |     130,106 |
| IX1102     | Documents                 |   2,499,997 |   2,603,463 |
| IX1103     | Views                     |      12,510 |      12,127 |
| IX1201     | Payments                  |      23,337 |      20,000 |
| IX1202     | BDSPayments               |      18,378 |      15,235 |
| IX1203     | CSRPayments               |         492 |         495 |
| IX1204     | IVRPayments               |       1,506 |       1,425 |
| IX1205     | ONEPayments               |       2,961 |       2,845 |
| IX1219     | Payment_IVR_CC_DISC       |           8 |           8 |
| IX1220     | Payment_IVR_CC_MC         |          71 |          79 |
| IX1221     | Payment_IVR_CC_VISA       |         153 |         157 |
| IX1224     | Payment_IVR_PD_DISC       |           4 |           3 |
| IX1225     | Payment_IVR_PD_MC         |         470 |         440 |
| IX1226     | Payment_IVR_PD_VISA       |         800 |         738 |
| IX1239     | Payment_ONE_CC_DISC       |          39 |          31 |
| IX1240     | Payment_ONE_CC_MC         |         544 |         540 |
| IX1241     | Payment_ONE_CC_VISA       |         698 |         663 |
| IX1244     | Payment_ONE_PD_DISC       |           5 |          11 |
| IX1245     | Payment_ONE_PD_MC         |         582 |         523 |
| IX1246     | Payment_ONE_PD_VISA       |         942 |         940 |
| IX1250     | Conv_Fee_Payments         |       4,659 |       4,652 |
| IX1267     | Payment_VBS_ACH_ECP       |      18,378 |      15,235 |
| IX1289     | Payment_CSR_CC_DISC       |           8 |           5 |
| IX1290     | Payment_CSR_CC_MC         |          36 |          37 |
| IX1291     | Payment_CSR_CC_VISA       |          55 |          70 |
| IX1294     | Payment_CSR_PD_DISC       |           4 |           2 |
| IX1295     | Payment_CSR_PD_MC         |         161 |         164 |
| IX1296     | Payment_CSR_PD_VISA       |         227 |         217 |
| IX1302     | BDSReturned               |         128 |         132 |
| IX1304     | IVRReturned               |           1 |          -- |
| IX1305     | ONEReturned               |           1 |          -- |
| IX1600     | SMS_Notifications         |       1,566 |       1,656 |
| IX1700     | TotalRemit                |      23,337 |      20,000 |

---

## 10. Xcel Energy

**Account code:** `XcelEnergy` (US)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1102     | Documents                 |   7,921,548 |   7,780,093 |
| IX1201     | Payments                  |     413,387 |     404,391 |
| IX1204     | IVRPayments               |     100,368 |      98,042 |
| IX1205     | ONEPayments               |     313,019 |     306,349 |
| IX1218     | Payment_IVR_CC_AMEX       |       1,302 |       1,269 |
| IX1219     | Payment_IVR_CC_DISC       |         787 |         743 |
| IX1220     | Payment_IVR_CC_MC         |       8,161 |       8,271 |
| IX1221     | Payment_IVR_CC_VISA       |      37,142 |      36,395 |
| IX1224     | Payment_IVR_PD_DISC       |         278 |         342 |
| IX1225     | Payment_IVR_PD_MC         |      17,633 |      17,240 |
| IX1226     | Payment_IVR_PD_VISA       |      35,065 |      33,782 |
| IX1238     | Payment_ONE_CC_AMEX       |       8,634 |       8,184 |
| IX1239     | Payment_ONE_CC_DISC       |       6,325 |       5,819 |
| IX1240     | Payment_ONE_CC_MC         |      37,017 |      36,942 |
| IX1241     | Payment_ONE_CC_VISA       |     102,681 |     115,274 |
| IX1244     | Payment_ONE_PD_DISC       |       1,189 |       1,311 |
| IX1245     | Payment_ONE_PD_MC         |      20,102 |      16,090 |
| IX1246     | Payment_ONE_PD_VISA       |      22,877 |      32,927 |
| IX1250     | Conv_Fee_Payments         |     247,522 |     257,492 |
| IX1288     | Payment_CSR_CC_AMEX       |         691 |       1,308 |
| IX1289     | Payment_CSR_CC_DISC       |          58 |         452 |
| IX1290     | Payment_CSR_CC_MC         |       8,885 |       7,358 |
| IX1291     | Payment_CSR_CC_VISA       |      59,293 |      43,951 |
| IX1294     | Payment_CSR_PD_DISC       |           9 |          39 |
| IX1295     | Payment_CSR_PD_MC         |       7,335 |      10,784 |
| IX1296     | Payment_CSR_PD_VISA       |      37,471 |      25,452 |
| IX1304     | IVRReturned               |         120 |         135 |
| IX1305     | ONEReturned               |         511 |         612 |
| IX1600     | SMS_Notifications         |     135,694 |     142,295 |
| IX1700     | TotalRemit                |     413,387 |     404,391 |

> Xcel Energy has no Pages (IX1101) or Views (IX1103) -- documents only. No BDS or EFT payments. Very high IVR and ONE payment volumes.

---

## 11. City of Waterloo

**Account code:** `CityofWaterloo` (CAN)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |      27,730 |     149,618 |
| IX1102     | Documents                 |      13,864 |      74,749 |
| IX1103     | Views                     |       3,285 |       6,976 |
| IX1201     | Payments                  |       3,014 |       2,887 |
| IX1202     | BDSPayments               |       2,969 |       2,831 |
| IX1205     | ONEPayments               |          45 |          56 |
| IX1237     | Payment_ONE_ACH_ECP       |          19 |          25 |
| IX1240     | Payment_ONE_CC_MC         |           7 |           8 |
| IX1241     | Payment_ONE_CC_VISA       |          15 |          19 |
| IX1246     | Payment_ONE_PD_VISA       |           4 |           4 |
| IX1250     | Conv_Fee_Payments         |       1,029 |       1,017 |
| IX1267     | Payment_VBS_ACH_ECP       |       1,880 |       1,788 |
| IX1270     | Payment_VBS_CC_MC         |         357 |         301 |
| IX1271     | Payment_VBS_CC_VISA       |         568 |         597 |
| IX1275     | Payment_VBS_PD_MC         |          24 |          15 |
| IX1276     | Payment_VBS_PD_VISA       |         140 |         129 |
| IX1302     | BDSReturned               |           8 |          10 |
| IX1305     | ONEReturned               |          -- |           1 |
| IX1600     | SMS_Notifications         |          60 |         122 |
| IX1700     | TotalRemit                |       3,014 |       2,887 |

---

## 12. Metergy Solutions

**Account code:** `MetergySolutions` (CAN)

| Column Key | Display Name              |    Dec 2025 |    Jan 2026 |
|:-----------|:--------------------------|------------:|------------:|
| IX1101     | Pages                     |   1,189,061 |   1,229,473 |
| IX1102     | Documents                 |     350,681 |     391,275 |
| IX1103     | Views                     |      59,435 |      72,486 |
| IX1201     | Payments                  |     144,079 |     138,351 |
| IX1202     | BDSPayments               |     140,192 |     134,244 |
| IX1204     | IVRPayments               |         826 |         908 |
| IX1205     | ONEPayments               |       3,061 |       3,199 |
| IX1217     | Payment_IVR_ACH_ECP       |          20 |          20 |
| IX1220     | Payment_IVR_CC_MC         |         161 |         175 |
| IX1221     | Payment_IVR_CC_VISA       |         321 |         363 |
| IX1225     | Payment_IVR_PD_MC         |          26 |          35 |
| IX1226     | Payment_IVR_PD_VISA       |         287 |         311 |
| IX1237     | Payment_ONE_ACH_ECP       |         205 |         235 |
| IX1240     | Payment_ONE_CC_MC         |         527 |         566 |
| IX1241     | Payment_ONE_CC_VISA       |       1,155 |       1,213 |
| IX1245     | Payment_ONE_PD_MC         |         107 |         117 |
| IX1246     | Payment_ONE_PD_VISA       |       1,060 |       1,058 |
| IX1250     | Conv_Fee_Payments         |      40,477 |      42,497 |
| IX1267     | Payment_VBS_ACH_ECP       |      98,644 |      92,883 |
| IX1270     | Payment_VBS_CC_MC         |       9,081 |       8,959 |
| IX1271     | Payment_VBS_CC_VISA       |      20,366 |      20,162 |
| IX1275     | Payment_VBS_PD_MC         |       1,005 |       1,030 |
| IX1276     | Payment_VBS_PD_VISA       |      11,084 |      11,185 |
| IX1302     | BDSReturned               |       1,300 |       1,334 |
| IX1304     | IVRReturned               |           4 |           4 |
| IX1305     | ONEReturned               |          13 |          22 |
| IX1600     | SMS_Notifications         |       1,522 |       1,841 |
| IX1700     | TotalRemit                |     144,079 |     138,351 |

---

## 13. Region of Peel

**Not found in prod data.** No account matching "Region of Peel" exists in either prod CSV file.

---

## Summary: Feature Usage by Client

Shows which features each client uses (non-zero values in at least one month). "--" means no activity.

### Core Metrics

| Client                          | Pages | Docs  | Views |
|:--------------------------------|:-----:|:-----:|:-----:|
| CARMA - US Billing Services     |  Yes  |  Yes  |  Yes  |
| CARMA                           |  Yes  |  Yes  |  Yes  |
| Casella (CAN)                   |  Yes  |  Yes  |  Yes  |
| CasellaRCS (US)                 |  Yes  |  Yes  |  Yes  |
| CasellaWaste (US)               |  Yes  |  Yes  |  Yes  |
| CasellaWSS (US)                 |  Yes  |  Yes  |  Yes  |
| City of Anaheim                 |  Yes  |  Yes  |  Yes  |
| City of Richmond (US)           |  Yes  |  Yes  |  Yes  |
| CityofRichmondDPU (CAN)         |  Yes  |  Yes  |  Yes  |
| Curi                            |  Yes  |  Yes  |  Yes  |
| GCWW                            |  Yes  |  Yes  |  Yes  |
| GCWWSundry                      |  --   |  Yes  |  --   |
| Lakeland Electric               |  Yes  |  Yes  |  Yes  |
| Midwest Energy                  |  Yes  |  Yes  |  Yes  |
| Xcel Energy                     |  --   |  Yes  |  --   |
| City of Waterloo                |  Yes  |  Yes  |  Yes  |
| Metergy Solutions               |  Yes  |  Yes  |  Yes  |
| Region of Peel                  |  --   |  --   |  --   |

### Payment Channels

| Client                          | BDS | CSR | IVR | ONE | EFT | OnlRes | ChkFree | Metav | SMS | RPPS | Ext |
|:--------------------------------|:---:|:---:|:---:|:---:|:---:|:------:|:-------:|:-----:|:---:|:----:|:---:|
| CARMA - US Billing              | Yes | --  | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| CARMA                           | Yes | Yes | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| Casella (CAN)                   | Yes | Yes | --  | Yes | Yes |   --   |  Yes    | Yes   | --  |  --  | --  |
| CasellaRCS (US)                 | Yes | Yes | Yes | Yes | Yes |   --   |   --    |  --   | --  |  --  | --  |
| CasellaWaste (US)               | Yes | Yes | Yes | Yes | Yes |   --   |   --    |  --   | --  |  --  | --  |
| CasellaWSS (US)                 | Yes | Yes | Yes | Yes | Yes |   --   |   --    |  --   | --  |  --  | --  |
| City of Anaheim                 | Yes | --  | Yes | Yes | Yes |   --   |  Yes    | Yes   | --  |  --  | --  |
| City of Richmond (US)           | Yes | Yes | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| CityofRichmondDPU (CAN)         | --  | --  | --  | --  | --  |   --   |   --    |  --   | --  |  --  | --  |
| Curi                            | Yes | --  | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| GCWW                            | Yes | --  | Yes | Yes | Yes |   --   |   --    |  --   | Yes |  --  | --  |
| GCWWSundry                      | --  | --  | --  | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| Lakeland Electric               | Yes | Yes | Yes | Yes | --  |  Yes   |  Yes    | Yes   | --  |  --  | --  |
| Midwest Energy                  | Yes | Yes | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| Xcel Energy                     | --  | --  | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| City of Waterloo                | Yes | --  | --  | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| Metergy Solutions               | Yes | --  | Yes | Yes | --  |   --   |   --    |  --   | --  |  --  | --  |
| Region of Peel                  | --  | --  | --  | --  | --  |   --   |   --    |  --   | --  |  --  | --  |

### Payment Detail Breakdown (by method)

| Client                          | IVR Detail | ONE Detail | VBS Detail | CSR Detail | EFT Detail |
|:--------------------------------|:----------:|:----------:|:----------:|:----------:|:----------:|
| CARMA - US Billing              |    Yes     |    Yes     |    Yes     |     --     |     --     |
| CARMA                           |    Yes     |    Yes     |    Yes     |    Yes     |     --     |
| Casella (CAN)                   |     --     |    Yes     |    Yes     |    Yes     |    Yes     |
| CasellaRCS (US)                 |    Yes     |    Yes     |    Yes     |    Yes     |    Yes     |
| CasellaWaste (US)               |    Yes     |    Yes     |    Yes     |    Yes     |    Yes     |
| CasellaWSS (US)                 |    Yes     |    Yes     |    Yes     |    Yes     |    Yes     |
| City of Anaheim                 |    Yes     |    Yes     |    Yes     |     --     |    Yes     |
| City of Richmond (US)           |    Yes     |    Yes     |    Yes     |    Yes     |     --     |
| CityofRichmondDPU (CAN)         |     --     |     --     |     --     |     --     |     --     |
| Curi                            |    Yes     |    Yes     |    Yes     |     --     |     --     |
| GCWW                            |    Yes     |    Yes     |    Yes     |    Yes     |    Yes     |
| GCWWSundry                      |     --     |    Yes     |     --     |     --     |     --     |
| Lakeland Electric               |    Yes     |    Yes     |    Yes     |    Yes     |     --     |
| Midwest Energy                  |    Yes     |    Yes     |    Yes     |    Yes     |     --     |
| Xcel Energy                     |    Yes     |    Yes     |     --     |    Yes     |     --     |
| City of Waterloo                |     --     |    Yes     |    Yes     |     --     |     --     |
| Metergy Solutions               |    Yes     |    Yes     |    Yes     |     --     |     --     |
| Region of Peel                  |     --     |     --     |     --     |     --     |     --     |

### Returns, Communications, and Other

| Client                          | Returns            | Third Party          | SecEmail | SMS Notif | Conv Fee | Remit |
|:--------------------------------|:-------------------|:---------------------|:--------:|:---------:|:--------:|:-----:|
| CARMA - US Billing              | BDS, ONE           | --                   |   Yes    |    Yes    |   Yes    |  Yes  |
| CARMA                           | BDS, IVR, ONE      | --                   |   Yes    |    Yes    |   Yes    |  Yes  |
| Casella (CAN)                   | BDS, ONE, EFT      | CheckFree, Metavante |    --    |    --     |    --    |  Yes  |
| CasellaRCS (US)                 | BDS, IVR, ONE, EFT | --                   |    --    |    Yes    |    --    |  Yes  |
| CasellaWaste (US)               | BDS, ONE, EFT      | --                   |   Yes    |    Yes    |    --    |  Yes  |
| CasellaWSS (US)                 | BDS, IVR, ONE, EFT | --                   |    --    |    Yes    |    --    |  Yes  |
| City of Anaheim                 | BDS, ONE, EFT      | CheckFree, Metavante |    --    |    Yes    |    --    |  Yes  |
| City of Richmond (US)           | IVR, ONE           | --                   |   Yes    |    Yes    |    --    |  Yes  |
| CityofRichmondDPU (CAN)         | --                 | CheckFree            |    --    |    --     |    --    |  --   |
| Curi                            | BDS, ONE           | --                   |   Yes    |    Yes    |    --    |  Yes  |
| GCWW                            | BDS, IVR, ONE, EFT | --                   |   Yes    |    Yes    |   Yes    |  Yes  |
| GCWWSundry                      | --                 | --                   |    --    |    Yes    |   Yes    |  Yes  |
| Lakeland Electric               | BDS, IVR, ONE      | CheckFree            |   Yes    |    Yes    |   Yes    |  Yes  |
| Midwest Energy                  | BDS, IVR, ONE      | --                   |    --    |    Yes    |   Yes    |  Yes  |
| Xcel Energy                     | IVR, ONE           | --                   |    --    |    Yes    |   Yes    |  Yes  |
| City of Waterloo                | BDS, ONE           | --                   |    --    |    Yes    |   Yes    |  Yes  |
| Metergy Solutions               | BDS, IVR, ONE      | --                   |    --    |    Yes    |   Yes    |  Yes  |
| Region of Peel                  | --                 | --                   |    --    |    --     |    --    |  --   |

---

## Appendix A: Codes Used by These Clients

60 out of 206 billing column keys had non-zero values for at least one client in at least one month.

| #  | Column Key | Display Name              | Used By                                                                                            |
|:---|:-----------|:--------------------------|:---------------------------------------------------------------------------------------------------|
| 1  | IX1101     | Pages                     | All except GCWWSundry, XcelEnergy                                                                  |
| 2  | IX1102     | Documents                 | All accounts                                                                                       |
| 3  | IX1103     | Views                     | All except GCWWSundry, XcelEnergy                                                                  |
| 4  | IX1201     | Payments                  | All except CityofRichmondDPU                                                                       |
| 5  | IX1202     | BDSPayments               | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, Waterloo, Metergy |
| 6  | IX1203     | CSRPayments               | CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Richmond, Lakeland, MidWest                 |
| 7  | IX1204     | IVRPayments               | CARMAUS, CARMA, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Metergy |
| 8  | IX1205     | ONEPayments               | All except CityofRichmondDPU                                                                       |
| 9  | IX1206     | Online_Resources_Payments | Lakeland only                                                                                      |
| 10 | IX1207     | EFTPayments               | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, GCWW                                      |
| 11 | IX1208     | CheckFree_Payments        | Casella, Anaheim, Lakeland                                                                         |
| 12 | IX1209     | Metavante_Payments        | Casella, Anaheim, Lakeland                                                                         |
| 13 | IX1212     | SMS_Payments              | GCWW only                                                                                          |
| 14 | IX1217     | Payment_IVR_ACH_ECP       | CARMAUS, CARMA, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, Metergy |
| 15 | IX1218     | Payment_IVR_CC_AMEX       | CasellaRCS, CasellaWaste, CasellaWSS, Curi, GCWW, Lakeland, XcelEnergy                            |
| 16 | IX1219     | Payment_IVR_CC_DISC       | CARMAUS, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, GCWW, Lakeland, MidWest, XcelEnergy |
| 17 | IX1220     | Payment_IVR_CC_MC         | CARMAUS, CARMA, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Metergy |
| 18 | IX1221     | Payment_IVR_CC_VISA       | CARMAUS, CARMA, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Metergy |
| 19 | IX1224     | Payment_IVR_PD_DISC       | Richmond, GCWW, Lakeland, MidWest, XcelEnergy                                                     |
| 20 | IX1225     | Payment_IVR_PD_MC         | CARMAUS, CARMA, Richmond, GCWW, Lakeland, MidWest, XcelEnergy, Metergy                            |
| 21 | IX1226     | Payment_IVR_PD_VISA       | CARMAUS, CARMA, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Metergy                      |
| 22 | IX1237     | Payment_ONE_ACH_ECP       | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, GCWWSundry, Lakeland, Waterloo, Metergy |
| 23 | IX1238     | Payment_ONE_CC_AMEX       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Curi, GCWW, GCWWSundry, Lakeland, XcelEnergy       |
| 24 | IX1239     | Payment_ONE_CC_DISC       | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy |
| 25 | IX1240     | Payment_ONE_CC_MC         | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Waterloo, Metergy |
| 26 | IX1241     | Payment_ONE_CC_VISA       | All payment accounts                                                                               |
| 27 | IX1244     | Payment_ONE_PD_DISC       | CARMAUS, Richmond, GCWW, Lakeland, MidWest, XcelEnergy                                             |
| 28 | IX1245     | Payment_ONE_PD_MC         | CARMAUS, CARMA, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Metergy                       |
| 29 | IX1246     | Payment_ONE_PD_VISA       | CARMAUS, CARMA, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Waterloo, Metergy             |
| 30 | IX1250     | Conv_Fee_Payments         | CARMAUS, CARMA, Anaheim, GCWW, GCWWSundry, Lakeland, MidWest, XcelEnergy, Waterloo, Metergy        |
| 31 | IX1267     | Payment_VBS_ACH_ECP       | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, Waterloo, Metergy |
| 32 | IX1268     | Payment_VBS_CC_AMEX       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Curi                                               |
| 33 | IX1269     | Payment_VBS_CC_DISC       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Curi                                      |
| 34 | IX1270     | Payment_VBS_CC_MC         | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Curi, Waterloo, Metergy                   |
| 35 | IX1271     | Payment_VBS_CC_VISA       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Curi, Waterloo, Metergy                   |
| 36 | IX1275     | Payment_VBS_PD_MC         | Curi, Waterloo, Metergy                                                                            |
| 37 | IX1276     | Payment_VBS_PD_VISA       | Curi, Waterloo, Metergy                                                                            |
| 38 | IX1287     | Payment_CSR_ACH_ECP       | CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Richmond, GCWW, Lakeland                    |
| 39 | IX1288     | Payment_CSR_CC_AMEX       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Lakeland, XcelEnergy                               |
| 40 | IX1289     | Payment_CSR_CC_DISC       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Richmond, Lakeland, MidWest, XcelEnergy            |
| 41 | IX1290     | Payment_CSR_CC_MC         | CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Richmond, Lakeland, MidWest, XcelEnergy     |
| 42 | IX1291     | Payment_CSR_CC_VISA       | CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Richmond, Lakeland, MidWest, XcelEnergy     |
| 43 | IX1294     | Payment_CSR_PD_DISC       | Richmond, Lakeland, MidWest, XcelEnergy                                                            |
| 44 | IX1295     | Payment_CSR_PD_MC         | CARMA, Richmond, Lakeland, MidWest, XcelEnergy                                                     |
| 45 | IX1296     | Payment_CSR_PD_VISA       | CARMA, Richmond, Lakeland, MidWest, XcelEnergy                                                     |
| 46 | IX1302     | BDSReturned               | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Curi, GCWW, Lakeland, MidWest, Waterloo, Metergy |
| 47 | IX1304     | IVRReturned               | CARMA, CasellaRCS, CasellaWSS, Richmond, GCWW, Lakeland, MidWest, XcelEnergy, Metergy             |
| 48 | IX1305     | ONEReturned               | CARMAUS, CARMA, Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, Richmond, Curi, GCWW, Lakeland, MidWest, XcelEnergy, Waterloo, Metergy |
| 49 | IX1307     | EFTReturned               | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, GCWW                                      |
| 50 | IX1401     | CheckFree                 | Casella, Anaheim, CityofRichmondDPU, Lakeland                                                     |
| 51 | IX1403     | Metavante                 | Casella, Anaheim                                                                                   |
| 52 | IX1427     | Payment_EFT_ACH_ECP       | Casella, CasellaRCS, CasellaWaste, CasellaWSS, Anaheim, GCWW                                      |
| 53 | IX1428     | Payment_EFT_CC_AMEX       | Casella, CasellaRCS, CasellaWaste, CasellaWSS                                                     |
| 54 | IX1429     | Payment_EFT_CC_DISC       | Casella, CasellaRCS, CasellaWaste, CasellaWSS                                                     |
| 55 | IX1430     | Payment_EFT_CC_MC         | Casella, CasellaRCS, CasellaWaste, CasellaWSS                                                     |
| 56 | IX1431     | Payment_EFT_CC_VISA       | Casella, CasellaRCS, CasellaWaste, CasellaWSS                                                     |
| 57 | IX1501     | SecureEmails              | CARMAUS, CARMA, CasellaWaste, Richmond, Curi, GCWW, Lakeland                                      |
| 58 | IX1502     | SecureEmail_Pdf_Pages     | CARMAUS, CARMA, CasellaWaste, Richmond, Curi, GCWW, Lakeland                                      |
| 59 | IX1600     | SMS_Notifications         | All except Casella (CAN), CityofRichmondDPU                                                       |
| 60 | IX1700     | TotalRemit                | All except CityofRichmondDPU                                                                       |

---

## Appendix B: Codes NOT Used by Any Client

146 out of 206 billing column keys had zero values across all clients in both months. Grouped by category.

### Catalog Codes (3)

| Column Key   | Display Name              |
|:-------------|:--------------------------|
| CatalogDocs  | DocsPerCatalog            |
| CatalogPages | PagesPerCatalog           |
| CatalogViews | ViewsPerCatalog           |

### Alternate Document/Page Codes (2)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1104     | Pages                     |
| IX1105     | Documents                 |

### Unused Payment Channel Codes (4)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1210     | RPPS_Payments             |
| IX1211     | External_Payments         |
| IX1213     | Mobile_Payments           |
| IX1214     | Princeton_Payments        |

### Unused IVR Payment Detail Codes (3)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1222     | Payment_IVR_CC_OT         |
| IX1223     | Payment_IVR_PD_AMEX       |
| IX1227     | Payment_IVR_PD_OT         |

### Unused ONE Payment Detail Codes (3)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1242     | Payment_ONE_CC_OT         |
| IX1243     | Payment_ONE_PD_AMEX       |
| IX1247     | Payment_ONE_PD_OT         |

### IVR Outbound (1)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1260     | IVROutbound               |

### Unused VBS Payment Detail Codes (4)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1272     | Payment_VBS_CC_OT         |
| IX1273     | Payment_VBS_PD_AMEX       |
| IX1274     | Payment_VBS_PD_DISC       |
| IX1277     | Payment_VBS_PD_OT         |

### Unused CSR Payment Detail Codes (3)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1292     | Payment_CSR_CC_OT         |
| IX1293     | Payment_CSR_PD_AMEX       |
| IX1297     | Payment_CSR_PD_OT         |

### Unused Return Types (9)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1303     | CSRReturned               |
| IX1306     | Online_Resources_Returned |
| IX1308     | CHKReturned               |
| IX1309     | METReturned               |
| IX1310     | RPSReturned               |
| IX1311     | OTHReturned               |
| IX1312     | SMSReturned               |
| IX1313     | MOBReturned               |
| IX1314     | Princeton_Returned        |

### Unused Third-Party / Other (3)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1402     | ePost                     |
| IX1404     | Manilla                   |
| IX1405     | BPX_Documents             |

### Unused EFT Payment Detail Codes (6)

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1432     | Payment_EFT_CC_OT         |
| IX1433     | Payment_EFT_PD_AMEX       |
| IX1434     | Payment_EFT_PD_DISC       |
| IX1435     | Payment_EFT_PD_MC         |
| IX1436     | Payment_EFT_PD_VISA       |
| IX1437     | Payment_EFT_PD_OT         |

### Entire IX17xx Alternate Payment Series (27)

These are alternate/duplicate column keys for the same metrics already tracked in the IX12xx series. None had non-zero values.

| Column Key | Display Name              |
|:-----------|:--------------------------|
| IX1702     | BDSPayments               |
| IX1703     | CSRPayments               |
| IX1704     | IVRPayments               |
| IX1705     | ONEPayments               |
| IX1706     | Online_Resources_Payments |
| IX1707     | EFTPayments               |
| IX1708     | CheckFree_Payments        |
| IX1709     | Metavante_Payments        |
| IX1710     | RPPS_Payments             |
| IX1711     | External_Payments         |
| IX1712     | SMS_Payments              |
| IX1713     | Mobile_Payments           |
| IX1714     | Princeton_Payments        |
| IX1750     | Payments                  |
| IX1752     | BDSPayments               |
| IX1753     | CSRPayments               |
| IX1754     | IVRPayments               |
| IX1755     | ONEPayments               |
| IX1756     | Online_Resources_Payments |
| IX1757     | EFTPayments               |
| IX1758     | CheckFree_Payments        |
| IX1759     | Metavante_Payments        |
| IX1760     | RPPS_Payments             |
| IX1761     | External_Payments         |
| IX1762     | SMS_Payments              |
| IX1763     | Mobile_Payments           |
| IX1764     | Princeton_Payments        |

### Entire IX11xxx APPROVED Series (78)

None of the "_APPROVED" tracking codes had non-zero values for any of these clients.

| Column Key | Display Name                      |
|:-----------|:----------------------------------|
| IX11201    | Payments_APPROVED                 |
| IX11202    | BDSPayments_APPROVED              |
| IX11203    | CSRPayments_APPROVED              |
| IX11204    | IVRPayments_APPROVED              |
| IX11205    | ONEPayments_APPROVED              |
| IX11207    | EFTPayments_APPROVED              |
| IX11212    | SMSPayments_APPROVED              |
| IX11213    | MOBPayments_APPROVED              |
| IX11217    | Payment_IVR_ACH_ECP_APPROVED      |
| IX11218    | Payment_IVR_CC_AMEX_APPROVED      |
| IX11219    | Payment_IVR_CC_DISC_APPROVED      |
| IX11220    | Payment_IVR_CC_MC_APPROVED        |
| IX11221    | Payment_IVR_CC_VISA_APPROVED      |
| IX11222    | Payment_IVR_CC_OT_APPROVED        |
| IX11223    | Payment_IVR_PD_AMEX_APPROVED      |
| IX11224    | Payment_IVR_PD_DISC_APPROVED      |
| IX11225    | Payment_IVR_PD_MC_APPROVED        |
| IX11226    | Payment_IVR_PD_VISA_APPROVED      |
| IX11227    | Payment_IVR_PD_OT_APPROVED        |
| IX11237    | Payment_ONE_ACH_ECP_APPROVED      |
| IX11238    | Payment_ONE_CC_AMEX_APPROVED      |
| IX11239    | Payment_ONE_CC_DISC_APPROVED      |
| IX11240    | Payment_ONE_CC_MC_APPROVED        |
| IX11241    | Payment_ONE_CC_VISA_APPROVED      |
| IX11242    | Payment_ONE_CC_OT_APPROVED        |
| IX11243    | Payment_ONE_PD_AMEX_APPROVED      |
| IX11244    | Payment_ONE_PD_DISC_APPROVED      |
| IX11245    | Payment_ONE_PD_MC_APPROVED        |
| IX11246    | Payment_ONE_PD_VISA_APPROVED      |
| IX11247    | Payment_ONE_PD_OT_APPROVED        |
| IX11250    | Conv_Fee_Payments                 |
| IX11267    | Payment_VBS_ACH_ECP_APPROVED      |
| IX11268    | Payment_VBS_CC_AMEX_APPROVED      |
| IX11269    | Payment_VBS_CC_DISC_APPROVED      |
| IX11270    | Payment_VBS_CC_MC_APPROVED        |
| IX11271    | Payment_VBS_CC_VISA_APPROVED      |
| IX11272    | Payment_VBS_CC_OT_APPROVED        |
| IX11273    | Payment_VBS_PD_AMEX_APPROVED      |
| IX11274    | Payment_VBS_PD_DISC_APPROVED      |
| IX11275    | Payment_VBS_PD_MC_APPROVED        |
| IX11276    | Payment_VBS_PD_VISA_APPROVED      |
| IX11277    | Payment_VBS_PD_OT_APPROVED        |
| IX11287    | Payment_CSR_ACH_ECP_APPROVED      |
| IX11288    | Payment_CSR_CC_AMEX_APPROVED      |
| IX11289    | Payment_CSR_CC_DISC_APPROVED      |
| IX11290    | Payment_CSR_CC_MC_APPROVED        |
| IX11291    | Payment_CSR_CC_VISA_APPROVED      |
| IX11292    | Payment_CSR_CC_OT_APPROVED        |
| IX11293    | Payment_CSR_PD_AMEX_APPROVED      |
| IX11294    | Payment_CSR_PD_DISC_APPROVED      |
| IX11295    | Payment_CSR_PD_MC_APPROVED        |
| IX11296    | Payment_CSR_PD_VISA_APPROVED      |
| IX11297    | Payment_CSR_PD_OT_APPROVED        |
| IX11427    | Payment_EFT_ACH_ECP_APPROVED      |
| IX11428    | Payment_EFT_CC_AMEX_APPROVED      |
| IX11429    | Payment_EFT_CC_DISC_APPROVED      |
| IX11430    | Payment_EFT_CC_MC_APPROVED        |
| IX11431    | Payment_EFT_CC_VISA_APPROVED      |
| IX11432    | Payment_EFT_CC_OT_APPROVED        |
| IX11433    | Payment_EFT_PD_AMEX_APPROVED      |
| IX11434    | Payment_EFT_PD_DISC_APPROVED      |
| IX11435    | Payment_EFT_PD_MC_APPROVED        |
| IX11436    | Payment_EFT_PD_VISA_APPROVED      |
| IX11437    | Payment_EFT_PD_OT_APPROVED        |
| IX11702    | BDSPayments_APPROVED              |
| IX11703    | CSRPayments_APPROVED              |
| IX11704    | IVRPayments_APPROVED              |
| IX11705    | ONEPayments_APPROVED              |
| IX11707    | EFTPayments_APPROVED              |
| IX11712    | SMSPayments_APPROVED              |
| IX11713    | MOBPayments_APPROVED              |
| IX11752    | BDSPayments_APPROVED              |
| IX11753    | CSRPayments_APPROVED              |
| IX11754    | IVRPayments_APPROVED              |
| IX11755    | ONEPayments_APPROVED              |
| IX11757    | EFTPayments_APPROVED              |
| IX11762    | SMSPayments_APPROVED              |
| IX11763    | MOBPayments_APPROVED              |

---

### Quick Totals

| Category                         | Count |
|:---------------------------------|------:|
| **Codes used** by these clients  |    60 |
| **Codes not used**               |   146 |
| Total billing column keys        |   206 |
