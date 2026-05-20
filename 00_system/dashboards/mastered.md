# Mastered Concepts

## Engineering

```dataview
TABLE WITHOUT ID
  file.link AS Concept,
  language AS Language,
  date_mastered AS Mastered
FROM "03_engineering/concepts"
WHERE status = "mastered"
SORT date_mastered DESC
```

## Design

```dataview
TABLE WITHOUT ID
  file.link AS Concept,
  topic AS Topic,
  date_mastered AS Mastered
FROM "04_design/concepts"
WHERE status = "mastered"
SORT date_mastered DESC
```

## Total count

```dataview
TABLE WITHOUT ID
  length(rows) AS Count
FROM "03_engineering/concepts" OR "04_design/concepts"
WHERE status = "mastered"
GROUP BY true
```