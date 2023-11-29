## 第一部：基本文法

### JSとは
  - 大文字と小文字を区別
    - :star2: 可変のものは大文字なイメージ（例: 付け外し用のクラス＝ const ACTIVE）

### コメント
  - JS Docコメントの復習する：https://ics.media/entry/6789/

### 変数と宣言
  - ```const```：再代入できない変数の宣言とその変数が参照する値（初期値）を定義
  - ```let```：値の再代入が可能な変数を宣言
  - ```var```：値の再代入が可能な変数を宣言　※同じ名前の変数を再定義できてしまう問題があるため注意(constやletでは構文エラー（SyntaxError）が発生)
  - 変数名に使える名前のルール
    ```
      let $; // OK: $が利用できる
      let _title; // OK: _が利用できる
      let jquery; // OK: 小文字のアルファベットが利用できる
      let TITLE; // OK: 大文字のアルファベットが利用できる
      let es2015; // OK: 数字は先頭以外なら利用できる
      let 日本語の変数名; // OK: 一部の漢字や日本語も利用できる
    ```

### 値の評価と表示
  - :star2: デバッグスキルの高め方(JSのおすすめ勉強資料などあれば..！)

### データ型とリテラル
  - プリミティブ型（基本型）
    - 真偽値（Boolean）: trueまたはfalseのデータ型
    - 数値（Number）: 数値のデータ型
    - 巨大な整数（BigInt）: ES2020から追加された9007199254740992nなどの任意精度の整数のデータ型
    - 文字列（String）: 文字列のデータ型
    - undefined: 値が未定義であることを意味するデータ型
    - null: 値が存在しないことを意味するデータ型
    - シンボル（Symbol）
  - typeof演算子を使うことでデータ型を調べることができる
    ```
      console.log(typeof true);// => "boolean"
      console.log(typeof 42); // => "number"
    ```
  - リテラル = プリミティブ型の値や一部のオブジェクトは、リテラルを使うことで簡単に定義できる

### 演算子
  - 二項演算子
    - プラス演算子（+）
      ```
        1 + 2;
        console.log(1 + 1); // => 2
      ```
    - 文字列結合演算子（+）
      ```
        const value = "文字列" + "結合";
        console.log(value); // => "文字列結合"
      ```
    - マイナス演算子（-）
      ```
        console.log(1 - 1); // => 0
      ```
    - 乗算演算子（*）
      ```
        console.log(2 * 8); // => 16
      ```
    - 除算演算子（/）
      ```
        console.log(8 / 2); // => 4
      ```
    - 剰余演算子（%）= 割り算した余り
      ```
        console.log(8 % 2); // => 0
        console.log(9 % 2); // => 1
      ```

  - 単項演算子
    - 単項プラス演算子（+）
      ```
        console.log(+1); // => 1
        console.log(+"1"); // => 1
      ```
    - 単項マイナス演算子（-）
      ```
        console.log(-1); // => -1
        console.log(-(-1)); // => 1
      ```

  - インクリメント演算子（++）
    ```
      let num = 1;
      num++;
      console.log(num); // => 2
    ```

  - デクリメント演算子（--）
    ```
      let num = 1;
      num--;
      console.log(num); // => 0
    ```

  - 比較演算子<br>
    **※（===）の利用を推奨**
    - 厳密等価演算子（===）
      ```
        console.log(1 === 1); // => true
        console.log(1 === "1"); // => false
      ```
    - 厳密不等価演算子（!==）<br>
      異なる値である場合に、trueを返す
      ```
        console.log(1 !== 1); // => false
        console.log(1 !== "1"); // => true
      ```
    - 等価演算子（==）
      ```
        console.log(1 == 1); // => true
        console.log("str" == "str"); // => true
        
        // 文字列を数値に変換してから比較
        console.log(1 == "1"); // => true
        // "01"を数値にすると`1`となる
        console.log(1 == "01"); // => true
        // 真偽値を数値に変換してから比較
        console.log(0 == false); // => true
        // nullの比較はfalseを返す
        console.log(0 == null); // => false
        // nullとundefinedの比較は常にtrueを返す
        console.log(null == undefined); // => true
      ```
    - 不等価演算子（!=）
      ```
        console.log(1 != 1); // => false
        console.log("str" != "str"); // => false
        console.log("JavaScript" != "ECMAScript"); // => true
        console.log(true != true);// => false
      ```

  - 論理演算子<br>
    AND（かつ）、OR（または）、NOT（否定）を表現

    - AND演算子（&&）<br>
      左辺の値の評価結果がtrueならば、右辺の評価結果を返す<br>
      左辺の値の評価結果がfalseならば、そのまま左辺の値を返す
      ```
        // 左辺はtrueであるため、右辺の評価結果を返す
        console.log(true && "右辺の値"); // => "右辺の値"
        // 左辺がfalseであるなら、その時点でfalseを返す
        // 右辺は評価されない
        console.log(false && "右辺の値"); // => false
      ```
    - OR演算子（||）<br>
      左辺の値の評価結果がtrueならば、そのまま左辺の値を返す<br>
      左辺の値の評価結果がfalseであるならば、右辺の評価結果を返す
      ```
        // 左辺がtrueなので、左辺の値が返される
        console.log(true || "右辺の値"); // => true
        // 左辺がfalseなので、右辺の値が返される
        console.log(false || "右辺の値"); // => "右辺の値"
      ```
    - NOT演算子（!）<br>
      評価結果がtrueならば、falseを返す<br>
      評価結果がfalseならば、trueを返す
      ```
        console.log(!false); // => true
        console.log(!true);  // => false
      ```

### 暗黙的な型変換
  - 処理の過程でオペランドの型によって、 自動的に変換されること
  - NaNはNot a Number

### 明示的な型変換
  - プリミティブ型へ明示的な型変換をする
  - 数値 → 文字列
    ```
      String(1); // => "1"
    ```
  - 文字列 → 数値 = Numberコンストラクタ関数
    ```
      // ユーザー入力を文字列として受け取る
      const input = window.prompt("数字を入力してください", "42");
      // 文字列を数値に変換する
      const num = Number(input);
      console.log(typeof num); // => "number"
      console.log(num); // 入力された文字列を数値に変換したもの
    ```
    - 文字列から数字を取り出して変換する関数
      -  ```Number.parseInt```
      - ```Number.parseFloat```


### 関数と宣言
  - 関数宣言: 関数を定義するためにfunctionキーワードを使った文
  - 関数の引数
    - 後で読む　https://wp-p.info/tpl_rep.php?cat=js-application&fl=r12
    - 余った仮引数にはundefinedという値が代入
    - 仮引数=デフォルト値という構文で、仮引数ごとにデフォルト値を指定できる
    - 可変長引数=固定した数ではなく任意の個数の引数を受け取れること
    - Rest parameters=残余引数=関数に渡された値が配列として代入される
    - arguments: argumentsという関数の中でのみ参照できる特殊な変数<br>
      Rest parametersが利用できる環境では、arguments変数をあまり使わない
    - 分割代入: オブジェクトや配列からプロパティを取り出し、変数として定義し直す構文
      ```
        function printUserId(user) {
          console.log(user.id); // => 42
        }
        const user = {
            id: 42
        };
        printUserId(user);
      ```
    - 関数はオブジェクト
      - 関数名に()をつけることで、関数としてまとめた処理を呼び出すことができる
        ```
        function fn() {
          console.log("fnが呼び出されました");
        }
        // 関数`fn`を`myFunc`変数に代入している
        const myFunc = fn;
        myFunc();
      ```
    - 関数式=関数を値として変数へ代入している式
      ```
        // 関数式
        const 変数名 = function() {
            // 関数を呼び出したときの処理
            // ...
            return 関数の返り値;
        };
      ```
    - Arrow Function = => を使い、無名関数を定義する構文
      ```
        // Arrow Functionを使った関数定義
        const 変数名 = () => {
            // 関数を呼び出したときの処理
            // ...
            return 関数の返す値;
        };
      ```
        - 名前をつけることができない（常に無名関数）
        - thisが静的に決定できる
        - functionキーワードに比べて短く書くことができる
        - newできない（コンストラクタ関数ではない）
        - arguments変数を参照できない

    - [注意]同じ名前の関数宣言は上書きされる


### 文と式
  - JavaScriptは、文（Statement）と式（Expression）から構成される
  - 文は式になれない
  - 式は文になれる（式文）
  - 文の末尾にはセミコロンをつける
  - ブロックで終わる文は例外的にセミコロンをつけなくてよい

### 条件分岐
  - if文、else if文、else文で条件分岐した処理を扱える
  - 条件式に指定した値は真偽値へと変換してから判定される
  - 真偽値に変換するとfalseとなる値をfalsyと呼ぶ
  - switch文とcase節、default節を組み合わせて条件分岐した処理を扱える
  - case節でbreak文を省略した場合は、後ろに続くcase節が実行される

### ループと反復処理
  - while文/do-while文は安易に使用せず、他を模索するのがよさそう
  - for文 : 繰り返す範囲を指定した反復処理
    ```
      for (初期化式; 条件式; 増分式) {
      実行する文;
    ```
    1.初期化式 で変数の宣言<br>
    2.条件式 の評価結果がtrueなら次のステップへ、falseなら終了<br>
    3.実行する文 を実行<br>
    4.増分式 で変数を更新<br>
    5.ステップ2へ戻る<br>
}
  - forEachメソッド : for文と同じように反復処理を行うメソッド
    ```
      const array = [1, 2, 3];
      array.forEach(currentValue => {
          // 配列の要素ごとに呼び出される処理
      });
    ```
  - コールバック関数 : 引数として渡される関数のこと
    ```
      const array = [1, 2, 3];
      // forEachは"コールバック関数"を受け取る高階関数
      array.forEach(コールバック関数);
    ```
  - Array オブジェクト : 複数の項目の集合を単一の変数名の下に格納することができ、共通の配列操作を行うためのメンバーを持つ
  - :star2: for...in文がしっくり来ず...(書いてあることはなんとなく理解)基本的にforEachを使用する温度感でよいか？

### オブジェクト
  - :star2: プロパティへのアクセス：どちらかというとドット記法がなじみがあるのですが、住まいルール的に何かあるか