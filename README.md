Copy of the Haroogan Vim Youcompleteme for windows.
===================================================

Vim YouCompleteMe for Windows
=============================

--------------------------------------------------------------------------------

![Vim][Images/Vim]
![for][Images/for]
![Windows][Images/Windows]

Table of Contents
=================

--------------------------------------------------------------------------------

- [About](#markdown-header-about)
- [Installation](#markdown-header-installation)
    - [Requirements](#markdown-header-requirements)
        - [Platforms](#markdown-header-platforms)
        - [Architectures](#markdown-header-architectures)
    - [Instructions](#markdown-header-instructions)
    - [Pitfalls](#markdown-header-pitfalls)
        - [Python Terminal Window](#markdown-header-python-terminal-window)
        - [Microsoft Visual C Runtime](#markdown-header-microsoft-visual-c-runtime)
- [Miscellaneous](#markdown-header-miscellaneous)
- [Downloads](#markdown-header-downloads)
    - [Featured](#markdown-header-featured)
    - [Previous](#markdown-header-previous)

About
=====

--------------------------------------------------------------------------------

Building the native back end of the [Vim][Vim/Wikipedia] (*Vi IMproved*) plugin,
[YouCompleteMe][Valloric/GitHub/YouCompleteMe] (YCM) by [Val Markovic][], for
[Microsoft Windows][Windows/Wikipedia] has proven to be difficult for
inexperienced users.

The goal of this project is to provide high-quality native builds of YCM for
Windows with support for both x86 (32-bit) and x64 (64-bit) architectures.

Installation
============

--------------------------------------------------------------------------------

Requirements
------------

### Platforms

- Windows 2000;
- Windows XP;
- Windows Vista;
- Windows 7;
- Windows 8.

### Architectures

- x86 (x86-32, x32, i686);
- x64 (x86-64, amd64).

Instructions
------------

1. Make sure that your current Vim version is at least 7.3.584 and that it was
   compiled with support for [Python][Python/Wikipedia] 2 (in particular, 2.6 or
   2.7), and if you don't have one, then you could opt to my
   [Vim for Windows][];
2. Make sure that the directory containing Python 2 interpreter (`python.exe`
   and/or `pythonw.exe`) is in the `PATH` environment variable;
3. Since the plugin relies on [LLVM/Clang][] to provide accurate semantic
   completion framework for C-family, you will need to install it as well (in
   particular, all you need is `libclang.dll`), and if you don't have one, then
   you could opt to my [LLVM for Windows][];
4. Make sure that the directory containing `libclang.dll` is either in the
   `PATH` environment variable (recommended) or `libclang.dll` is in the same
   directory as `ycm_core.pyd`;
5. Go to [Downloads](#markdown-header-downloads) and obtain archive with desired
   version and compatible with your current platform and architecture (see
   [Requirements](#markdown-header-requirements));

    > **NOTE:** It is very important to make sure that targeted architectures
    > match for all 3 components:
    >
    > - Vim (`vim.exe` and `gvim.exe`);
    > - LLVM/Clang (`libclang.dll`);
    > - YCM (`ycm_core.pyd`).
    >
    > In other words, if you have 64-bit Vim, then you should rely on 64-bit
    > LLVM/Clang and 64-bit YCM. Conversely, if you have 32-bit Vim, then you
    > should rely on 32-bit LLVM/Clang and 32-bit YCM. Why? Because *memory
    > addressing models* (which are defined by targeted architectures) of
    > statically/dynamically linked binary components must match, otherwise
    > there is *binary incompatibility* and BOOM! The universe folds back on
    > itself... Don't do this at home... No, seriously, you were warned!

6. Finally, extract the archive and deploy the plugin with your favorite method.

Pitfalls
--------

### Python Terminal Window

Some parts of YCM require the directory containing Python 2 interpreter
(`python.exe` and/or `pythonw.exe`) to be present in the `PATH` environment
variable (see [Instructions](#markdown-header-instructions)). If after
installation you experience a Python terminal window when you start Vim, then
most likely the directory containing `pythonw.exe` is not present in the `PATH`
environment variable.

There is a major difference between `python.exe` and `pythonw.exe`. On the one
hand, when executed, `python.exe` opens a terminal window, which stays open even
if the program uses GUI. On the other hand, when executed, `pythonw.exe` does
not open any terminal window and runs silently on the background.

To summarize, in order to get rid of the annoying Python terminal window, make
sure that the directory containing `pythonw.exe` is present in the `PATH`
environment variable.

> **NOTE:** Usage of `pythonw.exe` is prioritized over `python.exe` when both
> are available.

### Microsoft Visual C Runtime

Microsoft Visual C Runtime (MSVCR) is notorious of having many different
versions, some of which are buggy and/or break backward compatibility. If after
properly installing YCM you experience the following error dialog when starting
Vim:

    :::text
    Runtime Error!

    Program: $VIM\gvim.exe

    R6034
    An application has made an attempt to load the C runtime
    library incorrectly.
    Please contact the application's support team for more
    information.

then congratulations, you've just plunged into that shit! `>_<`

To solve that, carefully search through all the directories in the `PATH`
environment variable for `msvcr90.dll` and eliminate them (at least for Vim
startup).

It is good, in general, to keep your `PATH` clean and to have there only those
directories that you currently need as it prevents situations like this. For
example, it is common these days that people have Intel iCLS Client (absolutely
useless by the way) installed which contains old/buggy version of `msvcr90.dll`,
and it adds itself to the system's `PATH` environment variable by default.
You'll have to definitely eliminate this one. Sigh... These giant corporations
will screw us all one day...

Miscellaneous
=============

--------------------------------------------------------------------------------

If you are interested which toolchain I use to build [Vim YouCompleteMe for
Windows][] as well as other native software for Windows in general, then I'd be
glad to say that I'm using [MinGW-w64][] (not [MinGW][]!) which is a production
quality toolchain, bringing bleeding-edge [GCC][GCC/Wikipedia] features to
Windows for both x86 and x64 architectures.

Downloads
=========

--------------------------------------------------------------------------------

> **NOTE:** Since YCM does not employ any versioning scheme, commit hashes are
> used instead.

Featured
--------

| x64                                                                  | x86                                                                  | YCM     | Python 2 | LLVM/Clang |
|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|:-------:|:--------:|:----------:|
| ![Download][Images/Download]* *[Download][Downloads/YCM/733de48/x64] | ![Download][Images/Download]* *[Download][Downloads/YCM/733de48/x86] | 733de48 | 2.7.X    | 3.4.X      |

Previous
--------

| x64                                                                  | x86                                                                  | YCM     | Python 2 | LLVM/Clang |
|:--------------------------------------------------------------------:|:--------------------------------------------------------------------:|:-------:|:--------:|:----------:|
| ![Download][Images/Download]* *[Download][Downloads/YCM/9e54390/x64] | ![Download][Images/Download]* *[Download][Downloads/YCM/9e54390/x86] | 9e54390 | 2.7.X    | 3.4.X      |
| ![Download][Images/Download]* *[Download][Downloads/YCM/cf62110/x64] | ![Download][Images/Download]* *[Download][Downloads/YCM/cf62110/x86] | cf62110 | 2.7.X    | 3.4.X      |
| ![Download][Images/Download]* *[Download][Downloads/YCM/ee12530/x64] | ![Download][Images/Download]* *[Download][Downloads/YCM/ee12530/x86] | ee12530 | 2.7.X    | 3.4.X      |

[Vim/Wikipedia]: http://en.wikipedia.org/wiki/Vim_(text_editor)

[Python/Wikipedia]: http://en.wikipedia.org/wiki/Python_(programming_language)

[Windows/Wikipedia]: http://en.wikipedia.org/wiki/Microsoft_Windows

[GCC/Wikipedia]: http://en.wikipedia.org/wiki/GNU_Compiler_Collection

[MinGW]: http://www.mingw.org/

[MinGW-w64]: http://mingw-w64.sourceforge.net/

[LLVM/Clang]: http://clang.llvm.org/

[Valloric/GitHub/YouCompleteMe]: http://valloric.github.io/YouCompleteMe/

[Val Markovic]: http://val.markovic.io/

[Vim for Windows]:               /Haroogan/vim-for-windows
[Vim YouCompleteMe for Windows]: /Haroogan/vim-youcompleteme-for-windows
[LLVM for Windows]:              /Haroogan/llvm-for-windows

[Downloads/YCM/733de48/x64]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-733de48-windows-x64.zip
[Downloads/YCM/733de48/x86]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-733de48-windows-x86.zip

[Downloads/YCM/9e54390/x64]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-9e54390-windows-x64.zip
[Downloads/YCM/9e54390/x86]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-9e54390-windows-x86.zip

[Downloads/YCM/cf62110/x64]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-cf62110-windows-x64.zip
[Downloads/YCM/cf62110/x86]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-cf62110-windows-x86.zip

[Downloads/YCM/ee12530/x64]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-windows-x64.zip
[Downloads/YCM/ee12530/x86]: /Haroogan/vim-youcompleteme-for-windows/downloads/vim-ycm-windows-x86.zip

[Images/Vim]:      https://bitbucket.org/Haroogan/vim-youcompleteme-for-windows/raw/master/images/400-400/vim.png               "Vim"
[Images/for]:      https://bitbucket.org/Haroogan/vim-youcompleteme-for-windows/raw/master/images/200-400/green-right-arrow.png "for"
[Images/Windows]:  https://bitbucket.org/Haroogan/vim-youcompleteme-for-windows/raw/master/images/400-400/windows.png           "Windows"
[Images/Download]: https://bitbucket.org/Haroogan/vim-youcompleteme-for-windows/raw/master/images/16-16/download.png            "Download"
