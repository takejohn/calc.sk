# calc.sk

## Overview

チャット欄に計算式を入力すると計算してくれる Skript です。
アドオンを使わずに作られています。

## Usage

`=` で始まるチャットを打つか、コマンド `/=` または `/calc` を入力すると入力者に計算結果を送ります。

### Examples

```
=1+1
```

```
/= -3×4^2
```

```
/calc 1-2*sin(30)
```

## Specification

### Literals

以下のリテラルを記述できます。

* 実数: 負号演算子があるため、負数のリテラルはありません。
    * 整数: 半角数字のみからなる1文字以上の文字列 (例: `0`, `123`)
    * 小数: 先頭と末尾が半角数字で、
      小数点 `.` を1個だけ含む、半角数字および小数点 `.` のみからなる文字列
      (例: `3.14`, `2.0`, `0.01`)

### Operators

以下の演算子を使用できます。
| 優先順位 | 演算子               | 結合性  | 効果 |
|---------:|:--------------------|:--------:|:----------|
|        1 | `f(x_0,...,x_n)`    | なし     | 関数の適用 |
|        2 | `a^b`               | 右から左 | 累乗 |
|        3 | `a*b` `a×b`         | 左から右 | 乗算 |
|          | `a/b` `a÷b`         |         | 除算 |
|        4 | `+a`                | なし    | 正号 |
|          | `-a`                |         | 負号 |
|        5 | `a+b`               | 左から右 | 加算 |
|          | `a-b`               |         | 減算 |

### Functions

関数は以下のものを使用できます。

| 関数     | 効果 |
|:---------|:-----|
| `abs(x)` | 絶対値 |
| `acos(x)` | 逆余弦 |
| `asin(x)` | 逆正弦 |
| `atan(x)` | 逆正接 |
| `atan2(x,y)` | (0, 0) から (x, y) の方向へ伸ばした半直線とx軸が反時計回りになす角度 (-180°～180°の範囲で) |
| `ceil(x)` `ceiling(x)` | 天井関数 |
| `cos(x)` | 余弦 |
| `exp(x)` | ネイピア数を底とする指数関数 |
| `floor(x)` | 床関数 |
| `ln(x)` | 自然対数 |
| `log(x)` `log(x,y)` | yを底とする対数。yが書略された場合は底を10とする |
| `max(x_0,...,x_n)` | 最大値 |
| `min(x_0,...,x_n)` | 最小値 |
| `mod(x,y)` | xをyで割った余り |
| `product(x_0,...,x_n)` | 積 |
| `round(x)` | xに最も近い整数 |
| `sin(x)` | 正弦 |
| `sqrt(x)` | 正の平方根 |
| `sum(x_0,...,x_n)` | 和 |
| `tan(x)` | 正接 |

## License

この Skript ファイルは Apache-2.0 ライセンスの元で使用できます。
詳しくは [`LICENSE` ファイル](/LICENSE) を参照してください。
