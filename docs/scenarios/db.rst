.. Databases
   =========

データベース
==================

DB-API
------

.. The Python Database API (DB-API) defines a standard interface for Python
   database access modules. It's documented in `PEP 249 <http://www.python.org/dev/peps/pep-0249/>`_.
   Nearly all Python database modules such as `sqlite3`, `psycopg` and
   `mysql-python` conform to this interface.

Python Database API (DB-API) は、Pythonでデータベースにアクセスするためのモジュール用の標準のインターフェースです。
`PEP 249 <http://www.python.org/dev/peps/pep-0249/>`_ でドキュメント化されています。
`sqlite3` 、 `psycopg` 、 `mysql-python` 等の大体のPythonのデータベースモジュールは、
このインタフェースに準拠しています。

.. Tutorials that explain how to work with modules that conform to this interface can be found
   `here <http://halfcooked.com/presentations/osdc2006/python_databases.html>`__ and
   `here <http://www.amk.ca/python/writing/DB-API.html>`__.

このインタフェースに準拠するモジュールの使用方法について解説しているチュートリアルは、
`ここ <http://halfcooked.com/presentations/osdc2006/python_databases.html>`__ と
`ここ <http://www.amk.ca/python/writing/DB-API.html>`__ にあります。

SQLAlchemy
----------

.. `SQLAlchemy <http://www.sqlalchemy.org/>`_ is a commonly used database toolkit.
   Unlike many database libraries it not only provides an ORM layer but also a
   generalized API for writing database-agnostic code without SQL.

`SQLAlchemy <http://www.sqlalchemy.org/>`_ はデータベースのツールキットとして一般的に使われています。
多くのデータベースライブラリとは異なり、ORM層だけを提供している訳ではなく、
SQLを書かずにデータベースに依存しないコードを書くための一般的なAPIもあります。

::

    pip install sqlalchemy

Django ORM
----------

.. The Django ORM is the interface used by `Django <http://www.djangoproject.com>`_
   to provide database access.

Django ORMは、データベースにアクセスするために `Django <http://www.djangoproject.com>`_ で使われているインターフェースです。

.. It's based on the idea of models, an abstraction that makes it easier to
   manipulate data in Python.

Pythonでデータを簡単に操作できるように抽象化されていて、このモデルの考え方をベースにしています。

.. Documentation can be found `here <https://docs.djangoproject.com/en/1.3/#the-model-layer>`_

ドキュメントは、 `ここ <https://docs.djangoproject.com/en/1.3/#the-model-layer>`_ にあります。
