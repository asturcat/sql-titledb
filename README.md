# sql-titledb

Automated daily mirror of Nintendo Switch `titledb.db.gz` in SQLite format, built from [`borntohonk/titledb`](https://github.com/borntohonk/titledb) using [`ivaano/titledbConverter`](https://github.com/ivaano/titledbConverter).

## Overview

Since `blawar/titledb` stopped receiving regular updates, this repository automatically compiles and publishes an up-to-date `titledb.db.gz` and its MD5 `version` checksum every day via GitHub Actions.

## Upstream Sources

- **TitleDB JSON source:** [`borntohonk/titledb`](https://github.com/borntohonk/titledb) (`master` branch)
- **SQLite converter:** [`ivaano/titledbConverter`](https://github.com/ivaano/titledbConverter)

## Files

- `titledb.db.gz` — Gzip-compressed SQLite database containing title metadata, versions, updates, and DLCs.
- `version` — 32-character MD5 hash of `titledb.db.gz` used for change detection.

## Schedule

The GitHub Actions workflow (`.github/workflows/update-titledb.yml`) runs automatically every day at **21:00 UTC** and can also be triggered manually via `workflow_dispatch`.

## Usage

Point your compatible tool (such as **NsxLibraryManager** or **GamesHub Switch**) to the raw URLs of this repository:

- **Repository / Version URL:** `https://github.com/asturcat/sql-titledb/raw/refs/heads/main/version`
- **Database URL:** `https://github.com/asturcat/sql-titledb/raw/refs/heads/main/titledb.db.gz`

For `NsxLibraryManager`, set `SqlTitleDbRepository` in `config.json` to:

```text
https://github.com/asturcat/sql-titledb
```
