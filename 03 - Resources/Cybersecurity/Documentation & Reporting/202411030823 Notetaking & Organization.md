---
date: 2024-11-03T08:23
tags:
  - "#cybersecurity"
  - "#reporting"
cssclasses:
  - pen-green
  - page-grid
---
#### Login
***

It is essential that we log all scanning and attack attempts and keep raw tool output wherever possible. This will greatly help us come reporting time.

Trough out notes should be clear and extensive, we may miss something and having our logs to fallback can help us when either adding more evidence to a report or responding to a client question 

## It’s essential to keep track of exploitation attempts in case the client needs to correlate events later on.

This is especially useful for those instances in which we have little to no findings in your report.

In this case, we can write up a narrative of the types of testing performed, so the reader can understand the kinds of things they are adequately protected against 

#### TMUX
***

The `tmux` is an excellent choice for terminal login. First, we need to clone the Tmux Plugin Manager repo to our home  directory.

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Next, we create a `.tmux.config` file

```bash
touch .tmux.config
```

And write the next content

```bash
# List of plugins

set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-logging'
set -g history-limit 50000

# Initialize TMUX plugin manager (keep at bottom)
run '~/.tmux/plugins/tpm/tpm'
```


Then we need to start the tmux session

```bash
tmux new -s setup
```

Once in the session, we should execute the next command:

```bash
tmux source ~/.tmux.conf
```

Then we need to type \[Ctrl] + \[B] and \[Shift] + \[I] and the plugin will install

To start the logging in the current session, type \[Ctrl] + \[B] and \[Shift] + \[P] (if all went as planned, the bottom of the window will show that logging is enabled)

To stop logging, press \[Shift] + \[P]

#### TMUX screen capture
***

Another handy trick is the ability to take a screen capture of the current Tmux window or an individual pane.

Let’s say we’re working in split window mode:

```bash
[Ctrl] + [B] + [Shift] + [%]
```

We can then move from pane to pane by typing

```bash
[Ctrl] + [B] + [0]
```

If we attempt to copy/paste the output from one pane, we will grab data from the other pane along with it, which will look very messy and require cleanup.

We can avoid this by taking a screen capture as follows:
\[Ctrl] + \[B] and \[Alt] + \[P]




