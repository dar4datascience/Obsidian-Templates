# Obsidian-Templates

Check list of common templates for vaults to align yaml

- [x] Daily Note
- [x] Weekly Note
    - [x] Weekly Timesheet
- [x] Meeting Note
- [x] Project Note
- [ ] People Note


- Calculations like below for building timesheet 

```dataview
TABLE
		sum(rows.PhonePickups) as total
	,	length(rows.PhonePickups) as count
	,	sum(rows.PhonePickups) / length(rows.PhonePickups) as avg
	,	min(rows.Date) as min
	,	max(rows.Date) as max

FROM
		"DV"
GROUP BY
		date(Date).year + "-" + date(Date).month as date
WHERE
		rows.date
```