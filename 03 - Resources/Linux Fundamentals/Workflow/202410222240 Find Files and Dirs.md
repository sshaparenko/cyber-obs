---
date: 2024-10-22T22:40
tags:
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
#### which
***
`which` returns the path to the file or link that should be executed. This allows us to determine if the specific programs, like `cURL` `netcat` `wget` `python` are available on the operating system. 

```bash
which python
```

```
/usr/bin/python
```

#### find
***
Another handy tool is `find`. Besides the function to find files and folders, this tool also contains function to filter the results.

We can use filter parameters like the size of the file or the date. We can also specify if we only search for files or directories

```bash
find <location> <options>
find / -type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null
```

| option                | description                                                                                                                                                                                                                                                                                                                                  |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `-type f`             | we define the type of the searched object. In this case `f` stands for `file`                                                                                                                                                                                                                                                                |
| `-name *.conf`        | With the `-name` we indicate the name of the file. The `*` stands for ‘all‘ and `.conf` is an extension                                                                                                                                                                                                                                      |
| `-user root`          | This option filter all files by the owner                                                                                                                                                                                                                                                                                                    |
| `-size 20k`           | We can then filter all the located files and specify that we only want to see the files that are larger than 20 KiB                                                                                                                                                                                                                          |
| `-newermt 2020-03-03` | With this option, we set the date. Only files newer than the specified date will be presented                                                                                                                                                                                                                                                |
| `-exec ls -al {} \;`  | `-exec` option executes the specified command on each file found by `find`.<br><br>`ls -al` is the command itself<br><br>`{}` is a placeholder that is replaced by `find` with the path to each file found<br><br>`;` is used to terminate the `exec` command. It needs `\` to prevent the shell from interpreting it as a special character |
| `2>/dev/null`         | This is a `STDERR` redirection to the `null device`. This device ensures that no errors are displayed in the terminal.<br><br># this redirection **should NOT** be an option for the `find` command                                                                                                                                          |
|                       |                                                                                                                                                                                                                                                                                                                                              |

#### locate
***
Command `locate` offers a quicker way to search through the system. In contrast to `find`, `locate` works with a local database that contains all information about the existing files and folders. 

We can update the database with the following command
```bash
sudo updatedb
```

If we now search for all the files with the “.conf“ extension, you will find that this search works faster then `find`

```bash
locate *.conf
```

However this tool does not have as many filter options that we can use.
