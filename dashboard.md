# NSMT Wiki Dashboard

Live overview powered by Dataview. Updates automatically as pages change.

---

## Open Decisions

```dataview
TABLE status, tags
FROM "decisions"
WHERE status = "proposed"
SORT file.name ASC
```

## Equipment Needing Attention

```dataview
TABLE status, tags
FROM "broadcast/equipment"
WHERE status = "pending"
SORT file.name ASC
```

## All Projects

```dataview
TABLE status, tags
FROM "projects"
SORT title ASC
```

## Recent Events

```dataview
TABLE status, tags
FROM "broadcast/events"
SORT created DESC
```

## Broadcast Roles (Quick Reference)

```dataview
TABLE tags
FROM "broadcast/roles"
SORT title ASC
```

## All Runbooks

```dataview
TABLE tags
FROM "broadcast/runbooks"
SORT title ASC
```

## Systems Overview

```dataview
TABLE status, tags
FROM "systems"
SORT title ASC
```

## Design Systems

```dataview
TABLE status, tags
FROM "design"
SORT title ASC
```

## Pages by Tag

### Equipment Decisions Pending
```dataview
LIST
FROM ""
WHERE contains(tags, "baseline-decision")
```

### Firebase-Related
```dataview
LIST
FROM ""
WHERE contains(tags, "firebase")
```

### Broadcast Crew
```dataview
LIST
FROM ""
WHERE contains(tags, "crew")
```

---

## Wiki Stats

```dataview
TABLE length(file.inlinks) AS "Inbound Links", length(file.outlinks) AS "Outbound Links"
FROM ""
WHERE file.name != "index" AND file.name != "dashboard" AND file.name != "CLAUDE" AND file.name != "log"
SORT length(file.inlinks) DESC
LIMIT 10
```
