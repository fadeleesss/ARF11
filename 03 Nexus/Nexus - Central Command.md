---
created: 2026-10-09 10:54
filter_year:
filter_project:
filter_team:
tags:
  - nexus
---
# 🧭 Central Command

> *"One mirror to view all realms, one locus to govern all threads."*

---

## 🏛️ Sanctum Protocols & Architecture
*Foundational vault specifications, meta-lore, and grimoire mechanics.*
```dataview
TABLE WITHOUT ID
  year AS "Year",
  project AS "Project",
  team AS "Team",
  operation AS "Operation",
  status AS "Status",
  file.link AS "Protocol Note",
  file.mtime AS "Last Attuned"
FROM "02 Lore"
WHERE contains(lower(string(project)), "grand grimoire") OR contains(file.tags, "#meta")
SORT year DESC
```
## 💡 Master Lore Observatory

_Automated index of all permanent knowledge across teams, projects, operations, and eras._

```dataview
TABLE WITHOUT ID
  year AS "Year",
  project AS "Project",
  team AS "Team",
  operation AS "Operation",
  status AS "Status",
  file.link AS "Lore Files",
  file.mtime AS "Last Attuned"
FROM "02 Lore"
WHERE 
  !contains(lower(string(project)), "grand grimoire") AND 
  !contains(file.tags, "#meta") AND
  (!this.filter_year OR year = this.filter_year) AND
  (!this.filter_team OR contains(lower(string(team)), lower(this.filter_team))) AND
  (!this.filter_project OR contains(lower(string(project)), lower(this.filter_project)))
SORT 
  year DESC,
  project ASC,
  team ASC,
  operation ASC
  ```