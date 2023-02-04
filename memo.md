# RMarkdownに関するメモ

## 基本情報

- 各Rmdファイルは`#`で始める
  - 一つの章に一つのRmdファイル
  - セクションに番号を振りたいくない場合は`##`の後に`{-}`を追加する
- ファイル名は`01-xxx.Rmd`の形式
 - アンダースコアで始まるファイルはスキップ(`_skip.Rmd`)される 
- `index.Rmd`は最初に配置される
  - メタデータは`index.Rmd`のみに記載する
- フットノートは`^[]`を挿入する箇所に記述、中身を[]内に記述 

## 参照
図とテーブルを参照するには文中で`\@ref(fig:chunk-label)` and `\@ref(tab:chunk-label)`とし、`chunk-label`の部分は参照先のチャンクの名前を指定する。

## 引用(マニュアル)

`book.bib`ファイルに書籍情報を次のように記述し、本文では`[@xie2015]`で引用できる。

```r
@Book{xie2015,
  title = {Dynamic Documents with {R} and knitr},
  author = {Yihui Xie},
  publisher = {Chapman and Hall/CRC},
  address = {Boca Raton, Florida},
  year = {2015},
  edition = {2nd},
  note = {ISBN 978-1498716963},
  url = {http://yihui.org/knitr/},
}
```

## 開発環境

previewでローカルサーバーを利用しbuildでdocsフォルダにhtmlファイルを生成する。

- previewするコマンド`bookdown::serve_book()`
- buildするコマンド`bookdown::render_book()`
  
- `_bookdown.yml`は設定ファイル
  - docsフォルダにhtmlファイルを出力するために、`output_dir: "docs"`を追記する
- `_output.yml`は出力のオプションを設定
- Markdownファイルの特定チャンクが重いならばキャッシュを利用する` {r chache=TRUE}`



## 参考文献
- [bookdown: Authoring Books and Technical Documents with R Markdown](https://bookdown.org/yihui/bookdown/)

- [逆関数法](https://ja.wikipedia.org/wiki/%E9%80%86%E9%96%A2%E6%95%B0%E6%B3%95)