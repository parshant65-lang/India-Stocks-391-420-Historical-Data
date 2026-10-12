# India-Stocks-391-420-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 391 to 420)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-391-420-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (391 to 420)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 391 | `LTFOODS` | LT Foods Ltd. | `LTFOODS.NS` |
| 392 | `LEMONTREE` | Lemon Tree Hotels Ltd. | `LEMONTREE.NS` |
| 393 | `MMTC` | MMTC Ltd. | `MMTC.NS` |
| 394 | `MTARTECH` | MTAR Technologies Ltd. | `MTARTECH.NS` |
| 395 | `MGL` | Mahanagar Gas Ltd. | `MGL.NS` |
| 396 | `M&MFIN` | Mahindra & Mahindra Financial Services Ltd. | `M&MFIN.NS` |
| 397 | `M&M` | Mahindra & Mahindra Ltd. | `M&M.NS` |
| 398 | `MANAPPURAM` | Manappuram Finance Ltd. | `MANAPPURAM.NS` |
| 399 | `MRPL` | Mangalore Refinery & Petrochemicals Ltd. | `MRPL.NS` |
| 400 | `MINDACORP` | Minda Corporation Ltd. | `MINDACORP.NS` |
| 401 | `MSUMI` | Motherson Sumi Wiring India Ltd. | `MSUMI.NS` |
| 402 | `NATCOPHARM` | NATCO Pharma Ltd. | `NATCOPHARM.NS` |
| 403 | `NBCC` | NBCC (India) Ltd. | `NBCC.NS` |
| 404 | `NCC` | NCC Ltd. | `NCC.NS` |
| 405 | `NSLNISP` | NMDC Steel Ltd. | `NSLNISP.NS` |
| 406 | `NAVA` | Nava Ltd. | `NAVA.NS` |
| 407 | `NAVINFLUOR` | Navin Fluorine International Ltd. | `NAVINFLUOR.NS` |
| 408 | `NETWEB` | Netweb Technologies India Ltd. | `NETWEB.NS` |
| 409 | `NEULANDLAB` | Neuland Laboratories Ltd. | `NEULANDLAB.NS` |
| 410 | `NAM-INDIA` | Nippon Life India Asset Management Ltd. | `NAM-INDIA.NS` |
| 411 | `NUVAMA` | Nuvama Wealth Management Ltd. | `NUVAMA.NS` |
| 412 | `NUVOCO` | Nuvoco Vistas Corporation Ltd. | `NUVOCO.NS` |
| 413 | `OLAELEC` | Ola Electric Mobility Ltd. | `OLAELEC.NS` |
| 414 | `OLECTRA` | Olectra Greentech Ltd. | `OLECTRA.NS` |
| 415 | `ONESOURCE` | Onesource Specialty Pharma Ltd. | `ONESOURCE.NS` |
| 416 | `PCBL` | PCBL Chemical Ltd. | `PCBL.NS` |
| 417 | `PGEL` | PG Electroplast Ltd. | `PGEL.NS` |
| 418 | `PNBHOUSING` | PNB Housing Finance Ltd. | `PNBHOUSING.NS` |
| 419 | `PTCIL` | PTC Industries Ltd. | `PTCIL.NS` |
| 420 | `PVRINOX` | PVR INOX Ltd. | `PVRINOX.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream LTFOODS 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-391-420-Historical-Data/main/LTFOODS/1m/2026/10/LTFOODS_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
