======================
About Python
======================

:著者: yuhma21

便利なPythonを導入する（for win）
============================================

Pythonで科学技術計算を行うには、
`IPhython Notebook <http://ipython.org/notebook.html>`_
が使いやすい。

**使い方**

#. \ `Python(x,y) <https://code.google.com/p/pythonxy/>`_  をダウンロードしてインストール
#. コマンドプロンプトで、\ **ipython notebook --pylab inline**\を入力すれば起動。
#. 上記のコマンドをbatファイルに書き込めば簡単に起動が可能。 

python(x,y)は2.7系

データ型
========

Pythonにはさまざまなデータ型がある

============  ===============
 Type          detail
============  ===============
 Integet       整数型
 Floats        小数点
 Complex       実数+虚数
 Booleans      真偽
============  ===============


* Integet

.. code-block:: python

   >>> 1 + 1
   2
   >>> a = 4
   >>> type(a)
   <type 'int'>

* Floats

.. code-block:: python

   >>> c = 2.1
   >>> type(c)
   <type 'float'>

* Complex

.. code-block:: python

   >>> a = 1.5 + 0.5j
   >>> a.real
   1.5
   >>> a.imag
   0.5
   >>> type(1. + 0j)
   <type 'complex'>

* Boolean

.. code-block:: python

   >>> 3 > 4
   False
   >>> test = (3 > 4)
   False
   >>> type(test)
   <type 'bool'>

コンテナ
========

配列のようなもの

* リスト
* 辞書
* タプル
* 集合

などがある

また、科学技術計算用にNumpyモジュールの\ **ndarray**\ オブジェクトもある

リスト
--------

大かっこ\ `[]`\ でくくったオブジェクト群の事

**リスト作成の例**

.. code-block:: python

   >>> L = [1, 2, 3, 4]
   >>> s = ['red', 'green', 'yellow']
   >>> L[1]
   2
   >>> s[2]
   'yellow'

**:**\ リテラルを使うことで自由にリストから値を取り出せます。次の例では2つ目の要素からすべて取り出します

.. code-block:: python

   >>> L = [1, 2, 3, 4]
   >>> L[1:]
   [2, 3, 4]

次の例では2,3要素を取り出します。1:3の後半の要素は含みません。

.. code-block:: python

   >>> L = [1, 2, 3, 4]
   >>> L[1:3]
   [2, 3]

後ろからの要素も指定でします。-1番目一番最後の要素になります

.. code-block:: python

   >>> L = [1, 2, 3, 4]
   >>> L[-4]
   1
   >>> L[1:-1]
   [2, 3]

リストの中にリストを入れることもできます\n
下の例は2行4列の配列を作成しています

.. code-block:: python

   >>> L = [[1, 2, 3, 4], [5, 6, 7, 8]]
   >>> L[1]
   [5, 6, 7, 8]
   >>> L[1][2]
   6

L配列の2列だけを取り出したいときは、リスト内包表記で取り出すのが便利です

.. code-block:: python

   >>> L = [[1, 2, 3, 4], [5, 6, 7, 8]]
   >>> [ls[1] for ls in L]
   [2, 6]

スマートでなくても、for文で記述しても構いません

.. code-block:: python

   >>> L2=[]
   >>> for ls in L:
   ...    L1.append(ls[1])
   ...
   >>> L2
   [2, 6] 

リストからの要素の取り出しは、データを扱うに当たって重要な操作になります。慣れておいたほうがよろしいかと思います

リストに関する重要な関数
^^^^^^^^^^^^^^^^^^^^^^^^

.. function:: list.append(x)

   リストの末尾に\ *x*\ を追加します。

.. function:: len(list)

   リストの要素数を返します

.. function:: list.insert(i, x)

   指定した位置iにxを挿入します

.. function:: list.remove(x)

   リスト中でxの値を持つ\ **最初の要素**\ を削除します。

.. function:: list.pop(i)
              list.pop(list)

   リストからi番目の要素を取り出し、削除します。引数としてリスト型の要素も使用できます。

.. function:: list.index(x)

   リストの中で値xを持っている最初の要素のインデックスを返す

.. function:: list.count(x)

   値xがリストに入っている個数を返す

.. function:: list.sort()

   リスト内の要素を昇順に並べる

.. function:: list.reverse()

   リスト内の要素を降順に並べる

**関数の使用例**

.. code-block:: python

   >>> L = [1, 2, 3, 4]
   >>>#最後の要素に5を追加
   >>>L.append(5)
   >>>L
   [1, 2, 3, 4, 5]
   >>> #リストの最後に配列を追加
   >>> L.extend([6, 7, 8])
   >>> L
   [1, 2, 3, 4, 5, 6, 7, 8]
   >>>

