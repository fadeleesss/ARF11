---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags:
  - status/inbox
  - incantation
---
<%* 
const title = await tp.system.prompt("Note title");
await tp.file.rename(title);
-%>
# <% title %>
## ⚡ The Spark

> [!quote] Raw Idea
> <% tp.system.prompt("What is the core idea/spark?") %>

## 🔍 Context & Details


## 🔗 Connections
- Origin: [[<% tp.date.now("YYYY-MM-DD") %>]]
- Topic Hub: