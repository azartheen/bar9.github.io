---
layout: post
title: "Linux command of the week: scp"
author: Roland Brand
published: true
---

Even if you are not familiar with scp yet, you might have encountered WinSCP, especially if you use Windows.
This file transfer client among other protocols works with the scp protocol, a secure file transfer protocol over SSH.

Scp stands for secure copy, and is available on most linux machines, enabling you to copy files from or to
any host you are able to reach with an ssh connection. Authorisation is exactly the same as with SSH,
by a unix user usually either with a password or an RSA key.

You should not depend any installed GUI programs however. The scp shell command is really easy to memorise,
and if you even casually work in a DevOps environment, it is well worth doing so. The `scp` command
 even allows you to orchestrate from a remote host the transfer of files.

The basic syntax of scp is as simple as 

```scp user@sourcehost:sourcedir user@targethost:targetdir```, 

so always from source to target,
which is the intuitive order (and the same as with the 'little brother' of `scp`, `cp`). The triple `user@host:directory` is then basically all you have to memorize.
`directory` can also be a single file. Usually one of source or target is your localhost, so you can omit
`user@host` (and the colon) on that side. The other (remote) side is usually just an IP address. 
If you happen to use a host often, you can alias it in your `/etc/hosts` file with an easy-to-memorise name.

While globbing (wildcard filenames with `*`) is technically possible, I wouldn't recommend it since there
are lots of mistakes to be made with escaping as soon as several machines are involved. Try organizing your
files into copy-friendly directories (or `tar` archives) instead and just `scp` those.

While `scp` is a universal tool and happens to be incredibly useful from time to time, memorising the
syntax has further benefits. 
Modern container tools such as Docker with the `docker cp` command or cloud hosting tools such as
Google Compute Engine with the `gcloud compute copy-files` have the exact same syntax (with container 
or instance names instead of hostnames).

Scp is typically not the fastest means of file transfer. If you have numerous files to transfer, packing
them into an archive beforehand significantly speeds up the process.

Have fun copying (securely)!