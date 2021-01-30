#### 【オンライン開催】Burikaigi2021

- - -

## Ruby 2.0 から Ruby 3.0 を
## 駆け足で振り返る

---

### 気になる点やわからない点があれば
### Zoom の質問にどんどん書いてね！！
 
---

#### アジェンダ
- - -

* 自己紹介
* Ruby とは
* Ruby 2.0 以前の歴史
* Ruby 2.0 ~ 3.0 までを振り返る
    * どういう機能が追加されてきたのかを振り返ってみる
* 最近のモダンな機能紹介・デモ
    * Ruby 2.7, 3.0 の機能紹介
* まとめ

---

#### 自己紹介
- - -

* 名前：osyo
* Twitter : [@pink_bangbi](https://twitter.com/pink_bangbi)
* github  : [osyo-manga](https://github.com/osyo-manga)
* ブログ  : [Secret Garden(Instrumental)](http://secret-garden.hatenablog.com)
* 趣味で Ruby にパッチを投げている                     <!-- .element: class="fragment" -->
    * Ruby 2.5 ~ 3.0 まで何らかのパッチ投げてるぞい…
* Ruby 基礎文法最速マスターって記事を書いたので Ruby が気になる人は読んでみてね！！！                     <!-- .element: class="fragment" -->
    * [令和時代の Ruby 基礎文法最速マスター](https://secret-garden.hatenablog.com/entry/2020/12/01/232816)
* オンライン勉強会が多いので去年はあちこちの勉強会に参加                      <!-- .element: class="fragment" -->
<br>
    * [Fukuoka.rb](https://fukuokarb.connpass.com/)
[Hamada.rb](https://hamadarb.connpass.com/)
[kawasaki.rb](https://kawasakirb.connpass.com/)
[nikotama.rb](https://nikotamarb.connpass.com/)
[Sendai.rb](https://sendairb.connpass.com/)
[Shibuya.rb](https://shibuyarb.connpass.com/)
[Shinjuku.rb](https://shinjukurb.connpass.com/)
[Tama.rb](https://tamarb.connpass.com/)
[Toyama.rb](https://toyamarb.connpass.com/)
[Gotanda.rb](https://gotanda-rb.connpass.com/)
[Entaku.rb](https://entakurb.doorkeeper.jp/)
[Grow.rb](https://growrb.doorkeeper.jp/)
[Hamamatsu.rb](https://hmrb.doorkeeper.jp/)
[kanazawa.rb](https://kzrb.doorkeeper.jp/)
[Kobe.rb](https://koberb.doorkeeper.jp/)
[Machida.rb](https://machidarb.doorkeeper.jp/)
[mitaka.rb](https://mitakarb.doorkeeper.jp/)
[Ruby Tuesday](https://ruby-tuesday.doorkeeper.jp/)
[toruby](https://toruby.doorkeeper.jp/)
[西日暮里.rb](https://nishinipporirb.doorkeeper.jp/)
<br>

---

#### わたしと Ruby
- - -

* Ruby 1.8,1.9：はじめて Ruby を知る                     <!-- .element: class="fragment" -->
    * `eval` こわい、と思っていた記憶
* Ruby 2.1：初めて Ruby を書き始める                     <!-- .element: class="fragment" -->
    * チャットボットを Ruby でつくってた
* Ruby 2.2：Ruby をガッツリ触り始める                     <!-- .element: class="fragment" -->
    * メタプログラミングで遊びまくっていた
* Ruby 2.4：Ruby 本体にパッチを投げ始める                     <!-- .element: class="fragment" -->
    * 開発中の Ruby 2.5 に投げた[メソッド追加のパッチ](https://bugs.ruby-lang.org/issues/14142)が取り込まれた
* Ruby 2.5：お仕事で Ruby を使い始める                     <!-- .element: class="fragment" -->
    * ここで初めて Rails を本格的に使い始める
* Ruby 2.6, 2.7, 3.0：毎バージョンごとにパッチを投げる                     <!-- .element: class="fragment" -->
    * 最近は細々したバグ修正パッチが多い…
* 最近：気になった Ruby の開発チケットをブログにまとめたりしてる                     <!-- .element: class="fragment" -->
    * https://secret-garden.hatenablog.com/archive/category/bugs.ruby

---

## Ruby とは

---

#### [Ruby とは](https://www.ruby-lang.org/ja/about/#fn2)
- - -

* まつもとゆきひろ（通称:matz）が開発したオブジェクト指向言語                     <!-- .element: class="fragment" -->
    * 強い動的型付け言語
    * Perl や Smalltalk、Lisp の影響を受けている
    * プリミティブな型も含めてすべてがオブジェクトとして扱われる
* コードを書いていて『楽しい・気持ちがいい』をコンセプトに言語設計されている                     <!-- .element: class="fragment" -->
* MRI（Matz Ruby Interpreter）がいわゆる Ruby と呼ばれる処理系                     <!-- .element: class="fragment" -->
    * 他には JVM 上で動作する JRuby や 組み込み向けの軽量な mruby などが存在している
* 実務では主に Web フレームワークの Ruby on Rails で利用されている                     <!-- .element: class="fragment" -->
* Ruby は死んだ？                     <!-- .element: class="fragment" -->
    * まだ生きてるよ！！
* 去年の 2020年12月25日に Ruby 3.0 がリリース                     <!-- .element: class="fragment" -->

---

## Ruby 2.0 以前の歴史

---

#### Ruby 2.0 以前の歴史
- - -

* 1993年：Ruby が誕生(開発が開始)                     <!-- .element: class="fragment" -->
* 1995年：Ruby が発表                     <!-- .element: class="fragment" -->
* 1996年：Ruby 1.0 がリリース                     <!-- .element: class="fragment" -->
* 2003年：Ruby 1.8 がリリース                     <!-- .element: class="fragment" -->
* 2004年：Ruby on Rails が公開                     <!-- .element: class="fragment" -->
* 2005年：Ruby on Rails 1.0 がリリース                     <!-- .element: class="fragment" -->
* 2007年：Ruby 1.9.0 がリリース                     <!-- .element: class="fragment" -->
    * ここで初めて YARV と呼ばれる仮想マシンが導入された
    * 1.8 までは AST をインタラクティブに実行していた
    * 1.9 からはバイトコードに置き換えて実行している
* 2009年：Ruby 1.9.1 がリリース                     <!-- .element: class="fragment" -->
    * 1.9 系の初めての安定版
* 2011年：JIS規格（JIS X 3017）が制定                     <!-- .element: class="fragment" -->
* 2012年：ISO/IEC規格（ISO/IEC 30170）として承認                     <!-- .element: class="fragment" -->
* 2013年：Ruby 2.0 がリリース                     <!-- .element: class="fragment" -->

---

## Ruby 2.0 ~ 3.0 までを振り返る

---

#### Ruby 2.0
- - -

* [2013/02/24 にリリース](https://www.ruby-lang.org/ja/news/2013/02/24/ruby-2-0-0-p0-is-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.0.0)
* キーワード引数の追加    <!-- .element: class="fragment" -->

    ```ruby
    # ラベル: でキーワード引数を定義
    def log(msg, level: "ERROR")
      puts "[#{ level }] #{ msg }"
    end
    log("OK")                   # => [ERROR] OK
    log("NG", level: "WARNING") # => [WARNING] NG
    ```
    <!-- .element: class="fragment" -->

* 正規表現エンジンとして鬼車の fork である Onigumo(鬼雲) を採用    <!-- .element: class="fragment" -->
* デフォルトのスクリプトエンコーディングが UTF-8 に変更    <!-- .element: class="fragment" -->
    * 以前は US-ASCII だった
* デバッグ用のトレース機能として TracePoint API が追加    <!-- .element: class="fragment" -->
    * クラスが定義されたときやメソッドが呼ばれたタイミングなどで任意の処理をフックすることができる機能
    * この機能を利用して profile などが実装されている

>>>

#### Ruby 2.0 続き
- - -

* 継承リストの先頭にモジュールを追加する `Module#prepend` メソッドが追加

    ```ruby
    module NameIs
      def name
        "name is #{super}"
      end
    end

    class Homu
      # prepend すると先に NameIs のメソッドが呼ばれる
      prepend NameIs
      def name
        "homu"
      end
    end

    # Homu の継承リスト
    p Homu.ancestors  # => [NameIs, Homu, Object, Kernel, BasicObject]
    p Homu.new.name   # => "name is homu"
    ```

>>>

#### Ruby 2.0 続き
- - -

* Refinements が実験的に実装
    * 特定のファイルでのみクラス拡張が反映される

```ruby
module StringEx
  # refine を使って String に新しいメソッドを定義する
  refine String do
    def twice
      self + self
    end
  end
end

# using したファイルでのみ String#twice が使える
using StringEx

p "homu".twice
```

* 参照
    * [Ruby 2.0.0 リリース特集](https://magazine.rubyist.net/articles/0041/0041-200Special.html)
    * [Ruby 2.0.0 の注意点やその他の新機能](https://magazine.rubyist.net/articles/0041/0041-200Special-note.html)


---

#### Ruby 2.1
- - -

* [2013/12/25 にリリース](https://www.ruby-lang.org/ja/news/2013/12/25/ruby-2-1-0-is-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.1対.0)
* Ruby 2.0 で実験的に追加された Refinements が正式に採用      <!-- .element: class="fragment" -->
    * ファイルだけではなくて class の中でも using できるようになった
* キーワード引数でデフォルト値を省略できるように変更    <!-- .element: class="fragment" -->
    * Ruby 2.0 ではデフォルト値が必須だった
* 新しい整数リテラルとして r と i が追加    <!-- .element: class="fragment" -->

    ```ruby
    p 42r.class  # => Rational
    p 42i.class  # => Complex
    ```
    <!-- .element: class="fragment" -->

* メソッドを定義する def がメソッド名のシンボルを返すように変更          <!-- .element: class="fragment" -->

    ```ruby
    method_name = def twice(value:)
      value + value
    end
    p method_name # => :twice
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照：[NEWS for Ruby 2.1.0 (Ruby 3.0.0 リファレンスマニュアル)](https://docs.ruby-lang.org/ja/latest/doc/news=2f2_1_0.html)</p>

---

#### Ruby 2.2
- - -

* [2014/12/25 にリリース](https://www.ruby-lang.org/ja/news/2014/12/25/ruby-2-2-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.2.0)
* シンボルのガベージコレクトを実装    <!-- .element: class="fragment" -->
    * 以前はシンボルが解放されずに残ったままになり、大量にリクエストが投げられて新しいシンボルが生成され続けてメモリが枯渇する問題があった
    * 参照：[(翻訳) Ruby 2.2 のシンボル GC](https://fiveteesixone.lackland.io/2015/01/21/symbol-gc-ruby-2-2/)
* nil / true / false オブジェクトが frozen 化    <!-- .element: class="fragment" -->
* Hash リテラルのキーでクオートが使えるように変更    <!-- .element: class="fragment" -->

    ```ruby
    { "hoge": 1 }
    # => {:hoge=>1}

    { "#{"foo" + "bar"}": 1 }
    # => {:foobar=>1}
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照：[NEWS for Ruby 2.2.0 (Ruby 3.0.0 リファレンスマニュアル)](https://docs.ruby-lang.org/ja/latest/doc/news=2f2_2_0.html)</p>

---

#### Ruby 2.3
- - -

* [2015/12/25 にリリース](https://www.ruby-lang.org/ja/news/2015/12/25/ruby-2-3-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.3.0)
* Frozen String Literal プラグマコメントが追加    <!-- .element: class="fragment" -->

    ```ruby
    # frozen_string_literal: true

    # 文字列リテラルがデフォルトで frozen 化される
    p "hoge".frozen?  # => true
    ```
    <!-- .element: class="fragment" -->

* safe navigation operator(通称ぼっち演算子 &. )が追加    <!-- .element: class="fragment" -->

    ```ruby
    # レシーバが nil の場合はメソッドは呼ばれずに nil を返す
    p nil&.hoge       # => nil
    ```
    <!-- .element: class="fragment" -->

* did_you_mean gem が標準ライブラリに追加    <!-- .element: class="fragment" -->

  ```ruby
  p "hoge".cahrs
  # output:
  # error: undefined method `cahrs' for "hoge":String (NoMethodError)
  # Did you mean?  chars
  #                chr
  ```
  <!-- .element: class="fragment" -->

>>>

#### Ruby 2.3 続き
- - -

* Hash#dig / Array#dig メソッドが追加    <!-- .element: class="fragment" -->

    ```ruby
    user = { address: { tel: [111, 2222, 3333] } }

    # ネストしてる値を 1回で取得する
    # user[:address][:tel][2] を dig メソッドで取得できる
    p user.dig(:address, :tel, 2)   # => 3333

    # キーがない場合はその時点で探索を終了して nil を返す
    p user.dig(:address, :tel2, 2)   # => nil
    ```
    <!-- .element: class="fragment" -->

* インデントを取り除いてくれるヒアドキュメントの記法が追加    <!-- .element: class="fragment" -->

    ```ruby
    # ヒアドキュメント内でインデントしても先頭のインデントのスペースは追加されない
    str = <<~EOS
      homu
      mami
        saya
      mado
    EOS
    p str.split("\n")
    # => ["homu", "mami", "  saya", "mado"]
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照: [サンプルコードでわかる！Ruby 2.3の主な新機能](https://qiita.com/jnchito/items/0faac073cb77417d61c7)</p>


---

#### Ruby 2.4
- - -

* [2016/12/25 にリリース](https://www.ruby-lang.org/ja/news/2016/12/25/ruby-2-4-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.4.0)
* ハッシュテーブルの内部実装が変更されて高速化された          <!-- .element: class="fragment" -->
    * 詳細：[PHPとPythonとRubyの連想配列のデータ構造が同時期に同じ方針で性能改善されてた話 - hnwの日記](https://hnw.hatenablog.com/entry/2021/01/10/162018)
* Fixnum クラスと Bignum クラスが Integer クラスに統合           <!-- .element: class="fragment" -->
    * 基本的に整数は Fixnum で扱われているが極端に値が大きい、小さい時に Bignum を利用していた
* コード上で対話環境を起動することができる binding.irb が実装          <!-- .element: class="fragment" -->

    ```ruby
    def plus(a, b)
      result = a + b

      # この処理が呼ばれた時に対話環境が起動する
      # 対話環境内でローカル変数などが参照できる
      binding.irb

      return result
    end
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照：[サンプルコードでわかる！Ruby 2.4の新機能と変更点](https://qiita.com/jnchito/items/9f9d45581816f121af07)</p>

---

#### Ruby 2.5
- - -

* [2017/12/25 にリリース](https://www.ruby-lang.org/ja/news/2017/12/25/ruby-2-5-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.5.0)
* pp が自動ロードされるように変更    <!-- .element: class="fragment" -->
    * require "pp" と書かずによくなった
* rescue/else/ensure が do/end ブロック内にも直接書けるように変更    <!-- .element: class="fragment" -->
    ```ruby
    # do ~ ensure ~ end をまとめてかける
    hoge do
      # ...
    ensure
      # ...
    end
    ```
    <!-- .element: class="fragment" -->

* トップレベルの定数探索の仕組みが変更     <!-- .element: class="fragment" -->

  ```ruby
  class User; end
  class Address; end

  # 2.4 まではトップレベルの定数まで探索されてしまっていた
  p Address::User
  # 2.4 => User
  # 2.5 => error: uninitialized constant Address::User (NameError)
  ```
  <!-- .element: class="fragment" -->

>>>

#### Ruby 2.5 続き
- - -

* Kernel#yield_self メソッドが追加     <!-- .element: class="fragment" -->

    ```ruby
    # レシーバを受け取ってブロックの結果を返すメソッド
    p 42.yield_self { |a| a.to_s + a.to_s }
    # => "4242"
    ```
    <!-- .element: class="fragment" -->

* Hash#slice メソッドが追加          <!-- .element: class="fragment" -->

    ```ruby
    homu = { id: 1, name: "homu", age: 14 }

    # 指定したキーの要素のみを返す
    p homu.slice(:name, :age)
    # => {:name=>"homu", :age=>14}
    ```
    <!-- .element: class="fragment" -->

* キーワード引数で Struct の初期化ができるように設定を追加          <!-- .element: class="fragment" -->

    ```ruby
    # keyword_init: true にすると
    User = Struct.new(:name, :age, keyword_init: true)

    # ここでキーワード引数を使って初期化できる
    homu = User.new(name: "homu", age: 14)
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照：[サンプルコードでわかる！Ruby 2.5の主な新機能と変更点 Part 1](https://qiita.com/jnchito/items/f182b6f0093a6a3701a1)</p>

---

#### Ruby 2.6
- - -

* [2018/12/25 にリリース](https://www.ruby-lang.org/ja/news/2018/12/25/ruby-2-6-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.6.0)
* 終端なし Range リテラルを追加        <!-- .element: class="fragment" -->
    * `(1..)` のように終端を省略して Range リテラルを定義できる
* JIT コンパイラが導入        <!-- .element: class="fragment" -->
    * 自動的に YARV のバイトコードからバイナリコードに変換して高速に動作させる仕組み
    * [RubyのJITコンパイラを理解したい！rubykaigiの香りを添えて](https://qiita.com/yu_ra/items/0bdef90999949c5d95b0)
* bundler が default gems として追加        <!-- .element: class="fragment" -->
    * これによりデフォルトで `bundle` コマンドが使えるようになった
* Ruby コードの抽象構文木を扱うライブラリが実験的に追加        <!-- .element: class="fragment" -->
* Kernel#yield_self の別名として #then が追加        <!-- .element: class="fragment" -->
* #select / #select! の別名として #filter / #filter! が追加        <!-- .element: class="fragment" -->
* Proc を関数合成する Proc#<< と Proc#>> が追加        <!-- .element: class="fragment" -->
* <p class="fragment">参照：[プロと読み解く Ruby 2.6 NEWS ファイル](https://techlife.cookpad.com/entry/2018/12/25/110240)</p>


---

#### Ruby 2.7
- - -

* [2019/12/25 にリリース](https://www.ruby-lang.org/ja/news/2019/12/25/ruby-2-7-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-2.7.0)

* パターンマッチ構文が実験的に導入        <!-- .element: class="fragment" -->
* irb のサポートが強化        <!-- .element: class="fragment" -->
* コンパクション GC を導入        <!-- .element: class="fragment" -->
    * 手動で `GC.compact` メソッドを呼ぶことでコンパクションを行う
* Ruby 3.0 で行われるキーワード引数の非互換対応の前準備        <!-- .element: class="fragment" -->
    * 非互換になる書き方をすると警告が出るように対応
* (..10) のように先端なし Range リテラルを追加        <!-- .element: class="fragment" -->

    ```ruby
    # 5 以下 を Range で表現して探索するようなことができる
    p (1..10).grep(..5)
    # => [1, 2, 3, 4, 5]
    ```
    <!-- .element: class="fragment" -->

>>>

#### Ruby 2.7 続き
- - -

* 改行を含むメソッドチェインをコメントアウト可能に対応        <!-- .element: class="fragment" -->
    ```ruby
    hoge
      # ここでコメントアウトできるようになった
      # .foo
      .bar
    ```
    <!-- .element: class="fragment" -->

* デフォルトのブロックの仮引数として Numbered Parameters が導入（通称ナンパラ）        <!-- .element: class="fragment" -->
    ```ruby
    # _1 が第一引数、_2 が第二引数を参照する
    plus = proc { _1 + _2 }
    plus.call 1, 2
    # => 3

    p (20..30).map { _1.to_s(16) }
    # => ["14", "15", "16", "17", "18", "19", "1a", "1b", "1c", "1d", "1e"]
    ```
    <!-- .element: class="fragment" -->

* 引数をフォワードする (...) 記法を追加        <!-- .element: class="fragment" -->

    ```ruby
    def foo(...)
      # foo の引数をそのまま bar にフォワードする
      bar(...)
    end
    ```
    <!-- .element: class="fragment" -->

>>>

#### Ruby 2.7 続き
- - -

* Enumerable#tally が追加    <!-- .element: class="fragment" -->

    ```ruby
    # 配列の要素数とその要素を Hash として返す
    ["a", "b", "c", "b"].tally
    #=> {"a"=>1, "b"=>2, "c"=>1}
    ```
    <!-- .element: class="fragment" -->

* Enumerable#filter_map を追加    <!-- .element: class="fragment" -->

    ```ruby
    # ブロックの戻り値が偽なら結果から取り除く
    p (1..10).filter_map { _1 + _1 if _1.even? }
    # => [4, 8, 12, 16, 20]
    ```
    <!-- .element: class="fragment" -->

* <p class="fragment">参照：[プロと読み解くRuby 2.7 NEWS](https://techlife.cookpad.com/entry/2019/12/25/121834)</p>

---

#### Ruby 3.0
- - -

* [2020/12/25 にリリース](https://www.ruby-lang.org/ja/news/2020/12/25/ruby-3-0-0-released/) : [NEWS](https://github.com/ruby/ruby/blob/master/doc/NEWS-3.0.0.md)
* Ruby 3.0 は Ruby 2.0 と比較して3倍早くすることを目標にしてきた             <!-- .element: class="fragment" -->
    * 「Optcarrot ベンチマーク」では JIT コンパイル時に 3倍早くなっており目標を達成できた
* パターンマッチが正式に採用       <!-- .element: class="fragment" -->
* 並列処理をサポートする Ractor ライブラリが実験的に追加       <!-- .element: class="fragment" -->
* 型のサポートを行う RBS と TypeProf の 2つのライブラリが追加       <!-- .element: class="fragment" -->
* キーワード引数の非互換な変更       <!-- .element: class="fragment" -->
    * 詳しくは[こちら](https://www.ruby-lang.org/en/news/2019/12/12/separation-of-positional-and-keyword-arguments-in-ruby-3-0/)
* 右代入が追加       <!-- .element: class="fragment" -->
* エンドレスメソッド定義が追加       <!-- .element: class="fragment" -->
* 正規表現リテラルや Range リテラルがデフォルトで frozen 化    <!-- .element: class="fragment" -->
* 参照：       <!-- .element: class="fragment" -->
    * [プロと読み解く Ruby 3.0 NEWS - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/12/25/155741)
    * [Ruby 3.0 Advent Calendar 2020](https://qiita.com/advent-calendar/2020/ruby3)


>>>

#### Ruby 3.0 続き
- - -

* [Ruby 3.0 の Ractor を自慢したい - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/12/26/131858)

---

## 最近のモダンな機能紹介・デモ

---

#### パターンマッチ
- - -

* Ruby 2.7 で実験的に入って 3.0 で正式に導入された         <!-- .element: class="fragment" -->
* case expr; in pattern; end という書き方になる          <!-- .element: class="fragment" -->

```ruby
# 各要素ごとに in で条件（型）を指定できる
# その要素を => で変数に束縛できる
# * で複数の要素を受け取ることも可能
# マッチしなかったら else 節にくる
# マッチしなくて else 節がなければ例外
case [1,  "homu", 14]
in [Integer, String => name, Integer => age]
  { name: name, age: age }
in [Integer, Integer => age, String => name]
  { name: name, age: age }
in [first, *middle, last]
  middle
in []
  []
else
  {}
end
```
<!-- .element: class="fragment" -->

>>>

#### パターンマッチ 続き
- - -

* Hash 形式でも記述できる              <!-- .element: class="fragment" -->
    * キーの要素ごとに条件を指定できる

```ruby
def check(user)
  case user
  # age が 20未満
  in { name:, age: (..20) }
    "#{name}は魔法少女です"
  # age が 20以上
  in { name:, age: (20..) }
    "#{name}は魔法少女ではありません"
  # それ以外
  else
    "わからない"
  end
end

p check({ name: "ほむ", age: 14 })  # => "ほむは魔法少女です"
p check({ name: "マミ", age: 30 })  # => "マミは魔法少女ではありません"
p check(["まどか", 14])             # => "わからない"
```
<!-- .element: class="fragment" -->

---

#### 1行 in (実験的)
- - -

* パターンマッチを 1行でかける構文             <!-- .element: class="fragment" -->
* これは Ruby 3.0 では実験的な機能になる         <!-- .element: class="fragment" -->
    * 使用すると実験的な警告が出るので注意
* Ruby 2.7 でも使用できるが挙動がちょっと違うので注意         <!-- .element: class="fragment" -->

```ruby
# これは普通のパターンマッチ
case user
in { name: String, age: (..20) }
end

# 上のパターンマッチが 1行でかける
# マッチしてたら true を返し、そうでなければ false を返す
# warning: One-line pattern matching is experimental, and the behavior may change in future versions of Ruby!
user in { name: String, age: (..20) }
```
<!-- .element: class="fragment" -->

>>>

#### 1行 in (実験的) 続き
- - -

* 1行 in は真理値を返すので if 文などの条件式として利用できる     <!-- .element: class="fragment" -->

```ruby
user = { name: "mami", age: 30 }

# 条件分岐をより細かく記述できる
if user in { name: String, age: (..20) }
  puts "OK"
else
  puts "NG"
end
```
<!-- .element: class="fragment" -->

```ruby
users = [
  { name: "homu", age: 14 },
  { name: "mami", age: 15 },
  { name: "mado", age: 14 }
]

# こんな感じで _1 と併用するとより簡潔に要素の絞り込みができる
pp users.select { _1 in { name: /^m/, age: (..15) } }
# => [{:name=>"mado", :age=>14}]
```
<!-- .element: class="fragment" -->

---

#### 右代入 (一部実験的)
- - -

* 左辺の値を右辺の変数に代入する構文   <!-- .element: class="fragment" -->

  ```ruby
  # 左辺の値を右辺の変数に代入する
  42 => value
  ```
  <!-- .element: class="fragment" -->

* コードは通常左から右に向かって記述する、その流れのまま代入式を書くことができるので気持ちよくコードがかける   <!-- .element: class="fragment" -->

```ruby
# 左からコードを書いてそのまま変数に代入できる
(1..10).select { _1.even? }.map { _1 + _1 } => result
pp result
# => [4, 8, 12, 16, 20]
```
<!-- .element: class="fragment" -->

```ruby
# ちなみにインスタンス変数やグローバル変数には代入できないので注意
# error: syntax error, unexpected instance variable
1 => @value
2 => $value
```
<!-- .element: class="fragment" -->

>>>

#### 右代入 (一部実験的) 続き
- - -

* この右代入はパターンマッチを利用している               <!-- .element: class="fragment" -->
    * なので Hash の要素をの中身を直接受け取ることができる

```ruby
user = { name: "mami", age: 15 }

# パターンマッチのように特定のキーの要素を束縛できる
user => { name:, age: }
pp name  # => "mami"
pp age   # => 15
```
<!-- .element: class="fragment" -->

```ruby
# もっと厳密にパターンを書くこともできる
user => { name: String => name, age: (..20) => age }
pp name
pp age
```
<!-- .element: class="fragment" -->

```ruby
# in とは違いパターンにマッチしなかったら例外が発生する
user => { name: Integer }
# => raise NoMatchingPatternError
```
<!-- .element: class="fragment" -->

* この書き方は Ruby 3.0 では実験的な警告が出るので注意         <!-- .element: class="fragment" -->

---

#### エンドレスメソッド定義
- - -

* 1行でメソッドが定義できるようになった        <!-- .element: class="fragment" -->
    * end を書かなくてメソッドが定義できるのでエンドレスメソッド
    * 元々は[エイプリルフールネタ](https://bugs.ruby-lang.org/issues/16746) だったのが matz の意向ではいっちゃった

```ruby
# end を書かずにメソッドが定義できる
# 引数がある場合は () は省略できないので注意
def twice(a) = a + a

p twice 42   # => 84

# 引数がない場合は () は省略できる
def value = 42
```
<!-- .element: class="fragment" -->


```ruby
# また = 付きメソッドは定義できないので注意
# error: setter method cannot be defined in an endless method definition
def value=(value) = @value = value
```
<!-- .element: class="fragment" -->

---

#### Ractor (実験的)
- - -

* Ractor は Ruby で並列処理を行うためのライブラリ    <!-- .element: class="fragment" -->
    * Ruby + Actor の略
* Ruby 3.0 では実験的な機能でまだちょっと不安定    <!-- .element: class="fragment" -->
* CPU のコアごとに独立した処理を実行できる       <!-- .element: class="fragment" -->
* 基本的に処理ごとにメモリ領域は共有せず、よりスレッドセーフな実装になっている    <!-- .element: class="fragment" -->
* 参照：       <!-- .element: class="fragment" -->
    * [Ruby 3.0 の Ractor を自慢したい - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/12/26/131858)
    * [Ruby の Ractor で ActiveObject を作る](https://zenn.dev/ko1/articles/46be20c67b57e057ef2a)
    * [Ruby に Software Transactional Memory (STM) を入れようと思った話 - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/11/20/110047)

>>>

#### Ractor (実験的) 続き
- - -

* [Ractor デモ](https://wandbox.org/permlink/2ngrcocPPT3hUMTB)

```ruby
# Ractor.new のブロックが並列処理として実行される
# .new の引数をブロックの引数として受け取る事ができる
ractor = Ractor.new(10) do |loop_count|
  loop_count.times do
    puts :hello
    sleep 0.3
  end
end

# 並列処理が終了するまでブロッキングする
# p ractor.take

10.times do
  puts :world
  sleep 0.3
end
```

---

#### 型周りのサポート
- - -

* Ruby 3.0 では Ruby の型情報を記述するために RBS を利用する      <!-- .element: class="fragment" -->
    * .rbs ファイルに Ruby のような構文で型情報を記述する
* Ruby 3.0 ではこの RBS をサポートするライブラリが追加された      <!-- .element: class="fragment" -->
    * RBS: .rbs ファイルや RBS 自体を扱うライブラリ
    * TypeProf: Ruby コードを解析して .rbs を自動生成するライブラリ
* また Ruby 3.0 時点では標準では型チェックを行う機能は入らない      <!-- .element: class="fragment" -->
    * steep という外部ライブラリで .rbs を使った型チェックを行うことができる
* <p class="fragment">[TypePorf デモ](https://mame.github.io/typeprof-playground/#rb=%23+test.rb%0Aclass+User%0A++def+initialize%28name%3A%2C+age%3A%29%0A++++%40name%2C+%40age+%3D+name%2C+age%0A++end%0A++%0A++attr_reader+%3Aname%2C+%3Aage%0Aend%0A%0Auser+%3D+User.new%28name%3A+%22John%22%2C+age%3A+20%29&rbs=)</p>
* 参照：                <!-- .element: class="fragment" -->
    * [Ruby 3 の静的解析ツール TypeProf の使い方 - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/12/09/120314)
    * [Ruby 3の静的解析機能のRBS、TypeProf、Steep、Sorbetの関係についてのノート - クックパッド開発者ブログ](https://techlife.cookpad.com/entry/2020/12/09/120454)

---

#### 最近の irb 事情
- - -

* Ruby 2.7 以前では GNU Readline で対話環境を実装していた      <!-- .element: class="fragment" -->
    * Ruby の標準ライブラリにも readline がある
* Ruby 2.7 では GNU Readline をピュア Ruby で実装した reline というライブラリが開発され irb はそれを利用するように改良された      <!-- .element: class="fragment" -->
* これにより Ruby 2.7 以降では以下のような機能が irb で利用できるようになった        <!-- .element: class="fragment" -->
    * 複数行編集機能
    * シンタックスハイライト
    * 簡単なコード補完
    * リファレンスの参照機能
* Ruby 3.0 では measure 機能が追加された        <!-- .element: class="fragment" -->
    * 実行時間が簡単に計測できるようになる
    * gem install stackprof すると measure :stackprof でメソッドのプロファイリングも行われる
    * 参照：[IRB’s Built-in Measure | Jemma Issroff](https://jemma.dev/blog/irb-measure)

---

## まとめ

---

#### まとめ
- - -

* Ruby が誕生してから今年で28年になる      <!-- .element: class="fragment" -->
* Ruby が死んだと毎年言われているががんばって開発されている      <!-- .element: class="fragment" -->
    * ちゃんと生きてるんじゃあ
    * 特に近年では新しい構文などが取り込まれる傾向にある
* わたしはまだ Ruby を使い始めて浅いのでスライドを書いてて昔の Ruby について知ることができてよかった      <!-- .element: class="fragment" -->
* 自分が使っている言語がどのように開発されているのか調べてみると色々と学びがある      <!-- .element: class="fragment" -->
    * そのが機能が追加された背景とか調べてみたりすると楽しい
* Ruby は書いてて気持ちがよいのでぜひぜひ触ってみましょう！      <!-- .element: class="fragment" -->


---

#### 参照
- - -

* [Rubyとは](https://www.ruby-lang.org/ja/about/#fn2)
* [Rubyist Hotlinks 【第 1 回】 まつもとゆきひろさん](https://magazine.rubyist.net/articles/0001/0001-Hotlinks.html)
* [まつもとゆきひろの履歴書｜仕事中にこっそり作ったRubyが世界を驚かせるまで - ぼくらの履歴書｜トップランナーの履歴書から「仕事人生」を深掘り！](https://employment.en-japan.com/myresume/entry/2019/09/26/103000)
* [まつもと×笹田、Ruby 1.9を語る − ＠IT](https://www.atmarkit.co.jp/news/200712/25/ruby.html)
* [これからの Ruby と今の Ruby について - Speaker Deck](https://speakerdeck.com/osyo/korekarafalse-ruby-tojin-false-ruby-nituite)
* [12月25日にリリースされる Ruby 3.0 に備えよう！ - Speaker Deck](https://speakerdeck.com/osyo/12yue-25ri-niririsusareru-ruby-3-dot-0-nibei-eyou)

---


### ご清聴
### ありがとうございました

