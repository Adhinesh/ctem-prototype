# CTEM Database & Asset Inventory 🛡️

A lightweight Continuous Threat Exposure Management (CTEM) prototype database built for PostgreSQL / Supabase, managed via a Python client.

## 🗄️ Database Tables (10-Table Schema)
- `assets` — Full IT asset inventory.
- `vulnerabilities` — CVE catalog with severity scores and exploit data.
- `open_ports` — Per-asset port state & service fingerprints.
- `dns_records` — DNS mapping and subdomain takeover risk tracking.
- `asset_changes` — Complete audit trail for any asset modification.
- `asset_logs` — Event stream (SIEM-lite) per asset.
- `scans` — Scan run history and metrics.
- `scan_snapshots` — Point-in-time security state captures.
- `asset_vulnerabilities` — Link table mapping CVEs to Assets with SLA tracking.
- `exposures` — Active CTEM threats mapped to business risk.

## 🚀 Getting Started

### 1. Database Setup
Copy the contents of `schema.sql` and run it in your PostgreSQL database or Supabase SQL Editor.

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Configuration
1. Copy `config.example.py` to `config.py`
2. Open `config.py` and replace the placeholder values with your actual Supabase URL and API Key.
*(Note: `config.py` is gitignored so you won't accidentally commit your secrets).*

### 4. Insert Sample Data
To populate the database with realistic CTEM sample data, run:
```bash
python insert_data.py
```
*(Need to reset the database? Run `python clear_data.py` before running the insert script again).*

### 5. Query the Data
To view your data nicely formatted in the terminal, run:
```bash
python queries.py
```
