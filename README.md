oyooyo's fork of LuaMinify
--------------------------

This is my fork of [stravant](http://github.com/stravant)'s [LuaMinify](http://github.com/stravant/LuaMinify).
It is identical to the original LuaMinify, but includes a few open pull requests that I consider very useful, but that have not been merged for years (stravant no longer seems to actively maintain LuaMinify):

- [#17: fix import on case-sensitive filesystems](https://github.com/stravant/LuaMinify/pull/17)
- [#16: Significantly more efficient local variable naming](https://github.com/stravant/LuaMinify/pull/16)
- [#12: allow running from outside of the script dir](https://github.com/stravant/LuaMinify/pull/12)

Lua Parsing and Refactorization tools
=========

A collection of tools for working with Lua source code. Primarily a Lua source code minifier, but also includes some static analysis tools and a general Lua lexer and parser.

Currently the minifier performs:

- Stripping of all comments and whitespace
- True semantic renaming of all local variables to a reduced form
- Reduces the source to the minimal spacing, spaces are only inserted where actually needed.


LuaMinify Command Line Utility Usage
------------------------------------

The `LuaMinify` shell and batch files are given as shortcuts to running a command line instance of the minifier with the following usage:

    LuaMinify sourcefile [destfile]

Which will minify to a given destination file, or to a copy of the source file with _min appended to the filename if no output file is given.


LuaMinify Roblox Plugin Usage
-----------------------------

First, download the source code, which you can do by hitting this button:

![Click That](http://github.com/stravant/LuaMinify/raw/master/RobloxPluginInstructions.png)

Then copy the `RobloxPlugin` folder from the source into your Roblox Plugins directory, which can be found by hitting `Tools->Open Plugins Folder` in Roblox Studio.

Features/Todo
-------------
Features:

    - Lua scanner/parser, which generates a full AST
    - Lua reconstructor
        - minimal
        - full reconstruction (TODO: options, comments)
        - TODO: exact reconstructor
    - support for embedded long strings/comments e.g. [[abc [[ def ]] ghi]]

Todo:
    - use table.concat instead of appends in the reconstructors