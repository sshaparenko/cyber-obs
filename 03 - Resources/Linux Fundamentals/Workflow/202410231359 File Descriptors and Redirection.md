---
date: 2024-10-23T13:59
tags:
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
#### File Descriptors
***
By default, the first three file descriptors in Linux are:
- `STDIN 0`: Data Stream for Input
- `STDOUT 1`: Data Stream for Output
- `STDERR 2`: Data Stream for error occurring

#### Redirect `STDERR` to null device
***
If we run the next command, we’ll get a result among many errors

```bash
find /etc/ -name shadow 
```

```bash
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/etc/cni/net.d’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/etc/vpnc’: Permission denied
/etc/shadow
```

In order to exclude the error messages, we can redirect the `STDERR` to null device by specifying `2 > /dev/null`

```bash
find /etc/ -name shadow 2>/dev/null
```

```bash
/etc/shadow
```

#### Redirect `STDOUT` to a file
***
Instead of printing the result into console, we can write it into a file

```bash
find /etc/ -name shadow > file.txt 2 > /dev/null
```

```bash
cat file.txt
**************
/etc/shadow
```

#### Redirect `STDOUT` and append to a file
***
The default behavior of redirecting the `STDOUT` stands for <u>creating a new file</u>, if it’s not exists <u>or rewriting it</u>! 

But if we want to append data to a file, we should use `>>` instead of `>`

```bash
find /etc/ -name shadow 2>/dev/null 1>>output.txt
```

#### Redirect `STDOUT` and `STDERR` to a separate files
***
In order to redirect result and errors into different files, we can specify:
- `1 > output.txt`: to write `STDOUT` into a file `output.txt`
- `2 > err.txt`: to write `STDERR` into a file `err.txt`

```bash
find /etc/ -name shadow 2>err.txt 1>output.txt
```

#### Redirect `STDIN`
***
We also can redirect input source. For example, we can provide an input for the `cat` from a file

```bash
cat < input.txt
*************************
This is a data from input.txt
```

#### Redirect `STDIN` stream to a file
***
We can also use `<<` to add our standard input through a stream file. We can also use `EOF` function to define when the input will end.

```bash
cat << EOF > stream.txt
```

```bash
> Hack
> the
> box
> EOF
```

```bash
cat stream.txt
Hack
the
box
```

#### Pipes
***
Another way to redirect `STDOUT` is to use pipes (`|`)

These are useful when we want to use the `STDOUT` from one program to be processed by another

One of such programs could be `grep` which is used to to filter `STDOUT` according to the pattern. 

In this example we’ll use grep to filter results which will start with `ii` and with `-c` flag we will count the number of outputs

```bash
dpkg --list | grep -c '^ii'
```

We can also use `wc -l` to count the number of outputs
```bash
ls -la | wc -l
```
