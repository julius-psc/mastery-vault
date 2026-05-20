# Currently Learning

## Engineering

```dataview
TABLE WITHOUT ID
  file.link AS Concept,
  language AS Language,
  date_started AS Started
FROM "03_engineering/concepts"
WHERE status = "learning"
SORT date_started DESC
```

## Design

```dataview
TABLE WITHOUT ID
  file.link AS Concept,
  topic AS Topic,
  date_started AS Started
FROM "04_design/concepts"
WHERE status = "learning"
SORT date_started DESC
```

## Stuck

```dataview
LIST
FROM #status/stuck
SORT file.mtime DESC
```