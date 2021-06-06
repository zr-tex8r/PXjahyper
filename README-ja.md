PXjahyper パッケージバンドル
============================

LaTeX： pLaTeX 上での hyperref のサポート

(u)pLaTeX 上で hyperref を用いて日本語の文書情報を含む PDF 文書を作成する
場合に必要となる以下の機能を提供する。

  * PDF 文字列内の和文文字のサポート
  * mag 指定に対するサポート

### 前提環境

  * フォーマット： LaTeX
  * エンジン： pTeX、upTeX、pTeX-ng  
    ※一部の機能では e-TeX 拡張が必要。
  * DVIウェア： dvipdfmx
  * 依存パッケージ：
      - atbegshi
      - hyperref
  * 一部の機能で必要なパッケージ：
      - japanese-otf
      - etoolbox
      - bxjatoucs

### インストール

  - `*.sty`, `*.def` → $TEXMF/tex/platex/PXjahyper

### ライセンス

本パッケージは MIT ライセンスの下で配布される。


pxjahyper パッケージ ー 本体
----------------------------

詳細についてはマニュアル `pxjahyper.pdf` を参照されたい。


pxjahyper-enc パッケージ ー 文字コード設定
------------------------------------------

他のパッケージの内部で読み込むために pxjahyper から機能を抜粋して作った
パッケージであり、DVI ファイル中の PDF 文字列の漢字コードを指定するため
の「tounicode special」を出力する機能のみをもつ。

※文書作成者は pxjahyper を読み込むことが推奨される。

### パッケージオプション

※オプション無しでの読込が望ましいが、一応グローバルのドライバオプション
に反応するようにしている。

  * ドライバオプション：`dvipdfmx`/`dvips`/`nodvidriver` があり、
    `dvipdfmx` 以外を指定した場合はパッケージの機能を無効化する。

### 機能

パッケージを読み込むと、既定動作として、エンジンの内部漢字コードに基づき
適切な「tounicode special」を出力する。

  * `\suppressbigcode`：内部漢字コードが Unicode のときに、`UTF8-UTF16`
    ではなく `UTF8-UCS2` の CMap を指定する。
  * `\suppressdefaulttounicode`：既定動作を無効にする。
  * `\pxjahyperToUnicodeSpecial{<名前>}`：引数の CMap 名を指定して
    「tounicode special」を出力する。


更新履歴
--------

  * Version 0.9c 〈2021/06/06〉
      - pxjahyper-uni モジュールを実際に使用する。

  * Version 0.9b 〈2021/05/29〉
      - PDF 文字列中で pxbabel の `\UTFJ` をサポート。
      - モジュール pxjahyper-uni.def を追加。

  * Version 0.9a 〈2021/05/11〉
      - バグ修正。

  * Version 0.9  〈2021/05/10〉
      - パッケージオプションの整理：`(no)papersize`、`convbkmk`、
        `(no)otfutf` を追加。
      - out2uni のエスケープ出力で UTF-16 を正しく扱う。
      - pLaTeX で tounicode 前提の動作をするときに、`\Ux` 等の Unicode
        符号入力についてフォールバック（ゲタ文字出力）を行う。

  * Version 0.8  〈2021/05/05〉
      - japanese-otf パッケージに対する実行のタイミングをパッケージ読込
        の直後に変更した。
      - (試験的) `(no)papersize` オプション。

  * Version 0.7b 〈2021/02/26〉
      - バグ修正。

  * Version 0.7a 〈2021/02/23〉
      - バグ修正。

  * Version 0.7  〈2021/02/13〉
      - 「upLaTeX での hyperref の `unicode` 指定への対応」を正式サポート
        の扱いとする。一部の正常動作しなかった機能についても対応させる。

  * Version 0.6a 〈2020/10/10〉
      - pxjahyper-enc：`dvips` 指定時はエラーでなく警告を出す。

  * Version 0.6  〈2020/10/05〉
      - pxjahyper-enc パッケージを追加した。
      - `otfmacros` オプションを既定で有効にする。

  * Version 0.5b 〈2020/10/04〉
      - バグ修正。

  * Version 0.5a 〈2020/09/27〉
      - LaTeX カーネル 2020/10/01 版への対応。

  * Version 0.5  〈2020/06/13〉
      - `otfmacros` オプションを正式にサポート。
      - `disablecmds` オプションを追加。
      - `none`（`nodvidriver` の別名）を非推奨とする。

  * Version 0.4b 〈2020/04/24〉
      - `\copyright` の再定義をやめる。

  * Version 0.4a 〈2019/11/23〉
      - (試験的) PDF 文字列中で japanese-otf の文字入力マクロをサポート
        （`otfmacros` オプション）

  * Version 0.4  〈2019/10/25〉
      - PDF 文字列中で `\CID` をサポート（`otfcid` オプション）

  * Version 0.3e 〈2019/06/20〉
      - hyperref の `unicode` 指定が後から変更された場合はエラーを出す。

  * Version 0.3d 〈2018/07/15〉
      - バグ修正。

  * Version 0.3c 〈2018/01/25〉
      - バグ修正。

  * Version 0.3b 〈2018/01/13〉
      - パッケージ定義の PDF 文字列の文字定義を拡充した。
      - (試験的) 自動判別の誤判定を防ぐため、アウトラインファイルに
        日本語文字のコメントを含ませておく。
      - (試験的) `(no)jacommentline` オプション。

  * Version 0.3a 〈2017/10/17〉
      - `bigcode` を既定に変更。
      - (試験的) upLaTeX で hyperref の `unicode` 指定を可能にする。

  * Version 0.3  〈2012/05/28〉
      - papersize special の調整機能を追加。
      - `\Ux` を追加。

  * Version 0.2  〈2012/05/27〉
      - 最初の公開版。

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
