.. ================
   Web Applications
   ================

================================
ウェブアプリケーション
================================

.. As a powerful scripting language adapted to both fast prototyping
   and bigger projects, Python is widely used in Web applications
   development.

強力なスクリプト言語は早くプロトタイプを作成することと大きなプロジェクトの両方に対応していて、
Pythonはウェブアプリケーションの開発で広く使われています。

.. Context
   :::::::

コンテキスト
::::::::::::::


WSGI
----

.. The Web Server Gateway Interface (or "WSGI" for short) is a standard
   interface between web servers and Python web application frameworks. By
   standardizing behavior and communication between web servers and Python web
   frameworks, WSGI makes it possible to write portable Python web code that
   can be deployed in any :ref:`WSGI-compliant web server <wsgi-servers-ref>`.
   WSGI is documented in `PEP-3333 <http://www.python.org/dev/peps/pep-3333/>`_.

Web Server Gateway Interface(省略して”WSGI”)は、
ウェブサーバーとPythonウェブアプリケーションフレームワーク間の標準的なインターフェースです。
ウェブサーバーとPythonウェブフレームワークとの間の振る舞いややり取りを共通化することで、
持ち運び可能なPythonのコードを書くことが可能になり、
:ref:`WSGIに対応した任意のウェブサーバー <wsgi-servers-ref>` にデプロイすることができます。
`PEP-3333 <http://www.python.org/dev/peps/pep-3333/>`_ でドキュメント化されています。


.. Frameworks
   ::::::::::

フレームワーク
::::::::::::::::::::

.. Broadly speaking, a web framework consist of a set of libraries and a main
   handler within which you can build custom code to implement a web application
   (i.e. an interactive web site). Most web frameworks include patterns and
   utilities to accomplish at least the following:

大まかに言うと、ウェブフレームワークはウェブアプリケーションを実装するための処理を独自のコードを書くためのライブラリから成ります。
ほとんどのウェブフレームワークはパターンがあって、少なくとも以下のことができるようなツールがあります。 :

.. URL Routing
     Matches an incoming HTTP request to a particular piece of Python code to
     be invoked

URLルーティング
  HTTPリクエストされたものと呼び出されるべきPythonの特定のコードとのマッチングを行う。

.. Request and Response Objects
     Encapsulate the information received from or sent to a user's browser

リクエストとレスポンスオブジェクト
  ユーザーのブラウザから送られてきた情報を受け取ってカプセル化する。

Template Engine
  Allows for separating Python code implementing an application's logic from
  the HTML (or other) output that it produces

Development Web Server
  Runs an HTTP server on development machines to enable rapid development;
  often automatically reloads server-side code when files are updated


Django
------

`Django <http://www.djangoproject.com>`_ is a "batteries included" web
application framework. By providing many utilities and patterns out of the
box, Django aims to make it possible to build complex, database-backed web
applications quickly, while encouraging best practices in code written using
it.

Django has a large and active community, and many pre-built `re-usable
modules <http://djangopackages.com/>`_ that can be incorporated into a new
project as-is, or customized to fit your needs.

There are annual Django conferences `in the United States
<http://djangocon.us>`_ and `in Europe <http://djangocon.eu>`_.


Flask
-----

`Flask <http://flask.pocoo.org/>`_ is a "microframework" for Python. Rather
than aiming to provide everything you could possibly need, Flask implements
the most commonly-used core components of a web application framework, like
URL routing, request and response objects, and templates. As a user of
Flask, it is therefore up to you to choose and integrate other components
you may need, such as database access or form generation and validation. For
many popular modules, `Extensions <http://flask.pocoo.org/extensions/>`_ may
already exist to suit your needs.

**Support** for flask can best be found in its mailing list. Just shoot an
email to flask@librelist.com and reply to the confirmation email.


.. todo:: Explain Pyramid


Web Servers
:::::::::::

.. _nginx-ref:

Nginx
-----

`Nginx <http://nginx.org/>`_ (pronounced "engine-x") is a web server and
reverse-proxy for HTTP, SMTP and other protocols. It is known for its
high performance, relative simplicity, and compatibility with many
application servers (like WSGI servers). It also includes handy features
like load-balancing, basic authentication, streaming, and others. Designed
to serve high-load websites, Nginx is gradually becoming quite popular.


.. _wsgi-servers-ref:

WSGI Servers
::::::::::::

Stand-alone WSGI servers typically use less resources than traditional web
servers and provide top performance [3]_.

.. _gunicorn-ref:

Gunicorn
--------

`Gunicorn <http://gunicorn.org/>`_ (Green Unicorn) is a WSGI server used
to serve Python applications. It is a Python interpretation of the Ruby
`Unicorn <http://unicorn.bogomips.org/>`_ server. Unicorn is designed to be
lightweight, easy to use, and uses many UNIX idioms. Gunicorn is not designed
to face the internet, in fact it was designed to run behind Nginx which buffers
slow requests, and takes care of other important considerations. A sample
setup for Nginx + gUnicorn can be found in the
`Gunicorn help <http://gunicorn.org/deploy.html>`_.

.. _uwsgi-ref:


Server Best Practices
:::::::::::::::::::::

The majority of self hosted Python applications today are hosted with a WSGI
server such as :ref:`gUnicorn <gunicorn-ref>`, either directly or behind a
lightweight web server such as :ref:`nginx <nginx-ref>`.

The WSGI servers serve the Python applications while the web server handles
tasks better suited for it such as static file serving, request routing, DDoS
protection, and basic authentication.

.. Hosting
   :::::::

ホスティング
:::::::::::::::::::::

Platform-as-a-Service
---------------------

Platform-as-a-Service (PaaS) is a type of cloud computing infrastructure
which abstracts and manages infrastructure, routing, and scaling of web
applications. When using PaaS, application developers can focus on writing
application code rather than needing to be concerned with deployment
details.

Most PaaS services offer a command-line interface that developers can use to
set up and interrogate configuration, and to deploy new releases of an
application to the service.

PaaS services and their partners offer add-on functionality which is well
integrated into the platform, such as database hosting, email services,
logging, scheduled and background tasks, billing and payment, etc.


Heroku
~~~~~~

`Heroku <http://www.heroku.com/>`_'s
`Cedar stack <http://devcenter.heroku.com/articles/cedar>`_ offers first class
support for Python 2.7 applications.

Heroku allows you to run as many Python web applications as you like, 24/7 and
free of charge. Heroku is best described as a horizontal scaling platform. They
start to charge you once you "scale" you application to run on more than one
Dyno (abstracted servers) at a time.

Heroku publishes `step-by-step instructions
<http://devcenter.heroku.com/articles/python>`_ on how to set up your first
application for use in Heroku, and maintains a list of `example applications
<http://python.herokuapp.com/>`_.


DotCloud
~~~~~~~~

.. `DotCloud <http://www.dotcloud.com/>`_ supports WSGI applications and
   background/worker tasks natively on their platform. Web applications running
   Python version 2.6, and uses :ref:`nginx <nginx-ref>` and :ref:`uWSGI
   <uwsgi-ref>`, and allows custom configuration of both
   for advanced users.

`DotCloud <http://www.dotcloud.com/>`_ は、WSGIアプリケーションとプラットフォーム上でバックグランドとワーカーのタスクを最初からサポートしています。
ウェブアプリケーションはPython 2.6、 :ref:`nginx <nginx-ref>` 、 :ref:`uWSGI <uwsgi-ref>` で実行され、設定を変更することができます。

.. DotCloud uses a custom command-line API client which can work with
   applications managed in git repositories or any other version control
   system.

DotCloudは、gitレポジトリや他の任意のバージョン管理システムで管理されているアプリケーションを作業するための独自のコマンドラインAPIを使うことができます。

.. DotCloud has a free plan with limited database size, and without extra
   services (caching…).

DotCloudはデータベース容量の制限や他のサービス(キャッシュ等)がない無料プランがあります。

.. See the `DotCloud documentation on Python
   <http://docs.dotcloud.com/services/python/>`_ for more information and help
   getting started.

使うためのヘルプやより詳しい情報を見る場合は、
`DotCloudのPythonドキュメント <http://docs.dotcloud.com/services/python/>`_ で確認して下さい。


Gondor
~~~~~~

.. `Gondor <https://gondor.io/>`_ is a PaaS specailized for deploying Django
   and Pinax applications. Gondor supports Django versions 1.2 and 1.3 on
   Python version 2.7, and can automatically configure your Django site if you
   use ``local_settings.py`` for site-specific configuration information.

`Gondor <https://gondor.io/>`_ はDjangoやPinaxのアプリケーションをデプロイするのに特化したPaaSです。
Gondorは、Pythonのバージョン2.7でDjangoのバージョン1.2と1.3をサポートしています。そして、
サイトの仕様が定義されている ``local_settings.py`` を使ってDjangoのサイトを自動で設定することができます。

.. Gondor publishes guides to deploying `Django projects
   <https://gondor.io/support/setting-up-django/>`_ and `Pinax projects
   <https://gondor.io/support/setting-up-pinax/>`_ on their platform.

Gondorは、Gondorプラットフォームに `Djangoプロジェクト <https://gondor.io/support/setting-up-django/>`_ と `Pinaxプロジェクト <https://gondor.io/support/setting-up-pinax/>`_ をデプロイするためのガイドを公開しています。

Templating
::::::::::

Most WSGI applications are responding to HTTP requests to serve
content in HTML or other markup languages. Instead of generating directly
textual content from Python, the concept of separation of concerns
advises us to use templates. A template engine manage a suite of
template files, with a system of hierarchy and inclusion to
avoid unnecessary repetition, and is in charge of rendering
(generating) the actual content, filling the static content
of the templates with the dynamic content generated by the
application.

As template files are
sometimes written by designers or front-end developers,
it can be difficult to handle increasing complexity.

Some general good practices apply to the part of the
application passing dynamic content to the template engine,
and to the templates themselves.

- Template files should be passed only the dynamic
  content that is needed for rendering the template. Avoid
  to be tempted to pass additional content "just in case":
  it is easier to add some missing variable when needed than to remove
  a likely unused variable later.

- Many template engines allow for complex statements
  or assignments in the template itself, and many
  allow some Python code to be evaluated in the
  templates. This convenience can lead to uncontrolled
  increase in complexity, and often harder to find bugs.

- It is often possible or necessary to mix javascript templates with
  HTML templates. A sane approach to this design is to isolate
  the parts where the HTML template passes some variable content
  to the javascript code.

.. rubric:: References

.. [1] `The mod_python project is now officially dead <http://blog.dscpl.com.au/2010/06/modpython-project-is-now-officially.html>`_
.. [2] `mod_wsgi vs mod_python <http://www.modpython.org/pipermail/mod_python/2007-July/024080.html>`_
.. [3] `Benchmark of Python WSGI Servers <http://nichol.as/benchmark-of-python-web-servers>`_
