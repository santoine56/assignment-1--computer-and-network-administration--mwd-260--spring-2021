# Spring 2020 Computer and Network Administration — Assignment 1

* **Do not edit this file.**  
* **Do not start this project until you have read these instructions carefully.**

---

## Before You Begin
1. Log in to GitHub.
2. Fork this repo(sitory). See [this video](http://code-warrior.github.io/tutorials/git/github/forking-and-cloning-at-the-github-web-site/) on how to carry out this step and step `3`.
3. Clone your fork, using either the web site or the GitHub Desktop client.
4. Checkout your personalized branch, the one with your name and GitHub user handle.

---

## Directions
All your answers must be included in the fenced region marked by back ticks and the word `bash`.

---

## Due Date
⏰ **Tuesday, 3 March 2020, at 11:59 PM. At that time, the repo will be closed and will not accept any more submissions. 🚫 _No late work will be accepted._**

---

## Submission
Issue a pull request back into the original repo, the one from which your forked was created, before the deadline. [Look at these videos](http://code-warrior.github.io/tutorials/git/github/) for help on how to do so.

**Note**: This assignment may *only* be submitted via GitHub. 🚫 **_No other form of submission will be accepted_**.

---

## / 1
Errors, access events, and system logs in Linux are kept in a pseudo-filesystem that is retained in memory, not non-volatile storage, and is designed for system admins. Write a command that monitors and updates in real time system changes, such as USB connections. (**25pts**)

```bash
tail -f /var/log/syslog
```

---

## / 2
Default bash profile files are sourced from multiple directories in the Linux filesystem. Locate the file that has the starter aliases and add an alias to the `rm` and `mv` commands that force interaction: `-i`. Then, using your own name, create a non-admin user and use the following algorithm: `first-name--last-name`. (**Note the double dashes**.) Log in to the system as this new user, launch a Terminal, then run the command `alias`. Look for your new aliases. Once you’ve verified that it worked, include the absolute path to the file, including the file itself below. Then copy 12 lines from that file: The 5 lines that precede the line where you made the change, the line where you made the change, and the 5 lines that follow the line where you made the changes. (**25pts**)

```
/etc/skel/
```

```bash
# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias rm='rm -i' # Added by Roy Vanegas on 3 March 2020
    alias mv='mv -i' # Added by Roy Vanegas on 3 March 2020
    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi
```

---

## / 3
In Linux, the `swapper_process`, created by the `start_kernel` function, in Linux has a PID `0`. It, in turn, spawns the `init`ial process with PID `1`. Recall that processes in Linux get a PID that is represented by a pseudo-filesystem in Linux. Write a command, or commands, that produces the following output in relation to PID `1`. (**25pts**)

```
State: S (sleeping)
```

**Hint**: You may need to pipe the output of one command into another.

```bash
more /proc/1/status | grep State
```

or
```bash
more /proc/1/status | grep -i state
```

---

## / 4
The `du` command will output disk, or file space, usage. Write a variant of the `du` command that outputs the following when run from your home folder. (**25pts**)

```
4.6M    Desktop
4.0K    Documents
4.0K    Downloads
4.0K    Music
4.0K    Pictures
4.0K    Public
12K     sketchbook
268K    snap
4.0K    Templates
4.0K    Videos
4.9M    total
```

```bash
```
