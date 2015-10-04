# Introduction #

**assembla2jira** is written in [LUA](http://www.lua.org/) scripting language. To run it you need to prepare/install LUA language interpreter according to your operation system practices and also some required LUA libraries.

# Requirements #
  1. **LUA interpreter**. **assembla2jira** is written and tested for Lua 5.1.x version. It should work under Lua 5.2.x but is not tested yet in this environment.
    * Unix users should look in your OS package manager for a port/package of LUA.
    * For Windows users I recommend [Lua for Windows (LfW)](http://code.google.com/p/luaforwindows/) package. Don't forget to add path to your LUA interpreter into PATH environment variable.
  1. **`JSON.lua`** by [Jeffrey Friedl](http://regex.info/blog/lua/json) - a pure LUA [JSON](http://json.org/) parser. We're already including **MODIFIED** version of this library with our distribution, it should be extracted in same folder where you put `assembla2jira.lua` so do not use original version - it will **not work**. Original version and patch file is also included in distribution in JSON.lua.orig and JSON.lua.patch files for informational/copyright uses.
  1. [\*LibYAML binding for Lua\*](http://yaml.luaforge.net/) - LUA module by Andrew Danforth written in C for parsing [YAML](http://en.wikipedia.org/wiki/YAML). YAML is used as a serialization format for packing some fields in Assembla database dumps.
    * Unix: check if your OS contains package for this library and install it. If it doesn't exists then you need to read its [Installation Manual](http://yaml.luaforge.net/manual.html#install) and build it manually by using make. After building it should be included in LUA search path for modules, consult with LUA documentation about this. Note that for building this module you will also need to build [LibYAML](http://pyyaml.org/wiki/LibYAML) library.
    * Windows: you can also try and build **LibYAML binding for Lua** by yourself but for convenience I put prebuilt archive, check it in [Downloads](http://code.google.com/p/assembla2jira/downloads/detail?name=yaml-0.2-lua-5.1.4.zip&can=2&q=#makechanges) section. This module is built against Lua for Windows 1.5.4 (`Lua_V5.1.4-45`). It should be extracted in clibs\ sub-folder within Lua for Windows folder, or in the same folder where you placed **assembla2jira** script.

# Verifying installation #
After preparing and installing all components mentioned in **Requirements** section try to run `assembla2jira.lua` script without parameters:
  * Unix:
```
/usr/local/bin/lua assembla2jira.lua
```
(or make it executable, then you can run it directly)
  * Windows:
```
<Path to LUA interpreter>\lua.exe assembla2jira.lua
```
(alternatively you can assign shell handler for .lua extension to be able to run LUA scripts directly).

`assembla2jira.lua` should execute without errors and display Usage information:
```
Usage: assembla2jira.lua [-s <settings file>] <dump file> <output file>
```