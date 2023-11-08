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

  - 比較演算子
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