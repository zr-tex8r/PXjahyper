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
  * DVIウェア： dvipdfmx
  * 依存パッケージ：
      - hyperref

### インストール

  - `*.sty` → $TEXMF/tex/platex/PXjahyper

### ライセンス

本パッケージは MIT ライセンスの下で配布される。


pxjahyper パッケージ ー 本体
----------------------------

詳細についてはマニュアル `pxjahyper.pdf` を参照されたい。


更新履歴
--------

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
