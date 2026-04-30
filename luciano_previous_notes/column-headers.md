# Billing CSV Column Headers Reference

This file maps the column key codes used in the billing CSV files (`prod_files/` and `test_files/`) to their human-readable display names, based on the config mapping. All CSV column headers are now fully mapped.


-- 
notes with mihaela and dhiren:
 - documents: jobs load, documents viewed, secure email, 
 - notifications: sms, email, 
 - payments: by type. 
 - consumers count: should be charging. (recommendation)
 - IVR: call duration. (seperate)

 legacy clients MyHQ: 
 - Lakeland US
 - Metergy CAN
 - Casella 
 - Carma US

---

## Column Key to Display Name

Sorted by column key for quick lookup.

| Column Key | Display Name |
|------------|--------------|
| CatalogDocs | DocsPerCatalog | 
| CatalogPages | PagesPerCatalog |
| CatalogViews | ViewsPerCatalog |
| IX1101 | Pages | Documents | MyHQ+
| IX1102 | Documents | Documents | MyHQ+
| IX1103 | Views | Documents | MyHQ+
| IX1104 | Pages | Documents
| IX1105 | Documents | Documents 
| IX1201 | Payments | Payments | MyHQ+
| IX1202 | BDSPayments | Payments
| IX1203 | CSRPayments | Payments
| IX1204 | IVRPayments | Payments
| IX1205 | ONEPayments | Payments
| IX1206 | Online_Resources_Payments |
| IX1207 | EFTPayments |
| IX1208 | CheckFree_Payments |
| IX1209 | Metavante_Payments |
| IX1210 | RPPS_Payments |
| IX1211 | External_Payments |
| IX1212 | SMS_Payments |
| IX1213 | Mobile_Payments |
| IX1214 | Princeton_Payments |
| IX1217 | Payment_IVR_ACH_ECP |
| IX1218 | Payment_IVR_CC_AMEX |
| IX1219 | Payment_IVR_CC_DISC |
| IX1220 | Payment_IVR_CC_MC |
| IX1221 | Payment_IVR_CC_VISA |
| IX1222 | Payment_IVR_CC_OT |
| IX1223 | Payment_IVR_PD_AMEX |
| IX1224 | Payment_IVR_PD_DISC |
| IX1225 | Payment_IVR_PD_MC |
| IX1226 | Payment_IVR_PD_VISA |
| IX1227 | Payment_IVR_PD_OT |
| IX1237 | Payment_ONE_ACH_ECP |
| IX1238 | Payment_ONE_CC_AMEX |
| IX1239 | Payment_ONE_CC_DISC |
| IX1240 | Payment_ONE_CC_MC |
| IX1241 | Payment_ONE_CC_VISA |
| IX1242 | Payment_ONE_CC_OT |
| IX1243 | Payment_ONE_PD_AMEX |
| IX1244 | Payment_ONE_PD_DISC |
| IX1245 | Payment_ONE_PD_MC |
| IX1246 | Payment_ONE_PD_VISA |
| IX1247 | Payment_ONE_PD_OT |
| IX1250 | Conv_Fee_Payments |
| IX1260 | IVROutbound |
| IX1267 | Payment_VBS_ACH_ECP |
| IX1268 | Payment_VBS_CC_AMEX |
| IX1269 | Payment_VBS_CC_DISC |
| IX1270 | Payment_VBS_CC_MC |
| IX1271 | Payment_VBS_CC_VISA |
| IX1272 | Payment_VBS_CC_OT |
| IX1273 | Payment_VBS_PD_AMEX |
| IX1274 | Payment_VBS_PD_DISC |
| IX1275 | Payment_VBS_PD_MC |
| IX1276 | Payment_VBS_PD_VISA |
| IX1277 | Payment_VBS_PD_OT |
| IX1287 | Payment_CSR_ACH_ECP |
| IX1288 | Payment_CSR_CC_AMEX |
| IX1289 | Payment_CSR_CC_DISC |
| IX1290 | Payment_CSR_CC_MC |
| IX1291 | Payment_CSR_CC_VISA |
| IX1292 | Payment_CSR_CC_OT |
| IX1293 | Payment_CSR_PD_AMEX |
| IX1294 | Payment_CSR_PD_DISC |
| IX1295 | Payment_CSR_PD_MC |
| IX1296 | Payment_CSR_PD_VISA |
| IX1297 | Payment_CSR_PD_OT |
| IX1302 | BDSReturned |
| IX1303 | CSRReturned |
| IX1304 | IVRReturned |
| IX1305 | ONEReturned |
| IX1306 | Online_Resources_Returned |
| IX1307 | EFTReturned |
| IX1308 | CHKReturned |
| IX1309 | METReturned |
| IX1310 | RPSReturned |
| IX1311 | OTHReturned |
| IX1312 | SMSReturned |
| IX1313 | MOBReturned |
| IX1314 | Princeton_Returned |
| IX1401 | CheckFree |
| IX1402 | ePost |
| IX1403 | Metavante |
| IX1404 | Manilla |
| IX1405 | BPX_Documents |
| IX1427 | Payment_EFT_ACH_ECP |
| IX1428 | Payment_EFT_CC_AMEX |
| IX1429 | Payment_EFT_CC_DISC |
| IX1430 | Payment_EFT_CC_MC |
| IX1431 | Payment_EFT_CC_VISA |
| IX1432 | Payment_EFT_CC_OT |
| IX1433 | Payment_EFT_PD_AMEX |
| IX1434 | Payment_EFT_PD_DISC |
| IX1435 | Payment_EFT_PD_MC |
| IX1436 | Payment_EFT_PD_VISA |
| IX1437 | Payment_EFT_PD_OT |
| IX1501 | SecureEmails |
| IX1502 | SecureEmail_Pdf_Pages |
| IX1600 | SMS_Notifications |
| IX1700 | TotalRemit |
| IX1702 | BDSPayments |
| IX1703 | CSRPayments |
| IX1704 | IVRPayments |
| IX1705 | ONEPayments |
| IX1706 | Online_Resources_Payments |
| IX1707 | EFTPayments |
| IX1708 | CheckFree_Payments |
| IX1709 | Metavante_Payments |
| IX1710 | RPPS_Payments |
| IX1711 | External_Payments |
| IX1712 | SMS_Payments |
| IX1713 | Mobile_Payments |
| IX1714 | Princeton_Payments |
| IX1750 | Payments |
| IX1752 | BDSPayments |
| IX1753 | CSRPayments |
| IX1754 | IVRPayments |
| IX1755 | ONEPayments |
| IX1756 | Online_Resources_Payments |
| IX1757 | EFTPayments |
| IX1758 | CheckFree_Payments |
| IX1759 | Metavante_Payments |
| IX1760 | RPPS_Payments |
| IX1761 | External_Payments |
| IX1762 | SMS_Payments |
| IX1763 | Mobile_Payments |
| IX1764 | Princeton_Payments |
| IX11201 | Payments_APPROVED |
| IX11202 | BDSPayments_APPROVED |
| IX11203 | CSRPayments_APPROVED |
| IX11204 | IVRPayments_APPROVED |
| IX11205 | ONEPayments_APPROVED |
| IX11207 | EFTPayments_APPROVED |
| IX11212 | SMSPayments_APPROVED |
| IX11213 | MOBPayments_APPROVED |
| IX11217 | Payment_IVR_ACH_ECP_APPROVED |
| IX11218 | Payment_IVR_CC_AMEX_APPROVED |
| IX11219 | Payment_IVR_CC_DISC_APPROVED |
| IX11220 | Payment_IVR_CC_MC_APPROVED |
| IX11221 | Payment_IVR_CC_VISA_APPROVED |
| IX11222 | Payment_IVR_CC_OT_APPROVED |
| IX11223 | Payment_IVR_PD_AMEX_APPROVED |
| IX11224 | Payment_IVR_PD_DISC_APPROVED |
| IX11225 | Payment_IVR_PD_MC_APPROVED |
| IX11226 | Payment_IVR_PD_VISA_APPROVED |
| IX11227 | Payment_IVR_PD_OT_APPROVED |
| IX11237 | Payment_ONE_ACH_ECP_APPROVED |
| IX11238 | Payment_ONE_CC_AMEX_APPROVED |
| IX11239 | Payment_ONE_CC_DISC_APPROVED |
| IX11240 | Payment_ONE_CC_MC_APPROVED |
| IX11241 | Payment_ONE_CC_VISA_APPROVED |
| IX11242 | Payment_ONE_CC_OT_APPROVED |
| IX11243 | Payment_ONE_PD_AMEX_APPROVED |
| IX11244 | Payment_ONE_PD_DISC_APPROVED |
| IX11245 | Payment_ONE_PD_MC_APPROVED |
| IX11246 | Payment_ONE_PD_VISA_APPROVED |
| IX11247 | Payment_ONE_PD_OT_APPROVED |
| IX11250 | Conv_Fee_Payments |
| IX11267 | Payment_VBS_ACH_ECP_APPROVED |
| IX11268 | Payment_VBS_CC_AMEX_APPROVED |
| IX11269 | Payment_VBS_CC_DISC_APPROVED |
| IX11270 | Payment_VBS_CC_MC_APPROVED |
| IX11271 | Payment_VBS_CC_VISA_APPROVED |
| IX11272 | Payment_VBS_CC_OT_APPROVED |
| IX11273 | Payment_VBS_PD_AMEX_APPROVED |
| IX11274 | Payment_VBS_PD_DISC_APPROVED |
| IX11275 | Payment_VBS_PD_MC_APPROVED |
| IX11276 | Payment_VBS_PD_VISA_APPROVED |
| IX11277 | Payment_VBS_PD_OT_APPROVED |
| IX11287 | Payment_CSR_ACH_ECP_APPROVED |
| IX11288 | Payment_CSR_CC_AMEX_APPROVED |
| IX11289 | Payment_CSR_CC_DISC_APPROVED |
| IX11290 | Payment_CSR_CC_MC_APPROVED |
| IX11291 | Payment_CSR_CC_VISA_APPROVED |
| IX11292 | Payment_CSR_CC_OT_APPROVED |
| IX11293 | Payment_CSR_PD_AMEX_APPROVED |
| IX11294 | Payment_CSR_PD_DISC_APPROVED |
| IX11295 | Payment_CSR_PD_MC_APPROVED |
| IX11296 | Payment_CSR_PD_VISA_APPROVED |
| IX11297 | Payment_CSR_PD_OT_APPROVED |
| IX11427 | Payment_EFT_ACH_ECP_APPROVED |
| IX11428 | Payment_EFT_CC_AMEX_APPROVED |
| IX11429 | Payment_EFT_CC_DISC_APPROVED |
| IX11430 | Payment_EFT_CC_MC_APPROVED |
| IX11431 | Payment_EFT_CC_VISA_APPROVED |
| IX11432 | Payment_EFT_CC_OT_APPROVED |
| IX11433 | Payment_EFT_PD_AMEX_APPROVED |
| IX11434 | Payment_EFT_PD_DISC_APPROVED |
| IX11435 | Payment_EFT_PD_MC_APPROVED |
| IX11436 | Payment_EFT_PD_VISA_APPROVED |
| IX11437 | Payment_EFT_PD_OT_APPROVED |
| IX11702 | BDSPayments_APPROVED |
| IX11703 | CSRPayments_APPROVED |
| IX11704 | IVRPayments_APPROVED |
| IX11705 | ONEPayments_APPROVED |
| IX11707 | EFTPayments_APPROVED |
| IX11712 | SMSPayments_APPROVED |
| IX11713 | MOBPayments_APPROVED |
| IX11752 | BDSPayments_APPROVED |
| IX11753 | CSRPayments_APPROVED |
| IX11754 | IVRPayments_APPROVED |
| IX11755 | ONEPayments_APPROVED |
| IX11757 | EFTPayments_APPROVED |
| IX11762 | SMSPayments_APPROVED |
| IX11763 | MOBPayments_APPROVED |

---

## Display Name to Column Keys (Reverse Lookup)

Sorted alphabetically by display name. Useful when the same name maps to multiple keys across different series.

| Display Name | Column Key(s) |
|--------------|---------------|
| BDSPayments | IX1202, IX1702, IX1752 |
| BDSPayments_APPROVED | IX11202, IX11702, IX11752 |
| BDSReturned | IX1302 |
| BPX_Documents | IX1405 |
| CHKReturned | IX1308 |
| CSRPayments | IX1203, IX1703, IX1753 |
| CSRPayments_APPROVED | IX11203, IX11703, IX11753 |
| CSRReturned | IX1303 |
| CheckFree | IX1401 |
| CheckFree_Payments | IX1208, IX1708, IX1758 |
| Conv_Fee_Payments | IX1250, IX11250 |
| Documents | IX1102, IX1105 |
| DocsPerCatalog | CatalogDocs |
| EFTPayments | IX1207, IX1707, IX1757 |
| EFTPayments_APPROVED | IX11207, IX11707, IX11757 |
| EFTReturned | IX1307 |
| External_Payments | IX1211, IX1711, IX1761 |
| IVROutbound | IX1260 |
| IVRPayments | IX1204, IX1704, IX1754 |
| IVRPayments_APPROVED | IX11204, IX11704, IX11754 |
| IVRReturned | IX1304 |
| MOBPayments_APPROVED | IX11213, IX11713, IX11763 |
| MOBReturned | IX1313 |
| METReturned | IX1309 |
| Manilla | IX1404 |
| Metavante | IX1403 |
| Metavante_Payments | IX1209, IX1709, IX1759 |
| Mobile_Payments | IX1213, IX1713, IX1763 |
| ONEPayments | IX1205, IX1705, IX1755 |
| ONEPayments_APPROVED | IX11205, IX11705, IX11755 |
| ONEReturned | IX1305 |
| OTHReturned | IX1311 |
| Online_Resources_Payments | IX1206, IX1706, IX1756 |
| Online_Resources_Returned | IX1306 |
| Pages | IX1101, IX1104 |
| PagesPerCatalog | CatalogPages |
| Payment_CSR_ACH_ECP | IX1287 |
| Payment_CSR_ACH_ECP_APPROVED | IX11287 |
| Payment_CSR_CC_AMEX | IX1288 |
| Payment_CSR_CC_AMEX_APPROVED | IX11288 |
| Payment_CSR_CC_DISC | IX1289 |
| Payment_CSR_CC_DISC_APPROVED | IX11289 |
| Payment_CSR_CC_MC | IX1290 |
| Payment_CSR_CC_MC_APPROVED | IX11290 |
| Payment_CSR_CC_OT | IX1292 |
| Payment_CSR_CC_OT_APPROVED | IX11292 |
| Payment_CSR_CC_VISA | IX1291 |
| Payment_CSR_CC_VISA_APPROVED | IX11291 |
| Payment_CSR_PD_AMEX | IX1293 |
| Payment_CSR_PD_AMEX_APPROVED | IX11293 |
| Payment_CSR_PD_DISC | IX1294 |
| Payment_CSR_PD_DISC_APPROVED | IX11294 |
| Payment_CSR_PD_MC | IX1295 |
| Payment_CSR_PD_MC_APPROVED | IX11295 |
| Payment_CSR_PD_OT | IX1297 |
| Payment_CSR_PD_OT_APPROVED | IX11297 |
| Payment_CSR_PD_VISA | IX1296 |
| Payment_CSR_PD_VISA_APPROVED | IX11296 |
| Payment_EFT_ACH_ECP | IX1427 |
| Payment_EFT_ACH_ECP_APPROVED | IX11427 |
| Payment_EFT_CC_AMEX | IX1428 |
| Payment_EFT_CC_AMEX_APPROVED | IX11428 |
| Payment_EFT_CC_DISC | IX1429 |
| Payment_EFT_CC_DISC_APPROVED | IX11429 |
| Payment_EFT_CC_MC | IX1430 |
| Payment_EFT_CC_MC_APPROVED | IX11430 |
| Payment_EFT_CC_OT | IX1432 |
| Payment_EFT_CC_OT_APPROVED | IX11432 |
| Payment_EFT_CC_VISA | IX1431 |
| Payment_EFT_CC_VISA_APPROVED | IX11431 |
| Payment_EFT_PD_AMEX | IX1433 |
| Payment_EFT_PD_AMEX_APPROVED | IX11433 |
| Payment_EFT_PD_DISC | IX1434 |
| Payment_EFT_PD_DISC_APPROVED | IX11434 |
| Payment_EFT_PD_MC | IX1435 |
| Payment_EFT_PD_MC_APPROVED | IX11435 |
| Payment_EFT_PD_OT | IX1437 |
| Payment_EFT_PD_OT_APPROVED | IX11437 |
| Payment_EFT_PD_VISA | IX1436 |
| Payment_EFT_PD_VISA_APPROVED | IX11436 |
| Payment_IVR_ACH_ECP | IX1217 |
| Payment_IVR_ACH_ECP_APPROVED | IX11217 |
| Payment_IVR_CC_AMEX | IX1218 |
| Payment_IVR_CC_AMEX_APPROVED | IX11218 |
| Payment_IVR_CC_DISC | IX1219 |
| Payment_IVR_CC_DISC_APPROVED | IX11219 |
| Payment_IVR_CC_MC | IX1220 |
| Payment_IVR_CC_MC_APPROVED | IX11220 |
| Payment_IVR_CC_OT | IX1222 |
| Payment_IVR_CC_OT_APPROVED | IX11222 |
| Payment_IVR_CC_VISA | IX1221 |
| Payment_IVR_CC_VISA_APPROVED | IX11221 |
| Payment_IVR_PD_AMEX | IX1223 |
| Payment_IVR_PD_AMEX_APPROVED | IX11223 |
| Payment_IVR_PD_DISC | IX1224 |
| Payment_IVR_PD_DISC_APPROVED | IX11224 |
| Payment_IVR_PD_MC | IX1225 |
| Payment_IVR_PD_MC_APPROVED | IX11225 |
| Payment_IVR_PD_OT | IX1227 |
| Payment_IVR_PD_OT_APPROVED | IX11227 |
| Payment_IVR_PD_VISA | IX1226 |
| Payment_IVR_PD_VISA_APPROVED | IX11226 |
| Payment_ONE_ACH_ECP | IX1237 |
| Payment_ONE_ACH_ECP_APPROVED | IX11237 |
| Payment_ONE_CC_AMEX | IX1238 |
| Payment_ONE_CC_AMEX_APPROVED | IX11238 |
| Payment_ONE_CC_DISC | IX1239 |
| Payment_ONE_CC_DISC_APPROVED | IX11239 |
| Payment_ONE_CC_MC | IX1240 |
| Payment_ONE_CC_MC_APPROVED | IX11240 |
| Payment_ONE_CC_OT | IX1242 |
| Payment_ONE_CC_OT_APPROVED | IX11242 |
| Payment_ONE_CC_VISA | IX1241 |
| Payment_ONE_CC_VISA_APPROVED | IX11241 |
| Payment_ONE_PD_AMEX | IX1243 |
| Payment_ONE_PD_AMEX_APPROVED | IX11243 |
| Payment_ONE_PD_DISC | IX1244 |
| Payment_ONE_PD_DISC_APPROVED | IX11244 |
| Payment_ONE_PD_MC | IX1245 |
| Payment_ONE_PD_MC_APPROVED | IX11245 |
| Payment_ONE_PD_OT | IX1247 |
| Payment_ONE_PD_OT_APPROVED | IX11247 |
| Payment_ONE_PD_VISA | IX1246 |
| Payment_ONE_PD_VISA_APPROVED | IX11246 |
| Payment_VBS_ACH_ECP | IX1267 |
| Payment_VBS_ACH_ECP_APPROVED | IX11267 |
| Payment_VBS_CC_AMEX | IX1268 |
| Payment_VBS_CC_AMEX_APPROVED | IX11268 |
| Payment_VBS_CC_DISC | IX1269 |
| Payment_VBS_CC_DISC_APPROVED | IX11269 |
| Payment_VBS_CC_MC | IX1270 |
| Payment_VBS_CC_MC_APPROVED | IX11270 |
| Payment_VBS_CC_OT | IX1272 |
| Payment_VBS_CC_OT_APPROVED | IX11272 |
| Payment_VBS_CC_VISA | IX1271 |
| Payment_VBS_CC_VISA_APPROVED | IX11271 |
| Payment_VBS_PD_AMEX | IX1273 |
| Payment_VBS_PD_AMEX_APPROVED | IX11273 |
| Payment_VBS_PD_DISC | IX1274 |
| Payment_VBS_PD_DISC_APPROVED | IX11274 |
| Payment_VBS_PD_MC | IX1275 |
| Payment_VBS_PD_MC_APPROVED | IX11275 |
| Payment_VBS_PD_OT | IX1277 |
| Payment_VBS_PD_OT_APPROVED | IX11277 |
| Payment_VBS_PD_VISA | IX1276 |
| Payment_VBS_PD_VISA_APPROVED | IX11276 |
| Payments | IX1201, IX1750 |
| Payments_APPROVED | IX11201 |
| Princeton_Payments | IX1214, IX1714, IX1764 |
| Princeton_Returned | IX1314 |
| RPPS_Payments | IX1210, IX1710, IX1760 |
| RPSReturned | IX1310 |
| SMS_Notifications | IX1600 |
| SMS_Payments | IX1212, IX1712, IX1762 |
| SMSPayments_APPROVED | IX11212, IX11712, IX11762 |
| SMSReturned | IX1312 |
| SecureEmail_Pdf_Pages | IX1502 |
| SecureEmails | IX1501 |
| TotalRemit | IX1700 |
| Views | IX1103 |
| ViewsPerCatalog | CatalogViews |
| ePost | IX1402 |

---

## Prod File Column Order

The columns appear in this exact order (left to right) in the prod CSV files. Both `BillingCollector_i-doxsBilling_202512.csv` and `BillingCollector_i-doxsBilling_202601.csv` share the same layout.

| # | Column Key | Display Name |
|---|------------|--------------|
| 1 | Account | Account |
| 2 | Server | Server | (this classifies as CAN or US entity)
| 3 | IX1101 | Pages |
| 4 | IX1102 | Documents |
| 5 | IX1103 | Views |
| 6 | IX1201 | Payments |
| 7 | IX1202 | BDSPayments |
| 8 | IX1203 | CSRPayments |
| 9 | IX1204 | IVRPayments |
| 10 | IX1205 | ONEPayments |
| 11 | IX1206 | Online_Resources_Payments |
| 12 | IX1207 | EFTPayments |
| 13 | IX1208 | CheckFree_Payments |
| 14 | IX1209 | Metavante_Payments |
| 15 | IX1210 | RPPS_Payments |
| 16 | IX1211 | External_Payments |
| 17 | IX1212 | SMS_Payments |
| 18 | IX1213 | Mobile_Payments |
| 19 | IX1214 | Princeton_Payments |
| 20 | IX1250 | Conv_Fee_Payments |
| 21 | IX1260 | IVROutbound |
| 22 | IX1302 | BDSReturned |
| 23 | IX1303 | CSRReturned |
| 24 | IX1304 | IVRReturned |
| 25 | IX1305 | ONEReturned |
| 26 | IX1306 | Online_Resources_Returned |
| 27 | IX1307 | EFTReturned |
| 28 | IX1308 | CHKReturned |
| 29 | IX1309 | METReturned |
| 30 | IX1310 | RPSReturned |
| 31 | IX1311 | OTHReturned |
| 32 | IX1312 | SMSReturned |
| 33 | IX1313 | MOBReturned |
| 34 | IX1314 | Princeton_Returned |
| 35 | IX1401 | CheckFree |
| 36 | IX1402 | ePost |
| 37 | IX1403 | Metavante |
| 38 | IX1404 | Manilla |
| 39 | IX1501 | SecureEmails |
| 40 | IX1502 | SecureEmail_Pdf_Pages |
| 41 | IX1600 | SMS_Notifications |
| 42 | IX1700 | TotalRemit |
| 43 | CatalogDocs | DocsPerCatalog |
| 44 | CatalogPages | PagesPerCatalog |
| 45 | CatalogViews | ViewsPerCatalog |
| 46 | IX1104 | Pages |
| 47 | IX1105 | Documents |
| 48 | IX1702 | BDSPayments |
| 49 | IX1703 | CSRPayments |
| 50 | IX1704 | IVRPayments |
| 51 | IX1705 | ONEPayments |
| 52 | IX1706 | Online_Resources_Payments |
| 53 | IX1707 | EFTPayments |
| 54 | IX1708 | CheckFree_Payments |
| 55 | IX1709 | Metavante_Payments |
| 56 | IX1710 | RPPS_Payments |
| 57 | IX1711 | External_Payments |
| 58 | IX1712 | SMS_Payments |
| 59 | IX1713 | Mobile_Payments |
| 60 | IX1714 | Princeton_Payments |
| 61 | IX1750 | Payments |
| 62 | IX1752 | BDSPayments |
| 63 | IX1753 | CSRPayments |
| 64 | IX1754 | IVRPayments |
| 65 | IX1755 | ONEPayments |
| 66 | IX1756 | Online_Resources_Payments |
| 67 | IX1757 | EFTPayments |
| 68 | IX1758 | CheckFree_Payments |
| 69 | IX1759 | Metavante_Payments |
| 70 | IX1760 | RPPS_Payments |
| 71 | IX1761 | External_Payments |
| 72 | IX1762 | SMS_Payments |
| 73 | IX1763 | Mobile_Payments |
| 74 | IX1764 | Princeton_Payments |
| 75 | IX1405 | BPX_Documents |
| 76 | IX11201 | Payments_APPROVED |
| 77 | IX11202 | BDSPayments_APPROVED |
| 78 | IX11203 | CSRPayments_APPROVED |
| 79 | IX11204 | IVRPayments_APPROVED |
| 80 | IX11205 | ONEPayments_APPROVED |
| 81 | IX11207 | EFTPayments_APPROVED |
| 82 | IX11212 | SMSPayments_APPROVED |
| 83 | IX11213 | MOBPayments_APPROVED |
| 84 | IX11250 | Conv_Fee_Payments |
| 85 | IX11702 | BDSPayments_APPROVED |
| 86 | IX11703 | CSRPayments_APPROVED |
| 87 | IX11704 | IVRPayments_APPROVED |
| 88 | IX11705 | ONEPayments_APPROVED |
| 89 | IX11707 | EFTPayments_APPROVED |
| 90 | IX11712 | SMSPayments_APPROVED |
| 91 | IX11713 | MOBPayments_APPROVED |
| 92 | IX11752 | BDSPayments_APPROVED |
| 93 | IX11753 | CSRPayments_APPROVED |
| 94 | IX11754 | IVRPayments_APPROVED |
| 95 | IX11755 | ONEPayments_APPROVED |
| 96 | IX11757 | EFTPayments_APPROVED |
| 97 | IX11762 | SMSPayments_APPROVED |
| 98 | IX11763 | MOBPayments_APPROVED |
| 99 | IX1217 | Payment_IVR_ACH_ECP |
| 100 | IX1218 | Payment_IVR_CC_AMEX |
| 101 | IX1219 | Payment_IVR_CC_DISC |
| 102 | IX1220 | Payment_IVR_CC_MC |
| 103 | IX1221 | Payment_IVR_CC_VISA |
| 104 | IX1222 | Payment_IVR_CC_OT |
| 105 | IX1223 | Payment_IVR_PD_AMEX |
| 106 | IX1224 | Payment_IVR_PD_DISC |
| 107 | IX1225 | Payment_IVR_PD_MC |
| 108 | IX1226 | Payment_IVR_PD_VISA |
| 109 | IX1227 | Payment_IVR_PD_OT |
| 110 | IX1237 | Payment_ONE_ACH_ECP |
| 111 | IX1238 | Payment_ONE_CC_AMEX |
| 112 | IX1239 | Payment_ONE_CC_DISC |
| 113 | IX1240 | Payment_ONE_CC_MC |
| 114 | IX1241 | Payment_ONE_CC_VISA |
| 115 | IX1242 | Payment_ONE_CC_OT |
| 116 | IX1243 | Payment_ONE_PD_AMEX |
| 117 | IX1244 | Payment_ONE_PD_DISC |
| 118 | IX1245 | Payment_ONE_PD_MC |
| 119 | IX1246 | Payment_ONE_PD_VISA |
| 120 | IX1247 | Payment_ONE_PD_OT |
| 121 | IX1267 | Payment_VBS_ACH_ECP |
| 122 | IX1268 | Payment_VBS_CC_AMEX |
| 123 | IX1269 | Payment_VBS_CC_DISC |
| 124 | IX1270 | Payment_VBS_CC_MC |
| 125 | IX1271 | Payment_VBS_CC_VISA |
| 126 | IX1272 | Payment_VBS_CC_OT |
| 127 | IX1273 | Payment_VBS_PD_AMEX |
| 128 | IX1274 | Payment_VBS_PD_DISC |
| 129 | IX1275 | Payment_VBS_PD_MC |
| 130 | IX1276 | Payment_VBS_PD_VISA |
| 131 | IX1277 | Payment_VBS_PD_OT |
| 132 | IX1287 | Payment_CSR_ACH_ECP |
| 133 | IX1288 | Payment_CSR_CC_AMEX |
| 134 | IX1289 | Payment_CSR_CC_DISC |
| 135 | IX1290 | Payment_CSR_CC_MC |
| 136 | IX1291 | Payment_CSR_CC_VISA |
| 137 | IX1292 | Payment_CSR_CC_OT |
| 138 | IX1293 | Payment_CSR_PD_AMEX |
| 139 | IX1294 | Payment_CSR_PD_DISC |
| 140 | IX1295 | Payment_CSR_PD_MC |
| 141 | IX1296 | Payment_CSR_PD_VISA |
| 142 | IX1297 | Payment_CSR_PD_OT |
| 143 | IX1427 | Payment_EFT_ACH_ECP |
| 144 | IX1428 | Payment_EFT_CC_AMEX |
| 145 | IX1429 | Payment_EFT_CC_DISC |
| 146 | IX1430 | Payment_EFT_CC_MC |
| 147 | IX1431 | Payment_EFT_CC_VISA |
| 148 | IX1432 | Payment_EFT_CC_OT |
| 149 | IX1433 | Payment_EFT_PD_AMEX |
| 150 | IX1434 | Payment_EFT_PD_DISC |
| 151 | IX1435 | Payment_EFT_PD_MC |
| 152 | IX1436 | Payment_EFT_PD_VISA |
| 153 | IX1437 | Payment_EFT_PD_OT |
| 154 | IX11217 | Payment_IVR_ACH_ECP_APPROVED |
| 155 | IX11218 | Payment_IVR_CC_AMEX_APPROVED |
| 156 | IX11219 | Payment_IVR_CC_DISC_APPROVED |
| 157 | IX11220 | Payment_IVR_CC_MC_APPROVED |
| 158 | IX11221 | Payment_IVR_CC_VISA_APPROVED |
| 159 | IX11222 | Payment_IVR_CC_OT_APPROVED |
| 160 | IX11223 | Payment_IVR_PD_AMEX_APPROVED |
| 161 | IX11224 | Payment_IVR_PD_DISC_APPROVED |
| 162 | IX11225 | Payment_IVR_PD_MC_APPROVED |
| 163 | IX11226 | Payment_IVR_PD_VISA_APPROVED |
| 164 | IX11227 | Payment_IVR_PD_OT_APPROVED |
| 165 | IX11427 | Payment_EFT_ACH_ECP_APPROVED |
| 166 | IX11428 | Payment_EFT_CC_AMEX_APPROVED |
| 167 | IX11429 | Payment_EFT_CC_DISC_APPROVED |
| 168 | IX11430 | Payment_EFT_CC_MC_APPROVED |
| 169 | IX11431 | Payment_EFT_CC_VISA_APPROVED |
| 170 | IX11432 | Payment_EFT_CC_OT_APPROVED |
| 171 | IX11433 | Payment_EFT_PD_AMEX_APPROVED |
| 172 | IX11434 | Payment_EFT_PD_DISC_APPROVED |
| 173 | IX11435 | Payment_EFT_PD_MC_APPROVED |
| 174 | IX11436 | Payment_EFT_PD_VISA_APPROVED |
| 175 | IX11437 | Payment_EFT_PD_OT_APPROVED |
| 176 | IX11237 | Payment_ONE_ACH_ECP_APPROVED |
| 177 | IX11238 | Payment_ONE_CC_AMEX_APPROVED |
| 178 | IX11239 | Payment_ONE_CC_DISC_APPROVED |
| 179 | IX11240 | Payment_ONE_CC_MC_APPROVED |
| 180 | IX11241 | Payment_ONE_CC_VISA_APPROVED |
| 181 | IX11242 | Payment_ONE_CC_OT_APPROVED |
| 182 | IX11243 | Payment_ONE_PD_AMEX_APPROVED |
| 183 | IX11244 | Payment_ONE_PD_DISC_APPROVED |
| 184 | IX11245 | Payment_ONE_PD_MC_APPROVED |
| 185 | IX11246 | Payment_ONE_PD_VISA_APPROVED |
| 186 | IX11247 | Payment_ONE_PD_OT_APPROVED |
| 187 | IX11267 | Payment_VBS_ACH_ECP_APPROVED |
| 188 | IX11268 | Payment_VBS_CC_AMEX_APPROVED |
| 189 | IX11269 | Payment_VBS_CC_DISC_APPROVED |
| 190 | IX11270 | Payment_VBS_CC_MC_APPROVED |
| 191 | IX11271 | Payment_VBS_CC_VISA_APPROVED |
| 192 | IX11272 | Payment_VBS_CC_OT_APPROVED |
| 193 | IX11273 | Payment_VBS_PD_AMEX_APPROVED |
| 194 | IX11274 | Payment_VBS_PD_DISC_APPROVED |
| 195 | IX11275 | Payment_VBS_PD_MC_APPROVED |
| 196 | IX11276 | Payment_VBS_PD_VISA_APPROVED |
| 197 | IX11277 | Payment_VBS_PD_OT_APPROVED |
| 198 | IX11287 | Payment_CSR_ACH_ECP_APPROVED |
| 199 | IX11288 | Payment_CSR_CC_AMEX_APPROVED |
| 200 | IX11289 | Payment_CSR_CC_DISC_APPROVED |
| 201 | IX11290 | Payment_CSR_CC_MC_APPROVED |
| 202 | IX11291 | Payment_CSR_CC_VISA_APPROVED |
| 203 | IX11292 | Payment_CSR_CC_OT_APPROVED |
| 204 | IX11293 | Payment_CSR_PD_AMEX_APPROVED | 
| 205 | IX11294 | Payment_CSR_PD_DISC_APPROVED | 
| 206 | IX11295 | Payment_CSR_PD_MC_APPROVED | 
| 207 | IX11296 | Payment_CSR_PD_VISA_APPROVED | 
| 208 | IX11297 | Payment_CSR_PD_OT_APPROVED | 
