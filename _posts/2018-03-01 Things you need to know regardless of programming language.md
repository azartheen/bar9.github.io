---
layout: post
title: "10 things you need to know regardless of programming language"
author: Roland Brand
published: false
---

A lot of people are taking up programming nowadays, either because they're young and it's
one of the options to learn for them, or because of the opportunities in a vastly growing
sector. Programming beginners are confronted with the difficult choice of their first language. 

First of all:
Don't listen to the camps of a "superior" language and to flame wars. It does not matter that much.
There are more important things to focus on. Any energy is wasted partaking in a 'camp'.
Here's a list of things you will need to learn regardless of language.
They all are not coupled to any language, so they could even be learned before learning to program.

## 1.Version control
Version control allows projects to stretch over time and many people and teams to collaborate
_without_ people overwriting stuff of the others or not being able to find old work. __git__ is
a no unquestioned standard in that respect. Learning __git__ is a top priority for anyone new
to programming. It takes some time and will accompany you every day.

## 2.Versioning
Sooner or later you will depend on other people's code and use libraries, packages, modules,
plugins (or whatever they are called in your language) for your work. You most likely will 
experience _dependency hell_ at one point. To make things a little bit more transparent for you,
you might want to learn the principles of __semantic versioning__. This can be checked off quickly,
it's an easy concept.

## 3.Encodings
Even though we have almost half a century of high level languages behind us, some things we struggle
with are still very arcane. One of these things is _character encodings_. This one depends on 
your orientation. As an aspiring frontend developer it will not bother you often. In the backend
however, then you work with databases, data migrations or message passing, you need to always be
aware of the encoding of the data at any point of your pipeline. Ignorance will be painful there.

You should at least look up _UTF-8_ and _ASCII_ and read up on what your language uses internally.
When you get to be more advances, try finding out about different string formats in your language
(e.g. byte streams vs. character arrays). Results may vary.

## 4.Float arithmetic and integer overflow
Computers do arithmetic in binary, and any language calls the interfaces the CPU provides for
that. Most of the time you are just fine with that, and what you learned in your math classes
holds true. However you need to be aware that in most cases, in order to perform e.g. an addition,
the two summands are filled into a register of (usually) 64bit lenght before the operation. 
The result must fit inside those 64bit as well. If a calculation results in a value longer than 
the register, the surplus is just truncated. This leads to undefined results for 
e.g. adding or multiplying very large integers or very small errors on float operations, for instance
`0.2 + 0.1` is not exactly `0.3`.
Beware that you cannot always count on mathematical truths as you know them being implemented 
perfectly. For almost any language, there are (built-in or contributed) libraries for arbitrary
precision math. Get acquainted with them and use them if appropriate.

## 5.Sockets
As soon as you're getting started with your "hello world", To-Do lists or other demo apps, you
are likely to encounter someting such as `127.0.0.1:8888 ` to open in your browser. 
That's the address of a socket, consisting of the host (127.0.0.1 is your computer, often aliased by
`localhost`), `8888` is the port. You can use sockets for communication between programs or processes.
Even if your language provides easy to use helper functions, they are always managed by your
operating system (or computers in a network). So if you can't use a socket it might be blocked
by a firewall or wrongly configured DNS.

## 6.Environment Variables
Mac, Windows and Linux have more in common than you might be aware of. One of these things are
environment variables. Those are often, but not exclusively, use to store paths on the
 filesystem. For instance, all major operating systems have the concept of a
_TEMP_ directory. Because path to the directory is not the same for each OS (or think custom
installations), the path is stored in an environment variable. The variable _can be looked up
anytime from within any program/process_ and your language of choice will have helper functions
to do so.

## 7.Stdin/Stdout/Stderr, args
Console tools are cool again, and that is for a reason. You can script and automate complex
workflows relatively easily, and even more important, you can chain together completely
unrelated tools. The standard I/O streams behave roughly the same on Windows, Linux and Mac,
and represent the interface for chaining together tools. Args are command arguments, allowing
to configure the command. Your language will have helper functions to read from and write to the
I/O streams and read arguments. Once you grasp them, you have a very simple yet sustainable
user interface at your disposal, allowing to share your programs with others.

## 8. Build time vs. runtime
Basically we distinguish between compiled languages and interpreted languages. There are nuances
in between, such as Just in Time compilation. However for practical purpose, 
this distinction can be misleading, depending on your point of entry. If you use a powerful
framework for an interpreted language for instance, you might still need to _compile_ (or build).
It is important to develop a rough understanding for what happens during the build, and how this
transforms your code (especially types). Some things have different meanings at build time or 
runtime, one trivial example is the family of __now()__ functions. Do we want to capture 
'build time time' or 'runtime time'?

## 9. Data Structures
Your language might have classes and objects, lists, arrays, functions 


## 10. Domain modelling

Why did I not mention unit testing and debugging? Because despite their importance and similarity across languages,
they are still tightly coupled to their respective language runtime.