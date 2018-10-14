---
layout: post
title: "Linux command of the week: tail"
author: Roland Brand
published: true
---

I still remember the first time I wanted to look up what made crash my application in a server log.
It was a document of a few MB, nothing alarming so far since word documents at that time could easily be
the size of several dozen MB. But scrolling to the end of the logfile seemed impossible, it just took ages...

That was my first contact with the concept of buffering files instead of reading them into memory in one
chunk. For the given example, I used a really simple editor without buffering (it might have been _notepad_).
Scrolling became a discrete-time process with a half minute step size. I never reached the end of the file
(which is usually where the bacon is in logfiles; you want to check what made your system break a few minutes ago).

The introductory setting is the principal use case for the `tail` command. It just reads in the last few
lines of a (usually very large) file to be output in _stdout_, without filling all your memory with the lines
you don't need. There is also the pendant from the other end of the file, `head`.
> Think of your file as a very long snake of characters on your disk. `head` and `tail` are literally
cutting of the head or tail of this snake.

By default, `tail` fetches the 10 last lines of the file, a number that can be overridden by calling head
with the `-n` option, e.g. `tail -n 15 /etc/hosts` will output the last 15 lines of your hostsfile.

As with all unix commands, you can easily redirect the output of the tail command into a file, e.g.
`tail -n 15 /etc/hosts > /tmp/tmp_hoststail.txt` to save the output of the previous example into a temporary
file. Or you could pass the output through a pipe to `tac`, 
which outputs the lines in reverse order, so you can see the most
recent entry on top: `tail -n 15 /etc/hosts | tac`. 
You might have noticed by the way, that `tac` is `cat` spelled backwards.