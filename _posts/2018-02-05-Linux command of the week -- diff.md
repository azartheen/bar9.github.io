---
layout: post
title: "Linux command of the week: diff"
author: Roland Brand
published: true
---

Have you ever come to the situation where you needed to quickly verify if two files are the same
or not? 
Chances are you already do this every day inside your IDE when checking the changes for a commit.

But what about on a server? 
Maybe you have deployed something but are not sure whether your deployment path is working. 
One tool to verify is `diff`.

## The diff command
-----

Diff takes two arguments, which are usually file paths, e.g.
`diff /etc/mysql/my.cnf /etc/my.cnf.dpkg-dist` to compare
your current MySQL config to the packaged defaults.

The output of the diff command is empty, if the files are identical. Otherwise a very 
specialized output format is used for outputting all differences. Look at the output of our
example command:

```100,101c87,88
< server-id         = 100
< log_bin           = /var/log/mysql/mysql-bin.log
---
> #server-id        = 1
> #log_bin          = /var/log/mysql/mysql-bin.log
...
```

I advise you try to get familiar with this format (in order to be able to read it). 
You will likely come across it when you have to merge with git on a command line, without the help
of a merge tool (although underneath the GUI these tools also work with this format). 

Also in some projects with a bit more ancient tooling, the diff format is used to distribute
patches, which can be reviewed e.g. inside a discussion thread. This has roughly the same 
purpose as a pull request, and is still used in some parts of the Drupal development community.