---
date: 2024-10-24T22:24
tags:
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
#### list of commands
***
- `more` and `less` is a pagination commands
- `head` prints firs 10 rows of the result
- `tail` prints last 10 rows of the result
- `sort` sorts result
- `grep` for filtering
- `cut -d` for cutting the result by a specific character
- `tr` to replace specific character
- `column -t` for tabular view of the result
- 

#### pagers `more` and `less`
***
Pagers allow us to scroll through the file in an interactive view.

#### `head`
***
If we want to get only the first lines of the file, we can use the tool `head`

By default `head` prints the first ten lines of the given file or input

```bash
head /etc/passwd
```

#### `tail`
***
If we want to see the last pars of a file, we can use `tail`

By default `tail` will print last ten lines

```bash
tail /etc/passwd
```

#### `sort`
***
In order to sort the desired results numerically or alphabetically we can use `sort`

```bash
cat /etc/passwd | sort
```

```shell-session
Debian-snmp:x:111:109::/var/lib/snmp:/bin/false
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
_galera:x:100:65534::/nonexistent:/usr/sbin/nologin
_gophish:x:105:105::/var/lib/gophish:/usr/sbin/nologin
_gvm:x:121:122::/var/lib/openvas:/usr/sbin/nologin
_rpc:x:110:65534::/run/rpcbind:/usr/sbin/nologin
avahi:x:120:120:Avahi mDNS daemon,,,:/run/avahi-daemon:/usr/sbin/nologin
azura:x:1000:1000:azura,,,:/home/azura:/usr/bin/zsh
```

#### `grep`
***
More often, we will only search for specific results that contain patterns we have defined. One of the most used tools for this is `grep`

```bash
cat /etc/passwd | grep "/bin/bash"
```

```shell-session
root:x:0:0:root:/root:/bin/bash
mrb3n:x:1000:1000:mrb3n:/home/mrb3n:/bin/bash
```

Also we can exclude specific results. For this option `-v` is used. In the next example we’ll exclude all users who have the standard shell with the name `/bin/false` or `/bin/nologin`

```bash
cat /etc/passwd | grep -v "false\|nologin"
```

```bash-session
root:x:0:0:root:/root:/usr/bin/zsh
sync:x:4:65534:sync:/bin:/bin/sync
postgres:x:119:119:PostgreSQL administrator,,,:/var/lib/postgresql:/bin/bash
azura:x:1000:1000:azura,,,:/home/azura:/usr/bin/zsh
```

#### `cut`
***
Specific results with different characters may be separated as delimiters and show the words on a line in a specified position

One of the tools that can be used for this is `cut`

Therefore we use the option `-d` and set the delimiter to the `:` and define with the `-f` the position in the line we want to output

```bash
cat /etc/passwd | grep -v "false\|nologin" | cut -d":" -f1
```

```bash
root
sync
postgres
azura
```

#### `tr`
***
To replace certain characters, we can use `tr`

```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " "
```

```bash
root x 0 0 root /root /usr/bin/zsh
sync x 4 65534 sync /bin /bin/sync
postgres x 119 119 PostgreSQL administrator,,, /var/lib/postgresql /bin/bash
azura x 1000 1000 azura,,, /home/azura /usr/bin/zsh
```

#### `column`
***
Since search results can often have an unclear representation, we can use `column -t` to display such results in tabular form

```bash
cat /etc/passwd | grep "false\|nologin" | column -t
```

```bash
root      x  0     0      root        /root             /usr/bin/zsh         
sync      x  4     65534  sync        /bin              /bin/sync            
postgres  x  119   119    PostgreSQL  administrator,,,  /var/lib/postgresql  /bin/bash
azura     x  1000  1000   azura,,,    /home/azura       /usr/bin/zsh  
```

#### `awk`
***
As we have noticed, the line for the user “postgres” has too many columns. To keep it as simple as possible, the (g)`awk` programming is beneficial.

This allows us to display the first (`$1`) and last (`$NF`) results of the line

```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | column -t
```

```bash
root      /usr/bin/zsh
sync      /bin/sync
postgres  /bin/bash
azura     /usr/bin/zsh
```

#### `sed`
***
There will come moments when we want to change specific names in the whole file or specific output. 

One of the tools we can use for this called `sed`. One of the most common uses of this tool is substituting text. 

Here `sed` looks for patterns we have defined in the form of regular expression and replaces them with another pattern that we have also defined

Let us stick to the last result and say that we want to replace the word “bin” with “HTB”

```bash
cat /etc/passwd/ | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $NF}' | sed 's/bin/HTB/b'
```

- `s` flag stands for the substitute command
- then we specify `bin` as the pattern that we want to replace
- then we specify `HTB` as the pattern that we want to use to replace `bin`
- `g` flag stands for **replacing all matches**

```bash
root /usr/HTB/zsh
sync /HTB/sync
postgres /HTB/bash
azura /usr/HTB/zsh
```

#### `wc`
***
It will also be useful to know how many successful matches we have

For this purpose we can use `wc` with `-l` flag


#### tasks
***
1. A line with the username `cry0l1t3`.

```bash
cat /etc/passwd | grep "cry0l1t3"
```

2. The usernames.

```bash
cat /etc/passwd | tr ":" " " | awk '{print $1}'
```

3. The username `cry0l1t3` and his UID.

```bash
cat /etc/passwd | grep "cry0l1t3" | tr ":" " " | awk '{print $1, $3}'
```

4. The username `cry0l1t3` and his UID separated by a comma (`,`).

```bash
cat /etc/passwd | grep "cry0l1t3" | tr ":" " " | awk '{print $1, $3}' | tr " " ","
```

5. The username `cry0l1t3`, his UID, and the set shell separated by a comma (`,`).

```bash
cat /etc/passwd | grep "cry0l1t3" | tr ":" " " | awk '{print $1, $3, $NF}' | tr " " ","
```

7. All usernames with their UID and set shells separated by a comma (`,`).

```bash
cat /etc/passwd | tr ":" " " | awk '{print $1, $3, $NF}' | tr " " ","
```

8. All usernames with their UID and set shells separated by a comma (`,`) and exclude the ones that contain `nologin` or `false`.

```bash
cat /etc/passwd | grep -v "false\|nologin" | tr ":" " " | awk '{print $1, $3, $NF}' | tr " " ","
```

9. All usernames with their UID and set shells separated by a comma (`,`) and exclude the ones that contain `nologin` and count all lines of the filtered output.

```bash
cat /etc/passwd | grep -v "nologin" | tr ":" " " | awk '{print $1, $3, $NF}' | tr " " "," | wc -l
```

10. How many services are listening on the target system on all interfaces? (Not on localhost and IPv4 only)

```bash
netstat -tuln | grep -v "127.0.0\|tcp6" | grep "LISTEN" | wc -l
```

11. Determine what user the ProFTPd server is running under. Submit the username as the answer

```bash
 systemctl list-units --type=service | grep "proftpd"
 ps aux | grep "proftpd"
```

12. Use cURL from your Pwnbox (not the target machine) to obtain the source code of the "https://www.inlanefreight.com" website and filter all unique paths of that domain. Submit the number of these paths as the answer.

```bash
curl https://www.inlanefreight.com/ | grep -Po "https://www.inlanefreight.com/[^'\"]*" | sort -u 
```