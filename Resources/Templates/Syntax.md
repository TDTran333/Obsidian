Date now: <% tp.date.now() %> 

Date now with format: <% tp.date.now("Do MMMM YYYY") %> 

Last week: <% tp.date.now("dddd Do MMMM YYYY", -7) %> 

Today: <% tp.date.now("dddd Do MMMM YYYY, ddd") %>

Next week: <% tp.date.now("dddd Do MMMM YYYY", 7) %> 

Date tomorrow with format: <% tp.date.tomorrow("Do MMMM YYYY") %> 

Date yesterday with format: <% tp.date.yesterday("Do MMMM YYYY") %> 

File's title + 1 day: <% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>

File content: <% tp.file.content %>

File creation date: <% tp.file.creation_date() %>
File creation date with format: <% tp.file.creation_date("dddd Do MMMM YYYY HH:mm") %>

File Folder: <% tp.file.folder() %>
File Folder with relative path: <% tp.file.folder(true) %>

File include: <% tp.file.include("Templates/Template1") %>

File Last Modif Date: <% tp.file.last_modified_date() %>
File Last Modif Date with format: <% tp.file.last_modified_date("dddd Do MMMM YYYY HH:mm") %>

File Path: <% tp.file.path() %>
File Path with relative path: <% tp.file.path(true) %>

Adding a "2" to file's title: <% tp.file.rename(tp.file.title + "2") %>

File Selection: <% tp.file.selection() %>

File tags: <% tp.file.tags %>

File title: <% tp.file.title %>

Web Daily quote:  
<%~ tp.web.daily_quote() %>

Web Random picture: 
<%~ tp.web.random_picture() %>

Web Random picture with size: 
<%~ tp.web.random_picture("200x200") %>

Web random picture with size + query: 
<%~ tp.web.random_picture("200x200", "landscape,water") %>