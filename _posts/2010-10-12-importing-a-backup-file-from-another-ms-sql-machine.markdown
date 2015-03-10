---
layout: post
status: publish
published: true
title: Importing a backup file from another MS SQL machine.
author:
  display_name: Toby
  login: admin
  email: toby.osbourn@googlemail.com
  url: ''
author_login: admin
author_email: toby.osbourn@googlemail.com
wordpress_id: 335
wordpress_url: http://www.tosbourn.com/?p=335
date: '2010-10-12 11:26:04 +0100'
date_gmt: '2010-10-12 10:26:04 +0100'
categories:
- Development Help
tags:
- MS SQL
- Backups
comments: []
---
<p>Today I had to do an import from a .BAK file created on a completely different machine than what I had to restore it onto.  It took me more than 5 minutes to find the complete solution online so I will post the code I ran here in the hope that someone else benefits from it.</p>
<p><code>ALTER DATABASE yourDatabase SET single_user WITH ROLLBACK IMMEDIATE<br />
GO<br />
USE master<br />
GO<br />
RESTORE FILELISTONLY<br />
FROM DISK = N'c:\path\to\backup.BAK'<br />
RESTORE DATABASE yourDatabase<br />
FROM DISK = N'c:\path\to\backup.BAK'<br />
WITH RECOVERY,<br />
MOVE 'yourDatabase_Data' TO 'C:\Program Files\Microsoft SQL Server\MSSQL\data\yourDatabase_Data.mdf',<br />
MOVE 'yourDatabase_Log' TO 'C:\Program Files\Microsoft SQL Server\MSSQL\data\yourDatabase_Log.ldf', REPLACE<br />
GO<br />
ALTER DATABASE yourDatabase SET MULTI_USER<br />
GO<br />
</code></p>
<p>What this does is first of all kicks everyone off your database, if it is in use the restore script will not run correctly. Then it runs the update, since the location of the files will have changes you need those MOVE commands in there. Finally it sets you database back to being multi user again so people can connect and use your updated tables.</p>
