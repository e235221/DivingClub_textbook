## 概要
U.R.D.C.ダイビング部の赤冊子の内容をjupyter notebookに変換したものです。 過去10年間の赤冊子の内容と部室内にある書籍類を参考にして作成しています。 まだ未完成なので，誤植は多いと思いますが気長にみてください。

## webpage
github pageを使って公開しています。
https://e235221.github.io/DivingClub_textbook/0intro.html


## ディレクトリ構造
- `root/docs`
	- GitHubPageで公開するために，docsファイルに公開したい HTML を置いています。
	- docs直下に空ファイル`.nojekyll` を置いています。これは Jekyll 処理を無効化にし，`juputer-book build`で生成されるアンダースコア付きフォルダも含め“そのまま”公開するために作成しています。

- `root/jupyterbook`
	- `_build/`：ビルド成果物を格納するディレクトリです，jupyter-book build 実行時に HTML や関連ファイルがここに出力されます．
	- `_config.yml`：Jupyter Book（Sphinx）の全体設定ファイルです，サイトのタイトルやテーマ設定，拡張機能の有効化など各種オプションを指定します．
	- `_toc.yml`：目次（Table of Contents）を定義するファイルです，章・節の並び順やネスト構造を YAML 形式で記述します．
	- `figs/`：書籍内で参照する画像ファイルを格納するディレクトリです．Markdown から相対パスで参照しています.
	- `references.bib`：参考文献リスト（BibTeX形式）です.
		

### 注釈
- docsは2025/05/05/07時点でjb buildしたhtml filesをcopyしたものである。
  - （理由（なぜそんなめんどくさいことをしているのか））：rootディレクトリで，`jb build jupyterbook/ --path-output docs`をすることで，jupyterbookのbuild出力先を`docs/`に変更できるが， `docs/` にフラットに吐き出す機能がないため，どうしても `_build/html` 配下に出力される仕組みになってしまい，`/jupyterbook`で`jb build`コマンドを実行 => `_build/html`をdocs/にコピーしなければならない。
  - Shell Scriptを作れば解決するが，最小の環境依存にするため排除した。

