.. Documentation
   =============

ドキュメント
==========================

.. Readability is a primary focus for Python developers, in both project
   and code documentation. Following some simple best practices can save
   both you and others a lot of time.

プロジェクトとコードのドキュメントのどちらにおいても、Pythonの開発者にとって読みやすさは最も大事なことです。
以下に紹介するいくつかのシンプルなプラクティスはあなたや他の人の多くの時間を節約することに役立つでしょう。

.. Project Documentation
   ---------------------

プロジェクトのドキュメント
------------------------------------------

.. A ``README`` file at the root directory should give general
   information to the users and the maintainers. It should be raw text or
   written in some very easy to read markup, such as
   :ref:`reStructuredText-ref` and Markdown. It should contain a few
   lines explaining the purpose of the project or the library (without
   assuming the user knows anything about the project), the url of the
   main source for the software, and some basic credit information. This
   file is the main entry point for readers of the code.

ルートディレクトリにある ``README`` ファイルは、一般的な情報を使う人やメンテナーに伝えるものです。
生のテキストか :ref:`reStructuredText-ref` や Markdown のような読みやすいマークアップで書かれている文章にして下さい。
プロジェクトやライブラリの目的を説明する部分(他にもプロジェクトで使う人に教えていたほうがいい情報)や、
ソフトウェアのソースがあるURLや、基本的なクレジット情報が数行ずつあります。
このファイルはコードの読者にとってエントリーポイントになります。

.. An ``INSTALL`` file is less necessary with python.  The installation
   instructions are often reduced to one command, such as ``pip install
   module`` or ``python setup.py install`` and added to the ``README``
   file.

``INSTALL`` ファイルはPythonでは必要ありません。
インストール手順は、 ``pip install module`` や ``python setup.py install`` のように一行にまとめて、
``README`` ファイルに書かれることもあります。

.. A ``LICENSE`` file should *always* be present and specify the license under which the
   software is made available to the public.

``LICENSE`` ファイルは、ソフトウェアが公開される場合にはライセンスを掲載して、指定するように常にして下さい。

.. A ``TODO`` file or a ``TODO`` section in ``README`` should list the
   planned development for the code.

``TODO`` ファイルや ``README`` の ``TODO`` セクションはコードの開発計画を箇条書きして下さい。

.. A ``CHANGELOG`` file or section in ``README`` should compile a short
   overview of the changes in the code base for the latest versions.

``CHANGELOG`` ファイルや ``README`` のセクションは最新版のコードの変更点の簡単な概要を書いて下さい。

.. Project Publication
   -------------------

プロジェクトの公開
--------------------------------------

.. Depending on the project, your documentation might include some or all
   of the following components:

プロジェクトによって、ドキュメントは以下のコンポーネントの一部、もしくは全てを含めることができます。 :

.. A *introduction* should show a very short overview of what can be
   done with the product, using one or two extremely simplified use
   cases. This is the thirty-second pitch for your project.

.. A *tutorial* should show some primary use cases in more detail. The reader will
   follow a step-by-step procedure to set-up a working prototype.

.. An *API reference* is typically generated from the code (see
   :ref:`docstrings <docstring-ref>`). It will list all publicly available interfaces,
   parameters, and return values.

.. *Developer documentation* is intended for potential contributors. This can
   include code convention and general design strategy of the project.

- *手順* は、製品で何ができるかの非常に簡潔な概要を掲載して下さい。
  This is the thirty-second pitch for your project.

- *チュートリアル* は、より詳しくユースケースを掲載して下さい。
  読者はプロトタイプの作業をするためにステップ・バイ・ステップで手順を追っていくでしょう。

- *APIリファレンス* は、コード( :ref:`docstrings <docstring-ref>` を参照して下さい)から生成されます。
  公開されていて、利用可能なインターフェース、パラメーター、返り値などの一覧にして下さい。

- *開発者用のドキュメント* は、潜在的なコントリビューター向けにすることを目的とします。
  これには、コード規約とプロジェクトの一般的なデザイン戦略を含めることができます。


.. _sphinx-ref:

Sphinx
~~~~~~

.. Sphinx_ is far and away the most popular python documentation
   tool. **Use it.**  It converts :ref:`restructuredtext-ref` markup language
   into a range of output formats including HTML, LaTeX (for printable
   PDF versions), manual pages, and plain text.

Sphinx_ は最も人気のあるPythonのドキュメント作成ツールです。 **使って下さい。**
HTML、LaTeX (印刷可能なPDF)、マニュアルページ、プレーンテキスト等のフォーマットで出力することができる
:ref:`restructuredtext-ref` マークアップ言語に変換されます。

.. There is also **great**, **free** hosting for your Sphinx_ docs:
   `Read The Docs`_. Use it. You can configure it with commit hooks to
   your source repository so that rebuilding your documentation will
   happen automatically.

Sphinx_ ドキュメントを **無料** でホスティングする　**すばらしい**　`Read The Docs`_ というものがあります。
使って下さい。ソースのレポジトリにコミットフックを設定することができるので、ドキュメントは自動的に再ビルドされます。


.. note::

    Sphinx is famous for its API generation, but it also works well
    for general project documentation. This Guide is built with
    Sphinx_ and is hosted on `Read The Docs`_

.. _Sphinx: http://sphinx.pocoo.org
.. _Read The Docs: http://readthedocs.org

.. _restructuredtext-ref:

reStructuredText
~~~~~~~~~~~~~~~~

.. Most Python documentation is written with reStructuredText_. It's like
   Markdown with all the optional extensions built in.

ほとんどのPythonのドキュメントは reStructuredText_ で書かれています。

The `reStructuredText Primer`_ and the `reStructuredText Quick
Reference`_ should help you familiarize yourself with its syntax.

.. _reStructuredText: http://docutils.sourceforge.net/rst.html
.. _reStructuredText Primer: http://sphinx.pocoo.org/rest.html
.. _reStructuredText Quick Reference: http://docutils.sourceforge.net/docs/user/rst/quickref.html


.. Code Documentation Advice
   -------------------------

コードドキュメントのアドバイス
--------------------------------------------------

.. Comments clarify code and begin with a hash (``#``).

コメントはコードを明確にします。
ハッシュ (``#``) で始めます。

.. _docstring-ref:

.. In Python, *docstrings* describe modules, classes, and functions: ::

Pythonでは、 *docstrings* はモジュール、クラス、関数に記述します。 ::

    def square_and_rooter(x):
        """Returns the square root of self times self."""
        ...

.. In general, follow the `comment section of PEP 0008`_ (the "Python Style Guide").

一般的には、 `comment section of PEP 0008`_ (Pythonスタイルガイド)に従って下さい。

.. _comment section of PEP 0008: http://www.python.org/dev/peps/pep-0008/#comments

.. Commenting Sections of Code
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~

コードのコメント
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. *Do not use triple-quote strings to comment code*. This is not a good
   practice, because line-oriented command-line tools such as grep will
   not be aware that the commented code is inactive. It is better to add
   hashes at the proper indentation level for every commented line. Your
   editor probably has the ability to do this easily, and it is worth
   learning the comment/uncomment toggle. (*e.g.* ctrl-v on Vim)

*コメントコードにトリプルクォートを使わないで下さい。*
これは良いプラクティスではありません。なぜなら、

Docstrings and Magic
~~~~~~~~~~~~~~~~~~~~

Some tools use docstrings to embed more-than-documentation behavior,
such as unit test logic. Those can be nice, but you won't ever go
wrong with vanilla "here's what this does."

.. Docstrings versus Block comments
   ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Docstringsとブロックコメント
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. These aren't interchangeable. For a function or class, the leading
   comment block is a programmer's note. The docstring describes the
   operation of the function or class: ::

これらは互換性がありません。関数やクラスの先頭のコメントブロックは開発者のメモです。
Docstringは関数やクラスの動作について説明されています。 ::

    # This function slows down program execution for some reason.
    def square_and_rooter(x):
        """Returns the square root of self times self."""
    ...

.. seealso:: Further reading on docstrings: `PEP 0257`_

.. _PEP 0257: http://www.python.org/dev/peps/pep-0257/


.. Other Tools
   -----------

他のツール
----------------------

.. You might see these in the wild. Use :ref:`sphinx-ref`.

どこかで以下のものを見ることがあるかもしれませんが、 :ref:`sphinx-ref` を使って下さい。

Pycco_
    .. Pycco is a "literate-programming-style documentation generator"
       and is a port of the node.js Docco_. It makes code into a
       side-by-side HTML code and documentation.

    Pyccoは読み書き可能なプログラミングスタイルのドキュメントのジェネレーターで、node.jsのDoccoの一部です。
    コードをHTMLのコードやドキュメントにします。

.. _Pycco: http://fitzgen.github.com/pycco
.. _Docco: http://jashkenas.github.com/docco

Ronn_
    .. Ronn builds unix manuals. It converts human readable textfiles to roff for terminal display, and also to HTML for the web.

    Ronnはunixのマニュアルを生成します。人間が読みやすいテキストファイルをターミナルで表示するよううに変換します。ウェブ用にHTMLにも変換します。

.. _Ronn: https://github.com/rtomayko/ronn

Epydoc_
    .. Epydoc is discontinued. Use :ref:`sphinx-ref` instead.

    Epydocは廃止されました。代わりに :ref:`sphinx-ref` を使って下さい。

.. _Epydoc: http://epydoc.sourceforge.net