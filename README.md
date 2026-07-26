# Luxembourg Administrative Divisions / Luxembourg



## Overview

| Item | Details |
|------|---------|
| Canton | 12 |
| Commune | 102 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-07-26 |
| Website | [openadmindata.org/lu](https://openadmindata.org/lu/) |
| API | [openadmindata.org/api/lu](https://openadmindata.org/api/lu/) |

## Browse by Canton

| # | Canton | Communes | Link |
|---|----|----|------|
| 1 | Diekirch | 0 | [Browse](divisions/diekirch-lu01/) |
| 2 | Grevenmacher | 7 | [Browse](divisions/grevenmacher-lu02/) |
| 3 | Luxembourg | 5 | [Browse](divisions/luxembourg-lu03/) |
| 4 | Wiltz | 9 | [Browse](divisions/wiltz-lu04/) |
| 5 | Redange | 10 | [Browse](divisions/redange-lu05/) |
| 6 | Capellen | 9 | [Browse](divisions/capellen-lu06/) |
| 7 | Esch-sur-Alzette | 14 | [Browse](divisions/esch-sur-alzette-lu07/) |
| 8 | Mersch | 14 | [Browse](divisions/mersch-lu08/) |
| 9 | Remich | 14 | [Browse](divisions/remich-lu09/) |
| 10 | Echternach | 8 | [Browse](divisions/echternach-lu10/) |
| 11 | Vianden | 7 | [Browse](divisions/vianden-lu11/) |
| 12 | Clervaux | 5 | [Browse](divisions/clervaux-lu12/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-canton.json](data/all-canton.json) | JSON | All 12 canton records |
| [all-commune.json](data/all-commune.json) | JSON | All 102 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-canton.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['commune']} communes")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-canton.json", "utf-8"));
console.log(`Total: ${data.length} cantons`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=canton, 2=commune |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{canton-slug}/
```

Communes are listed inline in each canton's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-canton links
- [Per-canton data](docs/llms-full/) — Full data by canton

## Citation

```
Luxembourg Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/luxembourg-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
