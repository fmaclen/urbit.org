---
date: ~2016.7.14
type: post
title: Urbyte 2: subject-oriented programming
author: Curtis Yarvin
layout: urbit,post
comments: true
hide: true
navmode: navbar
navdpad: false
navselect: blog
navpath: /
navhome: /
navclass: urbit
---
<br /><br />

You're playing in the Urbit REPL/shell (`:dojo`).  (If you
accidentally press `^X`, it will put you into the other default
app, `:talk`; press `^X` again to switch back.)

The dojo actually has its own command language, which is a
superset of Hoon.  Any input string which parses as a Hoon 
expression is a dojo command that prints the product of the 
expression.  In the space of strings which don't parse as Hoon
expressions, the dojo has other commands.

If this is just too abstract, think of the dojo as half Lisp
REPL, half Unix shell.

### Setting dojo variables

Like the Unix shell, the dojo has command variables.  Type

```
> =a 42
```

You've set the dojo variable `a` to the value `42`.  The dojo
puts this binding in the Hoon subject for expressions to use.
So you can write:

```
> a
42

> [4 a]
[4 42]

> ? [4 a]
  {@ud @ud}
[4 42]
```

To unbind `a`, just omit the value:

```
> =a
```

You removed `a` from the subject.  (We can bind it again later, or
bind over it without removing it.)

```
> [4 a]
-find.a
```

Now it's 
