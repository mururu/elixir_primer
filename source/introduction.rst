
====================================
Elixirとは
====================================

erlang VM の上で動作する、関数型、メタプログラミング指向のプログラミン
グ言語です。erlang上で動作する同様の言語としては、reia
(http://reia-lang.org/) がありますが、elixirはreiaの後継になります。わ
ざわざ、erlangという、高信頼並列プログラミング言語の上で動作するだけあっ
て、それなりの特徴があります。

近代的なシンタックス 
  ruby風味なので、Prologチックなerlangに比べて取っ付
  きやすくなっています。

全てが式 
  モジュール定義や関数定義、各種ディレクティブなど全てが式です。

強力なメタプログラミング機能 
  homoiconic 構文を持つため、elixriプログラ
  ムはelixirのデータ構造として表現されます。lispのような強力なマクロ機
  構により、コンパイル後の構文木をコード生成の前にプログラムからいじる
  ことができます。ここがerlangはじめ他の関数型言語と一線を画するところ
  です。

第一級オブジェクトしてのドキュメント 
  elixirではドキュメントがファーストクラスオブジェクトして取り扱うこと
  ができます。従って、ソースコード上にコメントを書く必要が著しく低減さ
  れています。ドキュメントは動的に追加、削除でき、iexのようなシェルから
  参照できます。

erlangランタイムとの相互運用 
  erlang/OTPの膨大なライブラリ資産をそのまま呼び出すことができます。
  Java VM上で動作するscalaがjavaのクラスライブラリを呼び出すことができ
  るのと似ています。

ひとことでまとめると、erlangの並列/高信頼フレームワークが利用できる
rubyライクの構文を持つlispです。

ビルドとインストール
--------------------

elixirはerlang/OTPのバージョン16Bかそれ以降が必要ですので、
www.erlang.orgからダウンロードしてインストールしておきます。erlang/OTP
のインストール後、elixirをビルド・インストールします。elixirは、
https://github.com/josevalim/elixir から入手できます。2013年6月時点の最
新版は0.9.3で2011年12月にリリースされた0.4.0から強力なマクロを備えた言
語に生まれ変わりました。それ以前のelixirはreiaと同様にerlang上で動作す
るruby類似のオブジェクト指向言語でした。

.. code-block:: bash
   :linenos:

   $ git clone https://github.com/elixir-lang/elixir.git
   $ cd elixir
   $ make test
   $ bin/elixir -v
   Elixir 0.9.3.dev

インストールはスーパーユーザになりmake install後、パスを通します。

.. code-block:: bash
   :linenos:

   $ sudo make install

Hello, world.
-------------

elixirのプログラムの構造は以下のとおりです。

.. code-block:: elixir
   :linenos:

   defmodule ModuleName do
     def MethodName(arg1, arg2,...) do
       body
     end
   def ShortMethod(arg1), do: body
   end
   ModuleName.MethodName(arg1, arg2,...) ## start point

rubyなどを知っていれば受け入れやすい文法と構造になっています。では最初
のプログラムを書いてみましょう。

.. literalinclude:: ../codes/hello.exs
   :language: elixir
   :linenos:

これをhello.exsとして保存し、elixirへ渡すと実行されます。

.. literalinclude:: ../codes/hello.lst
   :language: bash
   :linenos:


