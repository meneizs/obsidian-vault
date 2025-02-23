---
tags:
  - Managment
category: Managment
type: Managment
---
---
--- start-multi-column: Header

### Notes to read:
``` dataview
TABLE
FROM "Daily Quick Note"
```

--- column-break ---


### Unttaged notes:
``` dataview
TABLE 
  file.tags AS "Tag",  
  category AS "Category", 
  type AS "Type", 
  file.date.mtime AS "Modified At"
FROM "vault"
WHERE (length(file.tags) = 0 OR length(type) = 0 OR length(category) = 0) AND file.name != "draw.excalidraw"
```


--- end-multi-column






--- start-multi-column: ID_o8cx
```column-settings
Number of Columns: 3
Largest Column: standard
Shadow: on
Border: enabled
```

### Tarefas profissionais

``` dataview
TASK 
FROM "vault"
WHERE due >= date(today) AND contains(string(category), "Profissional")
SORT due ASC
```


--- column-break ---

### Tarefas Pessoais

``` dataview
TASK 
FROM "vault"
WHERE due >= date(today) AND contains(string(category), "Pessoal")
SORT due ASC
```


--- column-break ---

### Tarefas out-of-date

``` dataview
TABLE 
  category AS "Category", 
  due as "Due date"
FROM "vault"
WHERE due < date(today) and due != null and file.tags = "Task"
SORT due ASC
```

--- end-multi-column

