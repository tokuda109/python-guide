.. Your Development Environment
   ============================

あなたの開発環境
===============================


.. Text Editors
   ::::::::::::

テキストエディタ
::::::::::::::::::

.. Just about anything which can edit plain text will work for writing Python code,
   however, using a more powerful editor may make your life a bit easier.

Pythonのコードを書くためにはプレーンテキストを編集することができるものであれば何でも構いません。
しかし、さらに強力なエディタを使うことでもっと楽になるかもしれません。


VIM
---

.. Vim is a text editor which uses keyboard shortcuts for editing instead of menus
   or icons. There exist a couple of plugins and settings for the VIM editor to
   aid python development. If you only develop in Python, a good start is to set
   the default settings for indentation and line-wrapping to values compliant with
   `PEP 8 <http://www.python.org/dev/peps/pep-0008/>`_. In your home directory,
   open a file called `.vimrc` and add the following lines:::

Vimは、メニューやアイコンの代わりにキーボードショートカットを使うテキストエディタです。
Pythonの開発用のVimエディタのプラグインや設定がいくつもあります。
Pythonでしか開発しないなら、インデントと行の折り返しのデフォルトの設定を
`PEP 8 <http://www.python.org/dev/peps/pep-0008/>`_ の値にするといいと思います。
ホームディレクトリで `.vimrc` というファイルを開いて、以下の行を追加して下さい。 ::

    set textwidth=79
    set shiftwidth=4
    set tabstop=4
    set expandtab
    set softtabstop=4
    set shiftround

With these settings, newlines are inserted after 79 characters and indentation
is set to 4 spaces per tab. If you also use VIM for other languages, there is a
handy plugin at indent_, which handles indentation settings for python source
files.

There is also a handy syntax plugin at syntax_ featuring some improvements over
the syntax file included in VIM 6.1.

These plugins supply you with a basic environment for developing in Python.
To get the most out of Vim, you should continually check your code for syntax
errors and PEP8 compliance. Luckily PEP8_ and Pyflakes_ will do this for you.
If your VIM is compiled with `+python` you can also utilize some very handy
plugins to do these checks from within the editor.

For PEP8 checking, install the vim-pep8_ plugin, and for pyflakes you can
install vim-pyflakes_. Now you can map the functions `Pep8()` or `Pyflakes()`
to any hotkey or action you want in Vim. Both plugins will display errors at
the bottom of the screen, and provide an easy way to jump to the corresponding
line. It's very handy to call these functions whenever you save a file. In
order to do this, add the following lines to your `vimrc`::

    autocmd BufWritePost *.py call Pyflakes()
    autocmd BufWritePost *.py call Pep8()

If you are already using syntastic_ you can enable it to run Pyflakes on write
and show errors and warnings in the quickfix window. An example configuration
to do that which also shows status and warning messages in the statusbar would be::

    set statusline+=%#warningmsg#
    set statusline+=%{SyntasticStatuslineFlag()}
    set statusline+=%*
    let g:syntastic_auto_loc_list=1
    let g:syntastic_loc_list_height=5

Python-mode
^^^^^^^^^^^

Python-mode_ is complex solution in VIM for work with python code.
It has:

- Async python code checking (pylint, pyflakes, pep8, mccabe) in any combination;
- Code refactoring and autocompletion with Rope;
- Fastest python folding;
- Nice and powered python syntax;
- Virtual env support;
- Search by python documentation and run python code;
- More other things like auto pep8 error fixes;
- Very customizable an documented as well;
- Have all required libraries in self;

And more stuff.


.. _indent: http://www.vim.org/scripts/script.php?script_id=974
.. _syntax: http://www.vim.org/scripts/script.php?script_id=790
.. _Pyflakes: http://pypi.python.org/pypi/pyflakes/
.. _vim-pyflakes: https://github.com/nvie/vim-pyflakes
.. _PEP8: http://pypi.python.org/pypi/pep8/
.. _vim-pep8: https://github.com/nvie/vim-pep8
.. _syntastic: https://github.com/scrooloose/syntastic
.. _Python-mode: https://github.com/klen/python-mode

.. todo:: add supertab notes

Emacs
-----

Emacs is a powerful text editor. It's fully programmable (lisp), but
it can be some work to wire up correctly. A good start if you're
already an Emacs user is `Python Programming in Emacs`_ at EmacsWiki.

1. Emacs itself comes with a python mode.
2. Python ships with an alternate version:
   `python-mode.el <https://launchpad.net/python-mode>`_
3. Fabián Ezequiel Gallina's provides nice functionality and
   behavior out of the box: `python.el <https://github.com/fgallina/python.el>`_

.. _Python Programming in Emacs: http://emacswiki.org/emacs/PythonProgrammingInEmacs

TextMate
--------

"`TextMate <http://macromates.com/>`_ brings Apple's approach to operating
systems into the world of text editors. By bridging UNIX underpinnings and GUI,
TextMate cherry-picks the best of both worlds to the benefit of expert
scripters and novice users alike."

Sublime Text
------------

.. "`Sublime Text <http://www.sublimetext.com/>`_ is a sophisticated text editor
   for code, html and prose. You'll love the slick user interface and
   extraordinary features."

「`Sublime Text <http://www.sublimetext.com/>`_ は、
コードやHTMLや何らかの文章を書くための洗練されたテキストエディタです。
あなたは滑らかなユーザーインターフェイスや豊富な機能の方が好きだと思います。」

.. Sublime Text has excellent support for editing Python code and uses Python for
   its plugin API.

Sublime TextにはPythonコードの書くための素晴らしい機能があり、
Sublime Text自体のプラグインのAPIにもPythonが使われています。

IDEs
::::

PyCharm / IntelliJ IDEA
-----------------------

`PyCharm <http://www.jetbrains.com/pycharm/>`_ is developed by JetBrains, also
known for IntelliJ IDEA. Both share the same code base and most of PyCharm's
features can be brought to IntelliJ with the free `Python Plug-In <http://plugins.intellij.net/plugin/?id=631/>`_.


Eclipse
-------

.. The most popular Eclipse plugin for Python development is Aptana's
   `PyDev <http://pydev.org>`_.

Pythonを開発するための一番一般的なEclipseプラグインは、Aptanaの `PyDev <http://pydev.org>`_ です。


Komodo IDE
----------
.. `Komodo IDE <http://www.activestate.com/komodo-ide>`_ is developed by
   ActiveState and is a commercial IDE for Windows, Mac
   and Linux.

`Komodo IDE <http://www.activestate.com/komodo-ide>`_ は、
ActiveStateによって開発されていて、Windows、Mac、Linux向けの商用のIDEです。


Spyder
------

`Spyder <http://code.google.com/p/spyderlib/>`_ an IDE specifically geared
toward working with scientific python libraries (namely `Scipy <http://www.scipy.org/>`_).
Includes integration with pyflakes_, `pylint <http://www.logilab.org/857>`_,
and `rope <http://rope.sourceforge.net/>`_.

Spyder is open-source (free), offers code completion, syntax highlighting,
class and function browser, and object inspection.


WingIDE
-------

.. `WingIDE <http://wingware.com/>`_ a python specific IDE.   Runs for Linux,
   Windows, and Mac (as an X11 application, which frustrates some Mac users).

`WingIDE <http://wingware.com/>`_ はPython仕様のIDEです。
Linux、Windows、Mac(Macユーザーには憂鬱ですが、X11アプリケーションとして)で使うことができます。


NINJA-IDE
---------

`NINJA-IDE <http://www.ninja-ide.org/>`_ (from the recursive acronym: "Ninja-IDE
Is Not Just Another IDE", is a cross-platform IDE, specially designed to build
Python applications, and runs on Linux/X11, Mac OS X and Windows desktop operating
systems. Installers for these platforms can be downloaded from the website.

NINJA-IDE is open-source software (GPLv3 licence) and is developed in Python and
Qt. The source files can be downloaded from `GitHub <https://github.com/ninja-ide>`_.


Interpreter Tools
:::::::::::::::::


virtualenv
----------

Virtualenv is a tool to keep the dependencies required by different projects
in separate places, by creating virtual Python environments for them.
It solves the "Project X depends on version 1.x but, Project Y needs 4.x"
dilemma and keeps your global site-packages directory clean and manageable.

`virtualenv <http://www.virtualenv.org/en/latest/index.html>`_ creates
a folder which contains all the necessary executables to contain the
packages that a Python project would need. An example workflow is given.

Install virtualenv::

    $ pip install virtualenv


Create a virtual environment for a project::

    $ cd my_project
    $ virtualenv venv

``virtualenv venv`` will create a folder in the current directory
which will contain the Python executable files, and a copy of the ``pip``
library which you can use to install other packages. The name of the
virtual environment (in this case, it was ``venv``) can be anything;
omitting the name will place the files in the current directory instead.

In order the start using the virtual environment, run::

    $ source venv/bin/activate


The name of the current virtual environment will now appear on the left
of the prompt (e.g. ``(venv)Your-Computer:your_project UserName$``) to
let you know that it's active. From now on, any package that you install
using ``pip`` will be placed in the venv folder, isolated from the global
Python installation. Install packages as usual::

    $ pip install requests

To stop using an environment simply type ``deactivate``. To remove the
environment, just remove the directory it was installed into. (In this
case, it would be ``rm -rf venv``).

Other Notes
^^^^^^^^^^^

Running ``virtualenv`` with the option ``--no-site-packages`` will not
include the packages that are installed globally. This can be useful
for keeping the package list clean in case it needs to be accessed later.

In order to keep your environment consistent, it's a good idea to "freeze"
the current state of the environment packages. To do this, run

::

    $ pip freeze > requirements.txt

This will create a ``requirements.txt`` file, which contains a simple
list of all the packages in the current environment, and their respective
versions. Later, when a different developer (or you, if you need to re-
create the environment) can install the same packages, with the same
versions by running

::

    $ pip install -r requirements.txt

This can help ensure consistency across installations, across deployments,
and across developers.

Lastly, remember to exclude the virtual environment folder from source
control by adding it to the ignore list.

virtualenvwrapper
-----------------

`Virtualenvwrapper <http://pypi.python.org/pypi/virtualenvwrapper>`_ makes
virtualenv a pleasure to use by wrapping the command line API with a nicer CLI.

::

    $ pip install virtualenvwrapper


Put this into your `~/.bash_profile` (Linux/Mac) file:

::

    $ export VIRTUALENVWRAPPER_VIRTUALENV_ARGS='--no-site-packages'

This will prevent your virtualenvs from relying on your (global) site packages
directory, so that they are completely separate..

Other Tools
:::::::::::

IDLE
----

`IDLE <http://docs.python.org/library/idle.html>`_ is an integrated
development environment that is part of Python standard library. It is
completely written in Python and uses Tkinter GUI toolkit. Though IDLE
is not suited for full-blown development using Python , it is quite
helpful to try out small Python snippets and experiment with different
features in Python.

It provides following features:

* Python Shell Window (interpreter)
* Multi window text editor that colorizes Python code
* Minimal debugging facility


IPython
-------

.. `IPython <http://ipython.org/>`_ provides a rich toolkit to help you make the
   most out of using Python interactively. Its main components are:

`IPython <http://ipython.org/>`_ は、Pythonをよりインタラクティブに使うためのリッチなツールキットです。
主要なコンポーネントは以下の通りです。 :

* Powerful Python shells (terminal- and Qt-based).
* A web-based notebook with the same core features but support for rich media,
  text, code, mathematical expressions and inline plots.
* Support for interactive data visualization and use of GUI toolkits.
* Flexible, embeddable interpreters to load into your own projects.
* Tools for high level and interactive parallel computing.

::

    $ pip install ipython



BPython
-------

`bpython <http://bpython-interpreter.org/>`_ is an alternative interface to the
Python interpreter for Unix-like operating systems. It has the following features:

* In-line syntax highlighting.
* Readline-like autocomplete with suggestions displayed as you type.
* Expected parameter list for any Python function.
* "Rewind" function to pop the last line of code from memory and re-evaluate.
* Send entered code off to a pastebin.
* Save entered code to a file.
* Auto-indentation.
* Python 3 support.

::

    $ pip install bpython
