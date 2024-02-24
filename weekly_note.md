---
date: <% tp.date.now("YYYY-MM-DD") %>
week: <% tp.date.now().week() %>
tema: weeklynote
tags: [weekly, note]
---

[[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(7, 'd').format('YYYY-MM-DD') %>|Previous Week]] | [[<%fileDate = moment(tp.file.title, 'YYYY-MM-DD').add(7, 'd').format('YYYY-MM-DD')%>|Next Week]] 

## Tasks of Week <% tp.date.now().week() %>


```dataviewjs
dv.taskList(dv.pages().file.tasks 
  .where(t => !t.completed)
  .where(t => {
    const taskDate = moment(t.dataview.file.name, 'YYYY-MM-DD');
    return taskDate.week() === tp.date.now().week();
  })
)

```

## Time Sheet Tracking

Total working hours for the week: 40 (adjust as needed)

```dataview
TABLE
    sum(rows."Learning") as LearningTotal
    , sum(rows."Meetings") as MeetingsTotal
    , sum(rows."Development") as DevelopmentTotal
    , sum(rows."Miscellaneous") as MiscellaneousTotal
FROM
    "/Daily Notes"
WHERE
    date(rows.Date).week === tp.date.now().week()
```


## Reminders

- Reminder 1
- Reminder 2
