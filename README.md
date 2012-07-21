Two days ago, looking for an eventual Eclipse replacement, I started to give a try to
[Sublime Text 2](http://www.sublimetext.com/).
One of my main usages of [PyDev](http://pydev.org/) (very good Eclipse plug-in for Python coder) is the code formatter.
Under ST2 I installed [PythonTidy](https://github.com/witsch/SublimePythonTidy) but unfortunately
it did not work for me.
So, for fun and learning, I decided to create a new ST2 plug-in: **Python PEP8 Autoformat**.
It is based on [autopep8](https://github.com/hhatto/autopep8) as code formatter.

# Python PEP8 Autoformat

Python PEP8 Autoformat is a Sublime Text 2 plug-in for reformat interactively Python source code according
to [PEP8](http://www.python.org/dev/peps/pep-0008/) (Style Guide for Python Code). 

## Installation

To avoid dependences, a version of autopep8 is shipped in this package. If you want to use version installed
on your system, you have to set the path to autopep8 in settings (see below).

1. Manually:
    + Download an [archive](https://bitbucket.org/StephaneBunel/pythonpep8autoformat/downloads) of Python PEP8 Autoformat
    + Move into ST2/Packages directory (Preference -> Browse packages) and create a new directory named 'Python PEP8 Autoformat'
    + Extract archive contents into 'Python PEP8 Autoformat' directory.

1. Using mercurial (hg) repository on bitbucket:
    + Open a terminal, cd to ST2/Packages directory (Preference -> Browse packages). Then type in terminal:
    + `hg clone https://bitbucket.org/StephaneBunel/pythonpep8autoformat 'Python PEP8 Autoformat'`

1. Using [Sublime Package Manager](http://wbond.net/sublime_packages/package_control)
    + Use `cmd+shift+P` then `Package Control: Install Package`
    + Look for `Python PEP8 Autoformat` and install it.

## Settings

You'll find default settings in file `pep8_autoformat.sublime-settings`.

    {
        // autoformat code on save ?
        "autoformat_on_save": false,

        // path to autopep8 or "" to use packaged version
        "command": "",

        // select errors / warnings(e.g. ["E4", "W"])
        "select": [],

        // do not fix these errors / warnings(e.g. ["E4", "W"])
        "ignore": ["E501"],

        // for debugging purpose (print executed command in console)
        "show_command": true
    }

The first time you'll want to change them use Settings menu: Preferences > Packages Settings > Python PEP8 Autoformat > ...
Open both "Settings - Default" AND "Settings - User". Copy Default settings to User settings, modify
User settings and save. By doing like this, your personal settings will be kept safe over plug-in upgrade.

## Usage

Formatting is applied on the whole document if there is no selection.
Reformatting operate only if the document is in Python syntax mode (default for all .py files).

### Using keyboard:

- GNU/Linux: `ctrl+shift+r`
- OSX:       `ctrl+meta+r`
- Windows:   `ctrl+shift+r`

### Using Command Palette:

As defined in `Default.sublime-commands` file:

	[
	    { "caption": "User: Python PEP8 Autoformat", "command": "pep8_autoformat" }
	]

You can format your Python code by opening Command Palette (ctrl+shift+P)
and type "auto"... up to highlight full caption.

## License

Copyright 2012 Stéphane Bunel

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
