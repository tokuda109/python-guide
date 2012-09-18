.. ==================
   Image Manipulation
   ==================

==================
画像操作
==================

.. todo::
    Add introduction about image manipulation and its Python libraries.

Python Imaging Library
----------------------

.. The `Python Imaging Library <http://www.pythonware.com/products/pil/>`_, or PIL
   for short, is *the* library for image manipulation in Python.

`Python Imaging Library <http://www.pythonware.com/products/pil/>`_ 、短くPILと言われているライブラリは、
Pythonで画像操作のためのライブラリです。

.. It works with Python 1.5.2 and above, including 2.5, 2.6 and 2.7. Unfortunately,
   it doesn't work with 3.0+ yet.

Python 2.5、2.6、2.7を含む1.5.2以上で動きます。
不幸にも3.0以上ではまだ動きません。

.. Installation
   ~~~~~~~~~~~~

インストール方法
~~~~~~~~~~~~~~~~~~~~~~~~

.. PIL has a reputation of not being very straightforward to install. Listed below
   are installation notes on various systems.

PILは、インストールすることが簡単ではとてもないという評価を得ています。
様々なシステムでのインストールの注意事項は、以下の通りです。

.. Also, there's a fork named `Pillow <http://pypi.python.org/pypi/Pillow>`_ which is easier
   to install. It has good setup instructions for all platforms.

また、インストールがより容易な `Pillow <http://pypi.python.org/pypi/Pillow>`_ というフォークされたものもあります。
全てのプラットフォームにセットアップするための手順を掲載します。

.. Installing on Linux
   ~~~~~~~~~~~~~~~~~~~

Linuxにインストールする
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ubuntu 11.04
````````````

.. todo::
    Notes on installing on Ubuntu 11.04

.. Installing on Mac OS X
   ~~~~~~~~~~~~~~~~~~~~~~

Mac OS Xにインストールする
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. PIP doesn't know about the Mac OS X Freetype paths. To rectify that:

PIPはMac OS XのFreetypeのパスを特定できません。
それを正すには:

.. code-block:: bash

    $ ln -s /usr/X11/include/freetype2 /usr/local/include/
    $ ln -s /usr/X11/include/ft2build.h /usr/local/include/
    $ ln -s /usr/X11/lib/libfreetype.6.dylib /usr/local/lib/
    $ ln -s /usr/X11/lib/libfreetype.6.dylib /usr/local/lib/libfreetype.dylib

.. then:

それから:

.. code-block:: bash

    $ brew install libjpeg
    $ pip install PIL


.. Installing on Windows
   ~~~~~~~~~~~~~~~~~~~~~

Windowsにインストールする
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. todo::
    Notes on installing on Windows machines


