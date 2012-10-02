.. XML parsing
   ===========

XMLのパース
======================

untangle
--------

.. `untangle <http://0chris.com/untangle>`_ is a simple library which takes
   an XML document and returns a Python object which mirrors the nodes and
   attributes in its structure.

`untangle <http://0chris.com/untangle>`_ はXMLドキュメントを取得するシンプルなライブラリで、
構造としてノードとアトリビュートの複製版のPythonオブジェクトを返します。

.. For example, an xml file like this:

例として、xmlファイルは以下のようになります。 :

.. code-block:: xml

    <?xml version="1.0"?>
    <root>
        <child name="child1">
    </root>

.. can be loaded like this:

以下のように読み込むことができます。 :

.. code-block:: python

    import untangle
    obj = untangle.parse('path/to/file.xml')

.. and then you can get the child elements name like this:

そして、以下の様な名前の子要素を取得することができます。 :

.. code-block:: python

    obj.root.child['name']

.. also supports loading XML from a string or an URL.

untangleは文字列やURLからXMLを読み込むことできます。

