# 標準仕様

## 概要
IML(IMAI-LABEL)の仕様です。  
IMAI-SystemではIMLによって全てのオブジェクトが一意に表現されます。


## データ構造
|  |  GroupingNumber | SerialNumber | CheckDigit
| --- | --- | --- | --- |
| 最小値 | 0000 | 000 | 0 |
| 最大値 | FFFF | FFF | 9 |

### GroupingNumber
    管理するアイテムの分類を表す番号です.

#### プロ研で扱う場合
    - 上 1 ビット目  大分類 (書籍, 機材 ...)
    - 上 2 ビット目  中分類 (本, 同人誌, 雑誌 ...)
    - 上 3,4 ビット目  小分類 (Python 専門書, Docker 専門書 ...)

### SerialNumber
    `GroupingNumber` 配下に所属するオブジェクトの通し番号です。

### CheckDigit
    1桁ごとに10進数した値をLuhnアルゴリズムで計算します.
