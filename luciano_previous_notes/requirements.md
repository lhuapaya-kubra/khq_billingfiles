# KHQ Billing File Replication - Requirements

**Status:** Draft
**Date:** March 3, 2026
**Author:** Luciano Huapaya

---

## Background

Legacy iDoxs/DocWeb uses Epicor for automating billing and invoicing to clients for certain products, revenue, and billing models.

**Current flow:** iDoxs (data) -> DocWeb (formatting/mapping values) -> Epicor

Today, the 4 clients on the platform for EZ-PAY+ do not require invoicing due to a convenience fee model. KUBRA takes the convenience fee on a per-transaction basis, not requiring billing to the client.

**KHQ Clients:**

- City of Scottsdale
- City of Stamford
- Port of Long Beach (POLB)
- Lorain County Public Health (LCPH)

---

## Problem

Different products have different pricing models and billing instances at the end of the month (e.g., MyHQ, IVR, etc.).

We do not have billing ready for KHQ clients for products like **MyHQ+** and **IVR+** that have a different billing model requiring end-of-month invoicing.

**Constraint:** Potential new MyHQ+ client going live **May 14, 2026**.

---

## Solution

**Data File Replication:** Replicate the Epicor file sent for MyHQ+ and IVR+ products for now.

**Proposed flow:** KHQ file (data analytics) -> DocWeb (formats and maps the data) -> Epicor

**Future:** Evaluate if KUBRA wants to change the approach.

**Decision:** After talking with Francisco, we are going to use the same billing codes and same billing IDs.

---

## Use Cases

### In-Scope

For the initial phase, the following are in scope:

1. **Replicate billing Epicor file for MyHQ+:** Generate a comma-delimited CSV billing file for MyHQ+ clients that is structurally identical or functionally equivalent to the existing Epicor billing file.

2. **Automated monthly cadence:** Produce the file on a monthly schedule aligned with the existing IRO billing cycle, enabling recurring automated invoicing through Epicor.

### Billing Code Decision

**Option 1 (Selected): Reuse Existing iDoxs Billing Codes** (1-2 sprints)

- Less work across Data Analytics, DocWeb
- Requires no additional rework for finance

---

## Prod File Column Headers

The existing Epicor billing CSV files in production (`BillingCollector_i-doxsBilling_YYYYMM.csv`) contain **208 columns** in the following order. The KHQ replication file must match this structure.

| #   | Column Key    | Display Name                       |
|:----|:--------------|:-----------------------------------|
| 1   | Account       | Account                            |
| 2   | Server        | Server (CAN / US entity)           |
| 3   | IX1101        | Pages                              |
| 4   | IX1102        | Documents                          |
| 5   | IX1103        | Views                              |
| 6   | IX1201        | Payments                           |
| 7   | IX1202        | BDSPayments                        |
| 8   | IX1203        | CSRPayments                        |
| 9   | IX1204        | IVRPayments                        |
| 10  | IX1205        | ONEPayments                        |
| 11  | IX1206        | Online_Resources_Payments          |
| 12  | IX1207        | EFTPayments                        |
| 13  | IX1208        | CheckFree_Payments                 |
| 14  | IX1209        | Metavante_Payments                 |
| 15  | IX1210        | RPPS_Payments                      |
| 16  | IX1211        | External_Payments                  |
| 17  | IX1212        | SMS_Payments                       |
| 18  | IX1213        | Mobile_Payments                    |
| 19  | IX1214        | Princeton_Payments                 |
| 20  | IX1250        | Conv_Fee_Payments                  |
| 21  | IX1260        | IVROutbound                        |
| 22  | IX1302        | BDSReturned                        |
| 23  | IX1303        | CSRReturned                        |
| 24  | IX1304        | IVRReturned                        |
| 25  | IX1305        | ONEReturned                        |
| 26  | IX1306        | Online_Resources_Returned          |
| 27  | IX1307        | EFTReturned                        |
| 28  | IX1308        | CHKReturned                        |
| 29  | IX1309        | METReturned                        |
| 30  | IX1310        | RPSReturned                        |
| 31  | IX1311        | OTHReturned                        |
| 32  | IX1312        | SMSReturned                        |
| 33  | IX1313        | MOBReturned                        |
| 34  | IX1314        | Princeton_Returned                 |
| 35  | IX1401        | CheckFree                          |
| 36  | IX1402        | ePost                              |
| 37  | IX1403        | Metavante                          |
| 38  | IX1404        | Manilla                            |
| 39  | IX1501        | SecureEmails                       |
| 40  | IX1502        | SecureEmail_Pdf_Pages              |
| 41  | IX1600        | SMS_Notifications                  |
| 42  | IX1700        | TotalRemit                         |
| 43  | CatalogDocs   | DocsPerCatalog                     |
| 44  | CatalogPages  | PagesPerCatalog                    |
| 45  | CatalogViews  | ViewsPerCatalog                    |
| 46  | IX1104        | Pages                              |
| 47  | IX1105        | Documents                          |
| 48  | IX1702        | BDSPayments                        |
| 49  | IX1703        | CSRPayments                        |
| 50  | IX1704        | IVRPayments                        |
| 51  | IX1705        | ONEPayments                        |
| 52  | IX1706        | Online_Resources_Payments          |
| 53  | IX1707        | EFTPayments                        |
| 54  | IX1708        | CheckFree_Payments                 |
| 55  | IX1709        | Metavante_Payments                 |
| 56  | IX1710        | RPPS_Payments                      |
| 57  | IX1711        | External_Payments                  |
| 58  | IX1712        | SMS_Payments                       |
| 59  | IX1713        | Mobile_Payments                    |
| 60  | IX1714        | Princeton_Payments                 |
| 61  | IX1750        | Payments                           |
| 62  | IX1752        | BDSPayments                        |
| 63  | IX1753        | CSRPayments                        |
| 64  | IX1754        | IVRPayments                        |
| 65  | IX1755        | ONEPayments                        |
| 66  | IX1756        | Online_Resources_Payments          |
| 67  | IX1757        | EFTPayments                        |
| 68  | IX1758        | CheckFree_Payments                 |
| 69  | IX1759        | Metavante_Payments                 |
| 70  | IX1760        | RPPS_Payments                      |
| 71  | IX1761        | External_Payments                  |
| 72  | IX1762        | SMS_Payments                       |
| 73  | IX1763        | Mobile_Payments                    |
| 74  | IX1764        | Princeton_Payments                 |
| 75  | IX1405        | BPX_Documents                      |
| 76  | IX11201       | Payments_APPROVED                  |
| 77  | IX11202       | BDSPayments_APPROVED               |
| 78  | IX11203       | CSRPayments_APPROVED               |
| 79  | IX11204       | IVRPayments_APPROVED               |
| 80  | IX11205       | ONEPayments_APPROVED               |
| 81  | IX11207       | EFTPayments_APPROVED               |
| 82  | IX11212       | SMSPayments_APPROVED               |
| 83  | IX11213       | MOBPayments_APPROVED               |
| 84  | IX11250       | Conv_Fee_Payments                  |
| 85  | IX11702       | BDSPayments_APPROVED               |
| 86  | IX11703       | CSRPayments_APPROVED               |
| 87  | IX11704       | IVRPayments_APPROVED               |
| 88  | IX11705       | ONEPayments_APPROVED               |
| 89  | IX11707       | EFTPayments_APPROVED               |
| 90  | IX11712       | SMSPayments_APPROVED               |
| 91  | IX11713       | MOBPayments_APPROVED               |
| 92  | IX11752       | BDSPayments_APPROVED               |
| 93  | IX11753       | CSRPayments_APPROVED               |
| 94  | IX11754       | IVRPayments_APPROVED               |
| 95  | IX11755       | ONEPayments_APPROVED               |
| 96  | IX11757       | EFTPayments_APPROVED               |
| 97  | IX11762       | SMSPayments_APPROVED               |
| 98  | IX11763       | MOBPayments_APPROVED               |
| 99  | IX1217        | Payment_IVR_ACH_ECP                |
| 100 | IX1218        | Payment_IVR_CC_AMEX                |
| 101 | IX1219        | Payment_IVR_CC_DISC                |
| 102 | IX1220        | Payment_IVR_CC_MC                  |
| 103 | IX1221        | Payment_IVR_CC_VISA                |
| 104 | IX1222        | Payment_IVR_CC_OT                  |
| 105 | IX1223        | Payment_IVR_PD_AMEX                |
| 106 | IX1224        | Payment_IVR_PD_DISC                |
| 107 | IX1225        | Payment_IVR_PD_MC                  |
| 108 | IX1226        | Payment_IVR_PD_VISA                |
| 109 | IX1227        | Payment_IVR_PD_OT                  |
| 110 | IX1237        | Payment_ONE_ACH_ECP                |
| 111 | IX1238        | Payment_ONE_CC_AMEX                |
| 112 | IX1239        | Payment_ONE_CC_DISC                |
| 113 | IX1240        | Payment_ONE_CC_MC                  |
| 114 | IX1241        | Payment_ONE_CC_VISA                |
| 115 | IX1242        | Payment_ONE_CC_OT                  |
| 116 | IX1243        | Payment_ONE_PD_AMEX                |
| 117 | IX1244        | Payment_ONE_PD_DISC                |
| 118 | IX1245        | Payment_ONE_PD_MC                  |
| 119 | IX1246        | Payment_ONE_PD_VISA                |
| 120 | IX1247        | Payment_ONE_PD_OT                  |
| 121 | IX1267        | Payment_VBS_ACH_ECP                |
| 122 | IX1268        | Payment_VBS_CC_AMEX                |
| 123 | IX1269        | Payment_VBS_CC_DISC                |
| 124 | IX1270        | Payment_VBS_CC_MC                  |
| 125 | IX1271        | Payment_VBS_CC_VISA                |
| 126 | IX1272        | Payment_VBS_CC_OT                  |
| 127 | IX1273        | Payment_VBS_PD_AMEX                |
| 128 | IX1274        | Payment_VBS_PD_DISC                |
| 129 | IX1275        | Payment_VBS_PD_MC                  |
| 130 | IX1276        | Payment_VBS_PD_VISA                |
| 131 | IX1277        | Payment_VBS_PD_OT                  |
| 132 | IX1287        | Payment_CSR_ACH_ECP                |
| 133 | IX1288        | Payment_CSR_CC_AMEX                |
| 134 | IX1289        | Payment_CSR_CC_DISC                |
| 135 | IX1290        | Payment_CSR_CC_MC                  |
| 136 | IX1291        | Payment_CSR_CC_VISA                |
| 137 | IX1292        | Payment_CSR_CC_OT                  |
| 138 | IX1293        | Payment_CSR_PD_AMEX                |
| 139 | IX1294        | Payment_CSR_PD_DISC                |
| 140 | IX1295        | Payment_CSR_PD_MC                  |
| 141 | IX1296        | Payment_CSR_PD_VISA                |
| 142 | IX1297        | Payment_CSR_PD_OT                  |
| 143 | IX1427        | Payment_EFT_ACH_ECP                |
| 144 | IX1428        | Payment_EFT_CC_AMEX                |
| 145 | IX1429        | Payment_EFT_CC_DISC                |
| 146 | IX1430        | Payment_EFT_CC_MC                  |
| 147 | IX1431        | Payment_EFT_CC_VISA                |
| 148 | IX1432        | Payment_EFT_CC_OT                  |
| 149 | IX1433        | Payment_EFT_PD_AMEX                |
| 150 | IX1434        | Payment_EFT_PD_DISC                |
| 151 | IX1435        | Payment_EFT_PD_MC                  |
| 152 | IX1436        | Payment_EFT_PD_VISA                |
| 153 | IX1437        | Payment_EFT_PD_OT                  |
| 154 | IX11217       | Payment_IVR_ACH_ECP_APPROVED       |
| 155 | IX11218       | Payment_IVR_CC_AMEX_APPROVED       |
| 156 | IX11219       | Payment_IVR_CC_DISC_APPROVED       |
| 157 | IX11220       | Payment_IVR_CC_MC_APPROVED         |
| 158 | IX11221       | Payment_IVR_CC_VISA_APPROVED       |
| 159 | IX11222       | Payment_IVR_CC_OT_APPROVED         |
| 160 | IX11223       | Payment_IVR_PD_AMEX_APPROVED       |
| 161 | IX11224       | Payment_IVR_PD_DISC_APPROVED       |
| 162 | IX11225       | Payment_IVR_PD_MC_APPROVED         |
| 163 | IX11226       | Payment_IVR_PD_VISA_APPROVED       |
| 164 | IX11227       | Payment_IVR_PD_OT_APPROVED         |
| 165 | IX11427       | Payment_EFT_ACH_ECP_APPROVED       |
| 166 | IX11428       | Payment_EFT_CC_AMEX_APPROVED       |
| 167 | IX11429       | Payment_EFT_CC_DISC_APPROVED       |
| 168 | IX11430       | Payment_EFT_CC_MC_APPROVED         |
| 169 | IX11431       | Payment_EFT_CC_VISA_APPROVED       |
| 170 | IX11432       | Payment_EFT_CC_OT_APPROVED         |
| 171 | IX11433       | Payment_EFT_PD_AMEX_APPROVED       |
| 172 | IX11434       | Payment_EFT_PD_DISC_APPROVED       |
| 173 | IX11435       | Payment_EFT_PD_MC_APPROVED         |
| 174 | IX11436       | Payment_EFT_PD_VISA_APPROVED       |
| 175 | IX11437       | Payment_EFT_PD_OT_APPROVED         |
| 176 | IX11237       | Payment_ONE_ACH_ECP_APPROVED       |
| 177 | IX11238       | Payment_ONE_CC_AMEX_APPROVED       |
| 178 | IX11239       | Payment_ONE_CC_DISC_APPROVED       |
| 179 | IX11240       | Payment_ONE_CC_MC_APPROVED         |
| 180 | IX11241       | Payment_ONE_CC_VISA_APPROVED       |
| 181 | IX11242       | Payment_ONE_CC_OT_APPROVED         |
| 182 | IX11243       | Payment_ONE_PD_AMEX_APPROVED       |
| 183 | IX11244       | Payment_ONE_PD_DISC_APPROVED       |
| 184 | IX11245       | Payment_ONE_PD_MC_APPROVED         |
| 185 | IX11246       | Payment_ONE_PD_VISA_APPROVED       |
| 186 | IX11247       | Payment_ONE_PD_OT_APPROVED         |
| 187 | IX11267       | Payment_VBS_ACH_ECP_APPROVED       |
| 188 | IX11268       | Payment_VBS_CC_AMEX_APPROVED       |
| 189 | IX11269       | Payment_VBS_CC_DISC_APPROVED       |
| 190 | IX11270       | Payment_VBS_CC_MC_APPROVED         |
| 191 | IX11271       | Payment_VBS_CC_VISA_APPROVED       |
| 192 | IX11272       | Payment_VBS_CC_OT_APPROVED         |
| 193 | IX11273       | Payment_VBS_PD_AMEX_APPROVED       |
| 194 | IX11274       | Payment_VBS_PD_DISC_APPROVED       |
| 195 | IX11275       | Payment_VBS_PD_MC_APPROVED         |
| 196 | IX11276       | Payment_VBS_PD_VISA_APPROVED       |
| 197 | IX11277       | Payment_VBS_PD_OT_APPROVED         |
| 198 | IX11287       | Payment_CSR_ACH_ECP_APPROVED       |
| 199 | IX11288       | Payment_CSR_CC_AMEX_APPROVED       |
| 200 | IX11289       | Payment_CSR_CC_DISC_APPROVED       |
| 201 | IX11290       | Payment_CSR_CC_MC_APPROVED         |
| 202 | IX11291       | Payment_CSR_CC_VISA_APPROVED       |
| 203 | IX11292       | Payment_CSR_CC_OT_APPROVED         |
| 204 | IX11293       | Payment_CSR_PD_AMEX_APPROVED       |
| 205 | IX11294       | Payment_CSR_PD_DISC_APPROVED       |
| 206 | IX11295       | Payment_CSR_PD_MC_APPROVED         |
| 207 | IX11296       | Payment_CSR_PD_VISA_APPROVED       |
| 208 | IX11297       | Payment_CSR_PD_OT_APPROVED         |

---

## Column Categories Summary

The 208 columns break down as follows:

| Category                              | Columns | Range               |
|:--------------------------------------|:--------|:--------------------|
| Identifiers                           | 2       | Account, Server     |
| Core Metrics (Pages, Docs, Views)     | 5       | IX1101-IX1105       |
| Payment Channels                      | 15      | IX1201-IX1214, IX1250 |
| IVR Outbound                          | 1       | IX1260              |
| Returns                               | 13      | IX1302-IX1314       |
| Third-Party / Other                   | 5       | IX1401-IX1405       |
| Secure Email                          | 2       | IX1501-IX1502       |
| SMS Notifications                     | 1       | IX1600              |
| Total Remit                           | 1       | IX1700              |
| Catalog Metrics                       | 3       | CatalogDocs/Pages/Views |
| Alternate Payment Series (IX17xx)     | 27      | IX1702-IX1764       |
| Payment Detail - IVR                  | 11      | IX1217-IX1227       |
| Payment Detail - ONE                  | 11      | IX1237-IX1247       |
| Payment Detail - VBS                  | 11      | IX1267-IX1277       |
| Payment Detail - CSR                  | 11      | IX1287-IX1297       |
| Payment Detail - EFT                  | 11      | IX1427-IX1437       |
| APPROVED Series (all channels)        | 78      | IX11201-IX11297, IX11427-IX11437 |

---

## KHQ-Relevant Columns (MyHQ+ Scope)

Based on the column-headers analysis, the following columns are tagged as relevant to MyHQ+:

| Column Key | Display Name | Category |
|:-----------|:-------------|:---------|
| IX1101     | Pages        | Documents / MyHQ+ |
| IX1102     | Documents    | Documents / MyHQ+ |
| IX1103     | Views        | Documents / MyHQ+ |
| IX1201     | Payments     | Payments / MyHQ+ |

> All remaining columns should be included in the output file for structural compatibility but will be populated with `0` for KHQ clients that do not use those features.

---

## Open Questions

- [ ] Should we continue with the same billing codes or create new ones? (**Decision: Reuse existing - Option 1**)
- [ ] Which specific KHQ clients will need MyHQ+ billing first?
- [ ] What is the exact monthly schedule/cutoff date for file generation?
- [ ] Who is the new MyHQ+ client going live May 14, 2026?
- [ ] IVR+ billing scope and timeline -- when will this be included?
