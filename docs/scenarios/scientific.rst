.. =======================
   Scientific Applications
   =======================

===========================================
科学分野におけるアプリケーション
===========================================

.. Context
   :::::::

コンテキスト
::::::::::::::

.. Python is frequently used for high-performance scientific applications. Python
   is widely used in academia and scientific projects because it is easy to write,
   and it performs really well.

Pythonは、ハイパフォーマンスが要求される科学分野のアプリケーションによく使われます。
Pythonは、書くのが容易でキチンと動くという理由から学校や科学分野のプロジェクトで広く使われています。

.. Due to its high performance nature, scientific computing in python often refers
   to external libraries, typically written in faster languages (like C, or FORTRAN
   for matrix operations). The main libraries used are `NumPy`_ and
   `SciPy`_.

ハイパフォーマンスであるため、Pythonで科学技術の計算には、
より早く実行できる(行列演算が得意なCやFORTRANのような)言語で書かれた外部のライブラリが使われます。
主要なライブラリとして `NumPy`_ と `SciPy`_ が使われます。

.. Libraries
   :::::::::

ライブラリ
::::::::::::::::::

NumPy
-----

`NumPy <http://numpy.scipy.org/>`_ is a low level library written in C (and
FORTRAN) for high level mathematical functions. NumPy cleverly overcomes the
problem of running slower algorithms on Python by using multidimensional arrays
and functions that operate on arrays. Any algorithm can then be expressed as a
function on arrays, allowing the algorithms to be run quickly.

`NumPy <http://numpy.scipy.org/>`_ は、
ハイレベルな数学の計算をすることができるC言語(そしてFORTRAN)で書かれている低レベルのライブラリです。


.. NumPy is part of the SciPy project, and is released as a separate library so
   people who only need the basic requirements can just use NumPy.

NumPyはSciPyプロジェクトの一部で、
基本的な要件としてNumPyだけを使うことができるようにするために別のライブラリとしてリリースされています。

.. NumPy is compatible with Python versions 2.4 through to 2.7.2 and 3.1+.

NumPyはPythonのバージョン2.4から2.7.2や3.1以上まで互換性があります。

SciPy
-----

.. `SciPy <http://scipy.org/>`_ is a library that uses Numpy for more mathematical
   function. SciPy uses NumPy arrays as its basic data structure. SciPy comes with
   modules for various commonly used tasks in scientific programing like linear
   algebra, integration (calculus), ordinary differential equation solvers and
   signal processing.

`SciPy <http://scipy.org/>`_ は、数学分野の機能をより多く持っているライブラリで、Numpyを使っています。
SciPyは基本的なデータ構造の部分にNumPyの配列を使っています。
SciPyは、線形代数、統合（微積分）、常微分方程式ソルバや信号処理のような科学技術の分野で、
使われるプログラムの処理において様々なところで一般的に使われているモジュールから成ります。

Enthought
---------

.. Installing NumPy and SciPy can be a daunting task. Which is why the
   `Enthought Python distribution <http://enthought.com/>`_ was created. With
   Enthought, scientific python has never been easier (one click to install about
   100 scientific python packages). User beware: Enthought is not free.
   100 scientific python packages). The Enthought Python Distribution comes in two
   variants: a free version `EPD Free <http://enthought.com/products/epd_free.php>`_
   and a paid version with various `pricing options.
   <http://enthought.com/products/epd_sublevels.php>`_

NumPyとSciPyをインストールする作業は手こずるかもしれません。
そういった理由から `Enthought Python distribution <http://enthought.com/>`_ が作られました。
Enthoughtで、科学分野においてPythonを使うことはかつてないほど容易になりました。
(100くらいの科学分野のPythonパッケージがワンクリックでインストールできます)
Enthought Python Distributionは無料版の `EPD Free <http://enthought.com/products/epd_free.php>`_ と
`いくつかの支払オプション <http://enthought.com/products/epd_sublevels.php>`_ がある有償版の2種類が提供されています。

Matplotlib
----------

`matplotlib <http://matplotlib.sourceforge.net/>`_ is a flexible plotting
library for creating interactive 2D and 3D plots that can also be saved as
manuscript-quality figures.  The API in many ways reflects that of `MATLAB <http://www.mathworks.com/products/matlab/>`_,
easing transition of MATLAB users to Python.  Many examples, along with the
source code to re-create them, can be browsed at the `matplotlib gallery <http://matplotlib.sourceforge.net/gallery.html>`_.

Resources
:::::::::

.. Many people who do scientific computing are on Windows. And yet many of the
   scientific computing packages are notoriously difficult to build and install.
   `Christoph Gohlke <http://www.lfd.uci.edu/~gohlke/pythonlibs/>`_ however, has
   compiled a list of Windows binaries for many useful Python packages. The list
   of packages has grown from a mainly scientific python resource to a more
   general list. It might be a good idea to check it out if you're on Windows.

ほとんどの人が科学技術の計算をWindowsで行なっています。
そして科学技術の計算をするパッケージのほとんどがビルドやインストールすることが難しいという評判です。
しかし、 `Christoph Gohlke <http://www.lfd.uci.edu/~gohlke/pythonlibs/>`_ は、
たくさんの便利なPythonパッケージ用にWindowsバイナリのリストをコンパイルしました。
