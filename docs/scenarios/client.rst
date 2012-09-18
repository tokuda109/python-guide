.. Network Applications
   ====================

ネットワークアプリケーション
========================================

HTTP
::::

.. The Hypertext Transfer Protocol (HTTP) is an application protocol for
   distributed, collaborative, hypermedia information systems. HTTP is the
   foundation of data communication for the World Wide Web.

Hypertext Transfer Protocol (HTTP) は、
分散されているが協調的なハイパーメディア情報システムのためのアプリケーションプロトコルです。
HTTPはWorld Wide Webのデータ通信の基盤となっています。

.. Requests
   --------

リクエスト
----------------

.. Python’s standard urllib2 module provides most of the HTTP capabilities you
   need, but the API is thoroughly broken. It was built for a different time —
   and a different web. It requires an enormous amount of work (even method
   overrides) to perform the simplest of tasks.

Pythonのurllib2モジュールは、必要とされるほとんどのHTTPの機能を備えていますがAPIがめちゃくちゃです。
何回も修正され、異なる目的に対しても修正されてきました。
簡単なタスクを行うためにかなりの量の作業を必要とします(メソッドを上書きするのでさえ)。

.. Requests takes all of the work out of Python HTTP — making your integration
   with web services seamless. There’s no need to manually add query strings to
   your URLs, or to form-encode your POST data. Keep-alive and HTTP connection
   pooling are 100% automatic, powered by urllib3, which is embedded within
   Requests.

Requestsは、ウェブサービスとシームレスに統合され、PythonのHTTPの全ての処理を受け持ちます。
URLにクエリ文字列を手動で追加したり、POSTデータをフォームエンコードしたりする必要はありません。
キープアライブとHTTP接続は、Requestsに入っているurllib3によって100%自動でプーリングされます。

- `ドキュメント <http://docs.python-requests.org/en/latest/index.html>`_
- `PyPi <http://pypi.python.org/pypi/requests>`_
- `GitHub <https://github.com/kennethreitz/requests>`_


.. Distributed Systems
   ::::::::::::::::::::

分散システム
:::::::::::::::::::::::

ZeroMQ
------

.. ØMQ (also spelled ZeroMQ, 0MQ or ZMQ) is a high-performance asynchronous
   messaging library aimed at use in scalable distributed or concurrent
   applications. It provides a message queue, but unlike message-oriented
   middleware, a ØMQ system can run without a dedicated message broker. The
   library is designed to have a familiar socket-style API.

ØMQ (ZeroMQ、0MQ、ZMQというスペルでもあります)は、スケール可能な分散アプリケーションや同時実行するアプリケーションで使うことを目的としたハイパフォーマンスの非同期メッセージングライブラリです。
これにはメッセージキューが備えられているが、メッセージを主体としたミドルウェアと違って、ØMQシステムは専用のメッセージブローカーなしでも実行可能です。
ライブラリはソケットに似たAPIを持つように設計されています。
