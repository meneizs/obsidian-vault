 -  [ ] Nome da tarefa
	[Task:: [[ <% "vault/Tasks/" + tp.file.folder(true).split("/")[2] + "/" + tp.file.title + "/" + tp.file.selection() %>]] ]
	[due:: <% tp.date.tomorrow() %>]
	[project:: <% tp.file.title %>]
	[category:: [[<% tp.file.folder(true) %>|<% tp.file.folder(true).split("/")[2] %>]]]
	[type:: [[<% tp.file.folder(true) %>|<% tp.file.folder(true).split("/")[3] %>]]]
	[topic:: [[<% tp.file.folder(true) %>|<% tp.file.folder(true).split("/")[4] %>]]]
