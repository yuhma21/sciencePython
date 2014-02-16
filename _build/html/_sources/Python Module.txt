======================
Python Module
======================

:著者: yuhma21

モジュールを試す
======================

よく使う機能はモジュール化しておくと便利。モジュールはpythonの定義や文が
入ったファイルで、拡張子に\ **.py**\ が入ったものになる。

モジュールを作成する
--------------------

下記のコードをテキストエディタで記述し、fibo.pyで同じプロジェクト内に保存する

.. code-block:: python

   #!/usr/bin/env python
   # -*- coding: utf-8 -*-

   # フィボナッチ数列モジュール

   def fib(n):    # nまでのフィボナッチ級数を出力
       a, b = 0, 1
       while b < n:
           print b,
           a, b = b, a+b

   def fib2(n): # nまでのフィボナッチ級数を返す
       result = []
       a, b = 0, 1
       while b < n:
           result.append(b)
           a, b = b, a+b
       return result

:download:`fibo.py </download/fibo.py>`

作成したモジュールを使う
----------------------------------------

作成したモジュールは\ **import**\ で呼び出して使用します。
*モジュール名=ファイル名*\ になります。

呼び出し方には複数の方法があります。

#. 単純に呼び出す
#. 単純に呼び出し簡単にアクセスする
#. モジュール名を別名にして呼び出す
#. 使用する関数などを直接指定して呼び出す

単純に呼び出す
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

   >>> import fibo
   >>> fibo.fib(500)
   1 1 2 3 5 8 13 21 34 55 89 144 233 377

import モジュール名にすると、モジュール名+関数名で機能を呼び出せます。
同じ名前の関数名があった場合でもpythonインタープリタが迷わずに実行できます。

単純に呼び出し簡単にアクセスする
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

   >>> from fibo import *
   >>> fib(500)
   1 1 2 3 5 8 13 21 34 55 89 144 233 377

上記のように呼び出すと、関数名だけで実行できます。
* はすべての関数を呼び出す。といった記号です。

同じ関数名があった場合にインタープリタが迷う可能性があるので、お勧めしません。


モジュール名を別名として呼び出す
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

   >>> import fibo as fi
   >>> fi.fib(500)
   1 1 2 3 5 8 13 21 34 55 89 144 233 377

名前の長いモジュールを別の名前にします。
matplotlibを利用する場合などによく使いします。

**matplotlibの例**

.. code-block:: python

   >>> import matplotlib.pyplot as plt
   >>> plt.plot([1, 2, 3], [1, 4, 9], 'bo')

使用する関数などを直接指定して呼び出す
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python

   >>> from fibo import fib
   >>> fib(500)
   1 1 2 3 5 8 13 21 34 55 89 144 233 377

上記のように呼び出すと、fib2は実行できません。

下記のように、複数の関数も指定できます

.. code-block:: python

   >>> from fibo import fib, fib2
   >>> fib(500)
   1 1 2 3 5 8 13 21 34 55 89 144 233 377

標準モジュールを利用する
==========================================

Pythonには非常に多くの標準モジュールが搭載されています。その中の一部を紹介します。

組み込み関数
----------------------------------------

**組み込み関数一覧**

=============  ============  =============  ============  ===============
組み込み関数
=============  ============  =============  ============  ===============
abs()          divmod()      input()        open()        staticmethod()
all()          enumerate()   int()          ord()         str()
any()          eval()        isinstance()   pow()         sum()
basestring()   execfile()    issubclass()   print()       super()
bin()          file()        iter()         property()    tuple()
bool()         filter()      len()          range()       type()
bytearray()    float()       list()         raw_input()   unichr()
callable()     format()      locals()       reduce()      unicode()
chr()          frozenset()   long()         reload()      vars()
classmethod()  getattr()     map()          repr()        xrange()
cmp()          globals()     max()          reversed()    zip()
compile()      hasattr()     memoryview()   round()       __import__()
complex()      hash()        min()          set()         apply()
delattr()      help()        next()         setattr()     buffer()
dict()         hex()         object()       slice()       coerce()
dir()          id()          oct()          sorted()      intern()
=============  ============  =============  ============  ===============

**組み込み関数を一部紹介**

.. function:: abs(x)

   値xの絶対値を返す

   .. code-block:: python

      >>> abs(-5)
      5
      >>> abs(1. + 2.j)
      2.23606797749979

.. function:: bin(x)

   整数xを二進数の文字列に変換する

   .. code-block:: python

      >>> bin(10)
      '0b1010'

.. function:: chr(i)

   ASCIIコードがiになるような文字列を返す

   .. code-block:: python

      >>> chr(49)
      '1'
      >>> chr(65)
      'A'

.. function:: dict([arg])

   新しい辞書型のデータを作成する

   .. code-block:: python

      >>> key=['a',　'b',　'c']
      >>> value=[1, 2, 3]
      >>> dict(zip(key, value))
      {'a': 1, 'c': 3, 'b': 2}

.. function:: dir([object])

   objectの持つ名前のリストを返す

   .. code-block:: python

      >>> import __builtin__
      >>> dir(__builtin__)
      ['ArithmeticError', 'AssertionError', 'AttributeError', 
      'BaseException', 'BufferError', 'BytesWarning', 
      'DeprecationWarning', 'EOFError', 'Ellipsis', 'Environme,
      .....................]

   自分の作成したモジュールで試してみましょう

.. function:: float([x])

   文字列を浮動小数点型に変換する

   .. code-block:: python

      >>> float(1)
      1.0
      >>> float('0.01')
      0.01

.. function:: help([object])

   objectの組み込みのヘルプを表示する

   .. code-block:: python

      >>> import os
      >>> help(os)
      Help on module os:

      NAME
          os - OS routines for Mac, NT, or Posix depending on what system we're on.

      FILE
          c:\python27\lib\os.py

      DESCRIPTION
          This exports:
            - all functions from posix, nt, os2, or ce, e.g. unlink, stat, etc.
            - os.path is one of the modules posixpath, or ntpath
            - os.name is 'posix', 'nt', 'os2', 'ce' or 'riscos'
            - os.curdir is a string representing the current directory ('.' or ':')
            - os.pardir is a string representing the parent directory ('..' or '::')
            - os.sep is the (or a most common) pathname separator ('/' or ':' or '\\')
            - os.extsep is the extension separator ('.' or '/')
            - os.altsep is the alternate pathname separator (None or '/')
            - os.pathsep is the component separator used in $PATH etc
            - os.linesep is the line separator in text files ('\r' or '\n' or '\r\n')
            - os.defpath is the default search path for executables
            - os.devnull is the file path of the null device ('/dev/null', etc.)

          Programs that import and use 'os' stand a better chance of being
      -- More  --

