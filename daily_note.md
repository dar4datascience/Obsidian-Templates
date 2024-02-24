---
date: <% tp.date.now("YYYY-MM-DD") %>
tema: dailynote
tags: [daily, note]
---

[[<% fileDate = moment(tp.file.title, 'YYYY-MM-DD').subtract(1, 'd').format('YYYY-MM-DD') %>|Yesterday]] | [[<%fileDate = moment(tp.file.title, 'YYYY-MM-DD').add(1, 'd').format('YYYY-MM-DD')%>|Tomorrow]] 

## Tasks of the Day

## Time Sheet Tracking

Split 8 working hours 

Learning:: 0  
Meetings:: 0  
Development:: 0  
????:: 0
????:: 0



## Follow up on

```dataviewjs
dv.taskList(dv.pages().file.tasks 
  .where(t => !t.completed)
  .where(t => t.text.includes("{{date:YYYY-MM-DD}}")))
```

## Reminders

- blab
- blab





