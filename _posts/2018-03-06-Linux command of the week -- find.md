---
layout: post
title: "Linux command of the week: find"
author: Roland Brand
published: true
---

You certainly know the little search bar on top of your file browser -- Finder on a Mac or Explorer if 
you're on Windows. You just enter your search term and hit enter, and maybe refine your search with 
filters. Did you know the same thing also exists on the Linux or Mac command line? Meet the __find__ command.

## Basics
Find is one of the more sophisticated commands. Note the manual is quite lengthy and can be 
viewed on `man find`.

To find something, you just need to type `find` followed by a specification what you want to find.
Easy, right?

Following are some examples:

`find -type f -name '*.hs'` Finds all Haskell files in your current directory and lists them by full
path in the command output.

`find -type f -name '*.hs' ./stack` Does the same as the above command, but only looks inside the
_stack_ directory.

By intuition, I always run into the mistake of wanting to type `find WHAT` (without the `-name`), 
but the basic format is `find [WHERE] WHAT`, 
_WHERE_ being a path (and optional), _WHAT_ being the filter options where you usually set `-name` and other
filters.
The closest thing to a search in Windows explorer where you type e.g. `strawberries` would be:

`find -name '*strawberries*'`. This finds all files and directories inside your home directory that contain
the word strawberries.

> Caution: find on a Mac is not 100% compatible with find on Linux. Most notably you always have to
> provide a directory to search in on a Mac. On Linux, the current directory is assumed by default.

## Combining commands
A fine example of the Unix philosophy of chaining together small tools: _find_ also has an 
`-exec` 
option
allowing to further process the result set, e.g. search for contents _inside_ the files with `grep` or
delete the files found with `rm`. For instance, 

`find -name '*~.jpg' -exec rm {} \;` 

finds all JPG files
and deletes them.

## But why?
Why bother with memorising a picky syntax when you have a more fuzzy search bar available with easy 
to use filter facets? 
On the one hand, in a DevOps context it is quite often that you only have access to a system by _SSH_.
Or increasingly, the same access to _Docker Containers_, where you also just have the command line to
inspect them. This is where an intuitive grasp of the find command can become very handy.

## But Windows search is way faster..
That might be true, depending on what you last changed. That is because _find_ always works directly
on the file system, while Windows search is keeping a search index (which needs to be updated regularly in a 
background task). 

The same is without difficulty possible on the command line, if you use `locate` instead
of _find_. _Locate_ is not installed by default on all distributions, and it is not always sensible to use it.
On a production web server for instance, you obviously don't want a search indexing process to slow down
your machine.