.. Testing Your Code
   =====================

コードのテスト
========================

.. Testing your code is very important.

コードをテストすることはとても大事です。

Getting used to writing the testing code and the running code in parallel is
now considered a good habit. Used wisely, this method helps you define more
precisely your code's intent and have a more decoupled architecture.

.. Some general rules of testing:

テストには一般的なルールがいくつかあります。 :

- A testing unit should focus on one tiny bit of functionality and prove it
  correct.

- Each test unit must be fully independent. Each of them must be able to run
  alone, and also within the test suite, regardless of the order they are called.
  The implication of this rule is that each test must be loaded with a fresh
  dataset and may have to do some cleanup afterwards. This is usually
  handled by setUp() and tearDown() methods.

- Try hard to make tests that run fast. If one single test needs more than a
  few millisecond to run, development will be slowed down or the tests will not
  be run as often as desirable. In some cases, test can't be fast because they
  need a complex data structure to work on, and this data structure must be
  loaded every time the test runs. Keep these heavier tests in a separate test
  suite that is run by some scheduled task, and run all other tests as often
  as needed.

- Learn your tools and learn how to run a single test or a test case. Then,
  when developing a function inside a module, run this function's tests very
  often, ideally automatically when you save the code.

- Always run the full test suite before a coding session, and run it again
  after. This will give you more confidence that you did not break anything in
  the rest of the code.

- It is a good idea to implement a hook that runs all test before pushing code
  to a shared repository.

- If you are in the middle of a development and have to interrupt your work, it
  is a good idea to write a broken unit test about what you want to develop next.
  When coming back to work, you will have a pointer to where you were and get
  faster on tracks.

- The first step when you are debugging your code is to write a new test
  pinpointing the bug. While it is not always possible to do, those bug
  catching test are among the most valuable piece of code in your project.

- Use long and descriptive names for testing functions. The style guide here is
  slightly different than that of running code, where short names are often
  preferred. The reason is testing functions are never called explicitly.
  ``square()`` or even ``sqr()`` is ok in running code, but in testing code you
  would has names such as ``test_square_of_number_2()``,
  ``test_square_negative_number()``. These function names are displayed when a
  test fail, and should be as descriptive as possible.

- When something goes wrong or has to be changed, and if your code has a good
  set of tests, you or other maintainers will rely largely on the testing suite
  to fix the problem or modify a given behavior. Therefore the testing code will
  be read as much as or even more than the running code. A unit test whose
  purpose is unclear is not very helpful is this case.

- Another use of the testing code is as an introduction to new developers. When
  someone will have to work on the code base, running and reading the related
  testing code is often the best they can do. They will or should discover the
  hot spots, where most difficulties arise, and the corner cases. If they have
  to add some functionality, the first step should be to add a test and, by this
  mean, ensure the new functionality is not already a working path that has not
  been plugged in the interface.

The Basics
::::::::::


Unittest
--------

Unittest is the batteries-included test module in the Python standard library.
Its API will be familiar to anyone who has used any of the JUnit/nUnit/CppUnit
series of tools.

Creating testcases is accomplished by subclassing a TestCase base class

::

    import unittest

    def fun(x):
        return x + 1

    class MyTest(unittest.TestCase):
        def test(self):
            self.assertEqual(fun(3), 4)

As of Python 2.7 unittest also includes its own test discovery mechanisms.

    `unittest in the standard library documentation <http://docs.python.org/library/unittest.html>`_


Doctest
-------

The doctest module searches for pieces of text that look like interactive
Python sessions in docstrings, and then executes those sessions to verify that
they work exactly as shown.

Doctests have a different use case than proper unit tests: they are usually
less detailed and don't catch special cases or obscure regression bugs. They
are useful as an expressive documentation of the main use cases of a module and
its components. However, doctests should run automatically each time the full
test suite runs.

A simple doctest in a function:

::

    def square(x):
        """Squares x.

        >>> square(2)
        4
        >>> square(-2)
        4
        """

        return x * x

    if __name__ == '__main__':
        import doctest
        doctest.testmod()

When running this module from the command line as in ``python module.py``, the
doctests will run and complain if anything is not behaving as described in the
docstrings.

Tools
:::::


py.test
-------

py.test is a no-boilerplate alternative to Python's standard unittest module.

::

    $ pip install pytest

Despite being a fully-featured and extensible test tool it boasts a simple
syntax. Creating a test suite is as easy as writing a module with a couple of
functions

::

    # content of test_sample.py
    def func(x):
        return x + 1

    def test_answer():
        assert func(3) == 5

and then running the `py.test` command

::

    $ py.test
    =========================== test session starts ============================
    platform darwin -- Python 2.7.1 -- pytest-2.2.1
    collecting ... collected 1 items

    test_sample.py F

    ================================= FAILURES =================================
    _______________________________ test_answer ________________________________

        def test_answer():
    >       assert func(3) == 5
    E       assert 4 == 5
    E        +  where 4 = func(3)

    test_sample.py:5: AssertionError
    ========================= 1 failed in 0.02 seconds =========================

far less work than would be required for the equivalent functionality with the
unittest module!

    `py.test <http://pytest.org/latest/>`_


Nose
----

.. nose extends unittest to make testing easier.

Noseはテストをより簡単にするためにUnittestを拡張します。

::

    $ pip install nose

nose provides automatic test discovery to save you the hassle of manually
creating test suites. It also provides numerous plugins for features such as
xUnit-compatible test output, coverage reporting, and test selection.

    `nose <http://readthedocs.org/docs/nose/en/latest/>`_


tox
---

.. tox is a tool for automating test environment management and testing against
   multiple interpreter configurations

toxは、自動テスト環境の管理や複数のインタープリターに対してテストの設定をするためのツールです。

::

    $ pip install tox

.. tox allows you to configure complicated multi-parameter test matrices via a
   simple ini-style configuration file.

toxは、複雑な設定することができます。

    `tox <http://tox.testrun.org/latest/>`_

Unittest2
---------

unittest2 is a backport of Python 2.7's unittest module which has an improved
API and better assertions over the one available in previous versions of Python.

If you're using Python 2.6 or below, you can install it with pip

::

    $ pip install unittest2

You may want to import the module under the name unittest to make porting code
to newer versions of the module easier in the future

::

    import unittest2 as unittest

    class MyTest(unittest.TestCase):
        ...

This way if you ever switch to a newer python version and no longer need the
unittest2 module, you can simply change the import in your test module without
the need to change any other code.

    `unittest2 <http://pypi.python.org/pypi/unittest2>`_


