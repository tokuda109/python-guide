.. Picking an Interpreter
   ======================

インタプリタを選ぶ
=========================

.. _which-python:

.. Which Python to use?

どっちのPythonを使いますか?

2.x vs 3.x
~~~~~~~~~~

.. **tl;dr**: Python 2.x is the status quo, Python 3.x is the shiny new thing.

**tl;dr**: Python 2.xは現在のプロジェクトだとこちらで、新しいプロジェクトだとPython 3.xを選びます。

.. `Further Reading <http://wiki.python.org/moin/Python2orPython3>`_

`参考文献 <http://wiki.python.org/moin/Python2orPython3>`_

.. Today
   -----

今日
----------

.. If you're choosing a Python interpreter to use, I *highly* recommend you Use
   Python 2.7.x, unless you have a strong reason not to.

使用するPythonインタプリタを選択するときに、
特別な理由がない場合はPython 2.7.xを使うことを *強く* 推奨しています。


.. The Future
   ----------

将来
----------

.. As more and more modules get ported over to Python3, the easier it will be for
   others to use it.

より多くのモジュールがPython3に移行したなら、
そのモジュールを使っている他のものも移行するのが簡単になるでしょう。

.. Which Python to Support?
   ~~~~~~~~~~~~~~~~~~~~~~~~

どのPythonをサポートすべきでしょう?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. If you're starting work on a new Python module, I recommend you write it for
   Python 2.5 or 2.6, and add support for Python3 in a later iteration.

新しいPythonのモジュールで作業を始めるなら、
Python 2.5や2.6などのPython3の機能をサポートしているバージョンで書くことを勧めます。

.. Implementations
   ~~~~~~~~~~~~~~~

実装
~~~~~~~~~~~~~~~

.. There are several popular implementations of the Python programming language on
   different back-ends.

異なるバックエンド上で、Pythonプログラミング言語の人気のある実装がいくつかあります。

CPython
-------

.. `CPython <http://www.python.org>`_ is the reference implementation of Python,
   written in C. It compiles Python code to intermediate bytecode which is then
   interpreted by a virtual machine. When people speak of *Python* they often mean
   not just the language but also this implementation. It provides the highest
   level of compatibility with Python packages and C extension modules.

CPythonはC言語で書かれているPythonの実装のことを指しています。
Pythonのコードを即座にバイトコードにコンパイルして、仮想マシンに解釈させます。
人々がPythonと話すときは、言語だけを指しているのではなくて、この実装のことも指しています。
PythonのパッケージとC拡張モジュールとの互換性を最大限持っています。

.. If you are writing open-source Python code and want to reach the widest possible
   audience, targeting CPython is your best bet. If you need to use any packages
   that rely on C extensions for their functionality (eg: numpy) then CPython
   is your only choice.

オープンソースやたくさんの人に使ってもらいと思っているPythonコードを書いているなら、
CPythonをターゲットにするとベストです。
C拡張モジュールに依存する(例: numpy)パッケージを使う必要がある場合は、CPythonしか選択肢はありません。

.. Being the reference implementation, all versions of the Python language are
   available as CPython. Python 3 is only available in a CPython implementation.

リファレンス実装であるPython言語の全てのバージョンは、CPythonとして利用することができます。
Python 3は、CPythonの実装でのみ使うことができます。

PyPy
----

.. `PyPy <http://pypy.org/>`_ is a Python interpreter implemented in a restricted
   statically-typed subset of the Python language called RPython. The interpreter
   features a just-in-time compiler and supports multiple back-ends (C, CLI, JVM).

`PyPy <http://pypy.org/>`_ は、RPythonと呼ばれているPython言語の制限された静的型付けされたサブセットとして実装されているPythonインタプリタです。
インタプリタはジャストインタイムコンパイラの機能を持っていたり、複数のバックエンド(C、CLI、JVM)をサポートしています。

.. PyPy aims for maximum compatibility with the reference CPython implementation
   while improving performance.

PyPyは、パフォーマンスの改善する際にCPythonの実装を参照して互換性を最大限持たせることを目的としています。

.. If you are looking to squeeze more performance out of your Python code, it's
   worth giving PyPy a try. On a suite of benchmarks, it's current `over 5 times
   faster than CPython <http://speed.pypy.org/>`_.

Pythonのコードを、より高いパフォーマンスを得ることができるものを探しているなら、PyPyを試してみる価値があります。ベンチマークの結果では、現在CPythonよりも5倍早いです。

.. Currently PyPy supports Python 2.7. [#pypy_ver]_

現在PyPyはPython 2.7をサポートしています。 [#pypy_ver]_

Jython
------

.. `Jython <http://www.jython.org/>`_ is a Python implementation that compiles
   Python code to Java byte code that then executes on a JVM. It has the additional
   advantage of being able to import and use any Java class the same as a Python
   module.

`Jython <http://www.jython.org/>`_ は、PythonコードをJVM上で実行する際にJavaのバイトコードにコンパイルするPythonの実装です。
Pythonモジュールと同じようにJavaクラスをインポートして使うことができるのでさらに便利です。

.. If you need to interface with an existing Java codebase or have other reasons to
   need to write Python code for the JVM, Jython is the best choice.

既存のJavaコードがあって、そのためのインターフェースが必要であるか、
JVM用にPythonのコードを書く他の理由がある場合、Jythonはベストな選択だと思います。

.. Currently Jython supports up to Python 2.5. [#jython_ver]_

現在Jythonは、Python 2.5をサポートしています。 [#jython_ver]_

IronPython
----------

.. `IronPython <http://ironpython.net/>`_  is an implementation of Python for .NET
   framework. It can use both Python and .NET framework libraries, and can also
   expose Python code to other .NET languages.

`IronPython <http://ironpython.net/>`_ は、.NET framework用のPythonの実装です。
Pythonと.NET frameworkのライブラリを使うことができ、Pythonを他の.NET言語に提供することも可能です。

.. `Python Tools for Visual Studio <http://ironpython.net/tools/>`_ integrate
   IronPython directly in to the Visual Studio development environment, making it
   an ideal choice for Windows developers.

`Python Tools for Visual Studio <http://ironpython.net/tools/>`_ は、
Visual Studio開発環境に直接IronPythonを統合していて、Windows開発者が選択することができます。

.. IronPython supports Python 2.7. [#iron_ver]_

IronPythonは、Python 2.7をサポートしています。 [#iron_ver]_

.. [#pypy_ver] http://pypy.org/compat.html

.. [#jython_ver] http://wiki.python.org/jython/JythonFaq/GeneralInfo#Is_Jython_the_same_language_as_Python.3F

.. [#iron_ver] http://ironpython.codeplex.com/releases/view/81726