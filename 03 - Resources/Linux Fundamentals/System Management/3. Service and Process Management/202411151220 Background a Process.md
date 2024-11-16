---
date: 2024-11-15T12:20
tags:
  - linux
---
Sometimes it will be necessary to put the scan or process we just started in the background to continue using the current session to interact with the system or restart other processes.

To do this, we can suspend a service with \[Ctrl\] + Z

```bash
$ sudo python3 -m http.server 80
Serving HTTP on 0.0.0.0 port 80 (http://0.0.0.0:80/) ...
^Z
[1]+  Stopped                 sudo python3 -m http.server 80
```

We can use command `jobs` to see all the background jobs

```bash
$ jobs
[1]+  Stopped                 sudo python3 -m http.server 80
```

Now, to send this process to a background, use command `bg`

```bash
$ bg
[1]+ sudo python3 -m http.server 80 &

$jobs
[1]+  Running                 sudo python3 -m http.server 80 &
```

To bring this job back, use `fg <JOB_ID>`

```bash
$ fg 1
sudo python3 -m http.server 80
```
