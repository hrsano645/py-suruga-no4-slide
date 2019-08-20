#### Python駿河 勉強会 #4 

##### 〜Python初心者に寄ってたかって教えよう！〜

###### 2019/08/24 @Bivi藤枝

---

---

#### お前誰よ

- Twitter:＠hrs_sano645
- 普段は家業の自動車金型機械設計の設計以外の何でも屋
- ~~最近家電が壊れまくってお財布も壊れた~~
- 8月の #pyhack 行ってきました。めちゃくちゃ楽しかった！

---

#### アンケート

1. Python初めて~触って数ヶ月
2. 入門的書籍を通して終えれてる
3. 実際に趣味/業務でスクリプトとして利用してる
4. パッケージや業務のサービスとして稼働してる
5. サービスをリリースして運用している

---

#### この中で下3つの方は正直みる必要ないですw

---

#### 本日の内容

- Pythonの開発環境を作ろう
  - Pythonをいい感じで始める為の準備
- 寄ってたかって教える会
- LTがあればLT大会しましょう

---

#### Pythonの開発環境を作ろう

---

#### 目次

- Pythonをどう入れるか
- Pythonを書く環境は？
- Pythonの実行環境を用意(仮想環境

---

#### Pythonをどう入れるか

#### 各種OS向け

- win:公式パッケージ一択
- Mac: 標準だとpython2系なので、公式パッケージ, Homebrew, MacPortなどのパッケージマネージャー経由
- linux: デフォで入ってるし、いくつかのバージョンはLinuxのパッケージマネージャー(apt/yum などなど)経由でインストール可能


---

#### 他の手段
- ソースコードからビルド
  - 公式パッケージは基本的に最新版のみがバイナリしかないので必要なら
  - Python2系は2019/01/01にEOLです
- docker: [python - Docker Hub](https://hub.docker.com/_/python)
- anaconda
  - pythonというか科学分野向けの統合ディストリビューションaf

---

#### pythonを動かす、書く環境

---

#### Pythonを動かす環境

- CUI(command user interface:コマンドを1回ずつ実行して結果を見る環境）
  - - Pythonの1行ごと実行できる対話インターフェイスをつかう（REPL）
- スクリプトファイル(.py ファイル)
  - テキスト形式でコードを書いて実行
  - `python zikkou-sitai-file.py`

---

#### CUIで動かす:Win

- コマンドプロンプト（cmd）が基本
- powershell（ps）は使えるらしいけど、自分は使ったことない
- WSL(Windows Subsystem for Linux) はWinの公式のインストーラーのものではなくLinux側の扱いになるので注意
- ターミナルアプリケーションの存在
	- hyper
	- windows terminal:MS公式のターミナルアプリ cmd, psやwslを一つの画面上で同時に利用できる
- そのほか cygwinとかmsys2とか色々ありますが割愛！

---

#### CUIで動かす:macOS, Linux

- macOS
	- 標準のターミナルが一番やりやすい
	- iterm2という高機能なターミナルもおすすめ
- LInux
	- デスクトップ環境がある場合はその環境のターミナル(gnome terminal, lxterminal, などなど）
	- cuiならそもそもコマンドを叩けます。
---

#### スクリプトファイルを書くエディタを用意する
---

#### クロスプラットフォーム

- VSCode, Atom: WEB系の技術で作られたエディタ(nodejs,electron)  
利用者多いのとPython開発のサポートや拡張機能があります
  - ほかにもadobe系のBracketsとか
- Sublime Text3 （有償）
- PyCharm(intellij系): jetbreain社の統合開発環境（IDE） 
- vim/emacs: わかる人に聞いてください（サーバー上ならこちらの方が良い場合）
- Eclipse + pydev

---

#### そのほか

- Win
	- [Notepad++](https://notepad-plus-plus.org/)
	- [サクラエディタ](https://sakura-editor.github.io/)
- Mac
	- 基本クロスプラットフォームのものが良さげ
	- [Coda](https://panic.com/jp/coda/)
		- [Panic - Nova](https://panic.com/jp/nova/)
	- [TextMate: Text editor for macOS](https://macromates.com/)
	- Xcodeもできるけどあまり聞かない

---

#### そのほか

- Linux:割愛（すみません。。クロスプラットフォーム向けは良い選択肢）
- Python向けのエディタも沢山あります
  - [PythonEditors - Python Wiki](https://wiki.python.org/moin/PythonEditors)
  - [Collection: Text editors · GitHub](https://github.com/collections/text-editors)

---

#### おまけ:VSCodeでおすすめの拡張機能


- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python): **必ず入れるべき** 
  - MS公式提供の拡張機能。コード補完やデバッグ, 開発で利用するパッケージを統合サポートしてくれる（テスト, 静的解析, 自動フォーマットのライブラリもサポート）

---

#### おまけ:VSCodeでおすすめの拡張機能

- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync): 設定を別のマシンと同期できる
- [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight):TODOコメントをハイライトしてくれる
- markdownのプレビュー系
  - [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
- [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack): ペアプロするのにオススメ

---

#### Python拡張で使うとオススメなライブラリ

Pythonのコードを扱う時間が増えてきたらオススメ。VSCodeでサポートされてます。

- [リンター](https://code.visualstudio.com/docs/python/linting#_general-linting-settings): flake8, pylint
- [自動フォーマット](hhttps://code.visualstudio.com/docs/python/editing#_formatting): black, yapf, autopep8
- 型チェック: mypy -> [vscodeでの解説](https://code.visualstudio.com/docs/python/linting#_mypy)
- そのほか
  - isort: importの並びを綺麗にする -> [vscodeでの解説](https://code.visualstudio.com/docs/python/editing#_sort-imports)

参考:[Python 3.7とVisual Studio Codeで型チェックが捗る内作Pythonアプリケーション開発環境の構築 - Qiita](https://qiita.com/shibukawa/items/1650724daf117fad6ccd#%E3%82%BF%E3%82%A4%E3%83%88%E3%83%AB%E3%81%AE%E6%84%8F%E5%91%B3)

---

#### まとめ

- 試す環境:CUIで動かす
- 書く環境:エディタ IDEでスクリプトを書こう

---

---

#### Python環境を作る

---

#### 開発をするときは基本的に仮想環境がおすすめ

---

#### Why?

- システムの環境に様々なパッケージを入れることで綺麗でなくなる
- 開発中はなるべく利用するパッケージを固定にしたい

---

#### 仮想環境の種類

- ローカルの実行環境:ここを扱う => 仮想実行環境
- 仮想マシンでOSごと
  - コンテナも -> dockerとかも
- ユーザーアカウント
  - ユーザーディレクトリにPythonを入れる

---

#### Python仮想環境の選択肢

- Pythonの各バージョン依存
	- python3 venv + pipのrrequirements.txt
- 複数バージョン
	- pipenv:依存問題に対処しやすい
	- virtualeenv:pipenvでも使われてる
- その他
	- poetry, flit, pyenv

--- 

#### venv

Pythonの実行環境に入る標準の仮想実行環境作成ツール

- `python -m venv .venv` で実行時のディレクトリに仮想実行環境を作成
  - Win: `.venv¥Scripts¥activate.bat`
  - Mac/Linux: `source .venv/bin/activate`
- 仮想環境から抜けるとき: `deactivate`

---

#### ****

---

#### pipenv

Pypa公式になったpipの依存管理ツール

依存管理ツールとは？

開発中にバージョンを固定してやりたい。

バージョン固定 -> 同じ環境で開発し続けれる -> 計画的な依存ライブラリのバージョンアップができる

pipにも requirements.txtがある

ただ不便な面がある -> [Pipfile/Pipfile.lockの必要性 -requirements.txtを用いる手法と比較して- - Qiita](https://qiita.com/miyashiiii/items/92e6f745a940c4df2ddd)

別の環境（例えば本番環境と開発環境が分かれてるとき）でも同じ環境が作れる

ぶっちゃけこちらが素晴らしい解説だったので ~~丸投げ~~ 参照

[Pipenv のご紹介 - Google スライド](https://docs.google.com/presentation/d/1tmdB8TpJKcRGk95PoD0Q0jzeMCsBv1EddJ-LVYLj_mY/edit#slide=id.p)


---

#### poetry

Poetry: [sdispater/poetry](https://github.com/sdispater/poetry)

利用パッケージの依存関係の管理に加えて、パッケージ作成をするときのファイル(setup.pyなど)も生成してくれる。


パッケージ作成者ならこちらが使いやすいラシイ

----

#### flit

pyproject.tomlでパッケージ管理、ビルド可能。仮想環境は作る必要がある

[takluyver/flit: Simplified packaging of Python modules](https://github.com/takluyver/flit)

---

#### おまけ:pyenv

- pythonの複数バージョンをインストールしやすくする, 管理しやすくするものがコア
- わかっている人向けで、複数の実行環境が必要な人向け（特に2.7系, 3系の古いもの
- 今後必要になるかは不明（特に2.7系は来年1/1にEOLです, 3.5まではEOLです）

---

#### まとめ

- 基本: venv+pip/rrequirements.txt
- 最近の選択肢: Pipenv
- 第三の選択肢: poetry, flit
- 普通は使わなくても良い: pyenv

今はそれぞれ選択肢があるイメージ。一先ずvenvの使い方を覚えるのが良いです

