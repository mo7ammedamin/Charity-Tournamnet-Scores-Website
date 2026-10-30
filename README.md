# ISoc Charity Tournament – scores site

Live site: https://YOUR-USERNAME.github.io/YOUR-REPO/

The site has three tabs: **Tables**, **Results** and **Fixtures**. Everything comes from two files:

| File | What it holds |
|---|---|
| `teams.csv` | Every team in every league (so teams with 0 games still show in the table) |
| `matches.csv` | Every match – upcoming **and** finished |

League tables are calculated automatically from `matches.csv`. You never edit W/D/L by hand.

## Columns in matches.csv

```
date,time,league,stage,team1,score1,team2,score2,venue,note
```

- **date**: `YYYY-MM-DD` (e.g. `2026-11-07`), or blank for "Date TBC"
- **time**: `HH:MM` 24-hour (e.g. `15:30`), or blank
- **league**: must match the league name in `teams.csv` (e.g. `Football`, `Futsal`)
- **stage**: `Group` counts toward the table. Anything else (`Semi-final`, `Final`) only shows in Results/Fixtures
- **score1 / score2**: leave **both blank** for a fixture, fill **both in** for a result
- **venue**, **note**: optional (e.g. `Field 1`, `Eagles win 4-3 on penalties`)

## Adding a fixture

Add a line with the scores blank:

```
2026-11-07,15:00,Futsal,Group,Atlas,,Mechamen,,Court A,
```

## Recording a result

Find the fixture line and type in the two scores:

```
2026-11-07,15:00,Futsal,Group,Atlas,3,Mechamen,2,Court A,
```

It moves from Fixtures to Results and the table updates by itself.

## How to edit on GitHub (phone or laptop)

1. Open the repo on github.com and click `matches.csv`
2. Click the ✏️ pencil icon
3. Edit the line, then click **Commit changes**
4. Wait about 1 minute, then refresh the site

## Common mistakes

- Commas inside a name: wrap it in quotes, e.g. `"Smith, Jones & Co"`
- Team names must be spelled the same every time (capital letters don't matter)
- Don't open the CSV in Excel and re-save it: Excel often changes the date format. Edit on GitHub instead.
- If a line is wrong, the site shows an orange "Skipped invalid line" warning with the line number.
