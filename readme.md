# Binaries for cpgf library and dependencies

This repository contains the binary external dependency libraries for [cpgf library](https://github.com/cpgf/cpgf).

The core cpgf library doesn't have any external dependencies, but the script binding library depends on the underlying script engines.

Of course we can build those dependdencies from source, but some libraries may be quite difficult to build (such as Google V8) and waste a lot of time. The repository is to save our time.

## Folder and file structure

Each sub folder is a platform with a certain compiler. For example, the folder "mingw32" is for MingW 32 bits and apparently the compiler is GCC. The "msvc32" folder is for Microsoft Visual C++ and of course for Windows, 32 bits.

In each sub folder, there are zip files. Each file is for one library, one compiler, one build target, and one link mode.

A zip file should contain all necessary header files, library files, and as well as any dynamic executables (such as DLLs on Windows).

## The zip file name convention

For example, the zip file name

    lua-5.3.4_release_static_mingw_gcc-5.3.0.zip
     A    B     C       D      E    F    G
 
There are seven components in the file name, labeled A~G.

 - A - The library name. Here is Lua.
 - B - The library version. Here is 5.3.4. The version is the Lua version.
 - C - Release or debug.
 - D - Static or dynamic.
 - E - Which platform? MingW, or MSVC, or Linux, or whatever.
 - F - Which compiler? GCC, or MSVC, or Clang, or whatever.
 - G - The compiler version used to compile the library.

## The folder structure inside the zip file

**lua-5.3.4\_release\_static\_mingw\_gcc-5.3.0** # the root folder  
  **-- lib** # the library files, .a, or .lib  
  **-- include** # the header files  
  **-- bin** # any dynamic executable, .dll  

## How can you help to contribute to this project

You are welcome to put libraries for Lua, Python 2, Google V8 JavaScript engine, Mozilla SpiderMonkey JavaScript engine to this repository.

Especially V8 and SpiderMonkey are needed because they are too difficult to compile.

## About copyright

Each library binary should be redistributed under its own copyright. This respository is only a convenient way to get those binaries. I don't own any copyright of any libraries listed here.

