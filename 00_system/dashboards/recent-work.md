# Recent Work

## Last 7 days of daily logs

```dataview
LIST
FROM "01_daily"
WHERE date >= date(today) - dur(7 days)
SORT date DESC
```

## Recent dissections

```dataview
TABLE WITHOUT ID
  file.link AS Entry,
  product AS Product,
  date AS Date
FROM "04_design/library"
SORT date DESC
LIMIT 10
```

## Recent motion recreations

```dataview
TABLE WITHOUT ID
  file.link AS Recreation,
  tool AS Tool,
  date AS Date
FROM "06_motion/recreations"
SORT date DESC
LIMIT 10
```

## Recent illustration studies

```dataview
TABLE WITHOUT ID
  file.link AS Study,
  tool AS Tool,
  phase AS Phase,
  date AS Date
FROM "05_illustration/studies"
SORT date DESC
LIMIT 10
```

## All realizations

```dataview
LIST
FROM #realization
SORT file.mtime DESC
LIMIT 20
```