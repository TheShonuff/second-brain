---
creation date: <% tp.file.creation_date() %>
---
# <%tp.file.title%>
<<  [[<% moment(tp.file.title,'MM-DD-YYYY-dddd').add(-1,'days').format('MM-DD-YYYY-dddd')%>|Previous Day ]] | <% moment(tp.file.title,'MM-DD-YYYY').format("YYYY") %> -W<% moment(tp.file.title,"MM-DD-YYYY").add(-1,'days').week() %> | [[<% moment(tp.file.title,'MM-DD-YYYY-dddd').add(1,'days').format('MM-DD-YYYY-dddd') %>]] >>

---

# To Do Today
### Recurring Tasks
```tasks
starts <% tp.date.now() %>
is recurring
not done
hide task count
hide backlinks 
short mode
```
### Tasks
- [ ]   

## Follow-up
```dataview
List from #investigate where file.name != "Investigation Template"

```

---
# Fleeting Notes
- <% tp.file.cursor() %>

---
# Introspection

### What did you learn today?
**speki**::

---
### Code Warrior Thoughts
**CodingPractice**:: 


---
### VIM Training log
**vim_log**:: 


---
### Education 
**Udemy**::

**School**::