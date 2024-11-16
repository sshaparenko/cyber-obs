---
date: 2024-11-15T11:54
tags:
  - linux
---
A process can be in the following states:
- Running
- Waiting (for an event or system resource)
- Stopped
- Zombie (stopped but still has an entry in the process table)

Processes can be controlled using `kill`, `pkill`, `pgrep`, and `killall`

To interact with a process, we should send a signal to it. The most commonly used signals are:


| Signal | Description                                                                       |
| ------ | --------------------------------------------------------------------------------- |
| 1      | SIGHUP - This is sent to a process when the terminal that controls it is closed   |
| 2      | SIGINT - Sent when user press \[Ctrl\] + C in the terminal                        |
| 3      | SIGQUIT - Sent when a user press \[Ctrl\] + D to quit                             |
| 9      | SIGKILL - Immediately kill a process with no clean-up operations                  |
| 15     | SIGTERM - Program termination                                                     |
| 19     | SIGSTOP - Stop the program. It cannot be handled anymore                          |
| 20     | SIGTSTP - Sent when a user press \[Ctrl\] + Z to request for a service to suspend |
```bash
kill 9 <PID>
```