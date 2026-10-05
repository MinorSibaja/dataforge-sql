# DataForge SQL 🚀

> High-performance, 100% client-side streaming CSV/TSV to SQL converter with multi-dialect support and automated DDL type inference.

Live Tool: **[https://dataforgesql.com](https://dataforgesql.com)**

---

## 🔒 Zero-Knowledge Privacy Architecture
DataForge SQL operates entirely in the browser memory using HTML5 Web Workers and streams. **Zero bytes are transmitted over the network.** Your datasets, financial ledgers, and PII never leave your local CPU, inherently aligning with GDPR and HIPAA data protection compliance.

## ✨ Core Features
- **Streaming Ingestion:** Parses multi-gigabyte datasets without crashing the browser's UI thread via 4MB chunk processing.
- **Cross-Engine Dialect Matrix:** Native syntax formatting for:
  - **PostgreSQL:** Handles parameter bounds and purges null bytes (`\0`).
  - **MySQL:** Backtick escaping, custom backslash handling, and `max_allowed_packet` batch thresholds.
  - **Microsoft SQL Server (T-SQL):** Strictly enforces the 1,000-row table value constructor limit (**Msg 10738 prevention**).
  - **SQLite:** Strict DDL normalization and variable threshold compliance.
- **Dynamic Type Widening:** Automatically infers boolean, integer, bigint, numeric, timestamp, and varchar schemas from the first 1,000 rows while dynamically widening types if heterogeneous data appears later in the stream.
- **Direct Disk Streaming:** Utilizes the File System Access API (`showSaveFilePicker`) in Chromium-based browsers, with native partitioned Blob fallbacks for WebKit (iOS Safari) to prevent Jetsam memory kills.

## 🛠 Tech Stack
- Vanilla ES6+ JavaScript
- PapaParse v5.4.1 (Web Worker isolated)
- Native File System Access API
- Hosted at the edge via Cloudflare Pages ($0 compute footprint)

## 📄 License
MIT License - Open for developers and commercial teams.
