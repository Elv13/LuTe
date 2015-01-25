LuTe: An extensible terminal for Lua addicts
============================================

This is the holeof LuTe a terminal based around the Lua programming language.
This project is a fork of the SuckLess "ST" terminal. The goal of this project
are:

* Creating a terminal compatible with xTerm but without the legacy cruft
* Having a minimal C++11 library core
* Implementing features as Lua extensions

### But why!

Yes, there is many terminals out there. I am a fan of `rxvt-unicode` (URXVT).
Hovever, while URXVT offer advanced extensions using `Perl5`, I don't consider
Perl the right language for terminal extensions. Lua is much cleaner and while
its library collection is larger, it is mostly comprised of older, often legacy
libraries. LuaJit offer almost direct to existing C libraries without additional
bindings. LuaJit is also fast enough to actually re-implement some parts of the
core vtx protocal in pure lua, reducing the need for C/C++ code only to the
hottest path and low level posix handling,

### C++ !!!!111 Are you insane?

Of course, why ask! But this is parallel to the point. The choice of C++**11**
for this, project is driven around the lua binding I choosed to use. While good
C bindings exist for ANSI C, for once, the C++ template mechanism is actually
useful. Then the C++11 `auto` and `constexpr` keywords allow better compile time
sanitizing of the binding. I don't plan to use most of the C++ braindead self
foot shooting "features" anyway.

### Design

This terminal is designed around a core library the can be included by a LuTe
based terminal.

### TODO

* Get rid of the X11, Freetype and XFt direct dependency and replace it with a
Pango based one.
* Create a Cairo/GTK basic shell
* Implement AppMenu support
* Add .desktop and default executable
* rc.lua support
* DBus API