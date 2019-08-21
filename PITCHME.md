### Python駿河 勉強会 #4 

〜Python初心者に寄ってたかって教えよう！〜

2019/08/24 @Bivi藤枝

---

---

### お前誰よ

- Twitter:＠hrs_sano645
- 普段は家業の自動車金型機械設計の設計以外の何でも屋
- ~~最近家電が壊れまくってお財布も壊れた~~
- 8月の #pyhack 行ってきました。めちゃくちゃ楽しかった！

---

### アンケート

- Python初めて~触って数ヶ月
- 入門的書籍を通して終えれてる
- 実際に趣味/業務でスクリプトとして利用してる
- パッケージや業務のサービスとして稼働してる
- サービスをリリースして運用している

---

### アンケート

- Python初めて~触って数ヶ月
- 入門的書籍を通して終えれてる
- 実際に趣味/業務でスクリプトとして利用してる
----
- パッケージや業務のサービスとして稼働してる
- サービスをリリースして運用している

今回は上から3つの方向け対象です。

ノウハウの共有も大歓迎です🙆‍♂️
---

### 本日の内容

- Pythonの開発環境を作ろう
  - Pythonをいい感じで始める為の準備
- 寄ってたかって教える会
- LTがあればLT大会しましょう！

---

### Pythonの開発環境を作ろう

---

### 目次

- Pythonをどう入れるか
- Pythonを動かす/書く環境は？
- Pythonの実行環境を用意(仮想環境）

---

### Pythonをどう入れるか

---

### 各種OS向け

- win:公式パッケージ一択
- Mac: 標準だとpython2系なので、公式パッケージ
  - Homebrew, MacPortなどのパッケージマネージャー経由
- linux: 標準でインストール済み
  - 複数バージョンはLinuxのパッケージマネージャー(apt/yum/...)経由など

Win,Macは基本公式パッケージ

---

### 他の手段
- ソースコードからビルド
  - 公式パッケージは基本的に最新版のみがバイナリしかないので必要なら
  - Python2系は2020/01/01にEOLです😇
- docker: [python - Docker Hub](https://hub.docker.com/_/python)
- anaconda
  - pythonというか科学分野向けの統合ディストリビューション

---

### pythonを動かす、書く環境

---

### Pythonを動かす環境

- CUI(command user interface:コマンドを1回ずつ実行して結果を見る環境）
  - Pythonの1行ごと実行できる対話インターフェイスをつかう（REPL）

```sh
>>> print("hello Python Suruga")
```

- スクリプトファイル(.py ファイル)
  - テキスト形式でコードを書いて実行

```sh
python zikkou-sitai-file.py
```

---

### CUIで動かす:Win

- コマンドプロンプト（cmd）が基本
- powershell（ps）
- WSL(Windows Subsystem for Linux) : Winの公式インストーラーではなくLinux側の扱いになるので注意
- ターミナルアプリケーションの存在
  - Windows Terminal:MS公式のターミナルアプリ cmd, psやwslを一つの画面上で同時に利用できる
- そのほか cygwinとかmsys2とかは割愛！

---

### CUIで動かす:macOS, Linux

- macOS
  - 標準のターミナルが一番やりやすい
  - iterm2という高機能なターミナルもおススメ
- LInux
  - デスクトップ環境がある場合はその環境のターミナル(gnome terminal, lxterminal, などなど）
  - cuiならそもそもpythonコマンドを叩けます。
  
---

### スクリプトファイルを書くエディタを用意する

---

### クロスプラットフォーム

- nodejs,electron: WEB系の技術で作られたエディタ
  - VSCode, Atom
- Sublime Text3 （有償）
- PyCharm(intellij系): jetbrain社の統合開発環境（IDE） 
- vim/emacs: わかる人に聞いてください
- Eclipse + pydev

---

### そのほかOSごと

- Win
  - [Notepad++](https://notepad-plus-plus.org/)
  - [サクラエディタ](https://sakura-editor.github.io/)
- Mac
  - 基本クロスプラットフォームのものが良さげ
  - [Panic - Coda](https://panic.com/jp/coda/)
  - [TextMate: Text editor for macOS](https://macromates.com/)
  - Xcodeもできるけどあまり聞かない

---

### そのほかOSごと

- Linux:割愛（すみません。。クロスプラットフォーム向けは良い選択肢）
- Python向けのエディタも沢山あります
  - [PythonEditors - Python Wiki](https://wiki.python.org/moin/PythonEditors)
  - [Collection: Text editors · GitHub](https://github.com/collections/text-editors)

---

### おまけ:VSCodeおすすめ拡張機能

- [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python): **必ず入れるべき** 
  - MS公式提供の拡張機能。コード補完やデバッグ, 開発で利用するパッケージを統合サポートしてくれる
  - （テスト, 静的解析, 自動フォーマットのライブラリもサポート）

---

### おまけ:VSCodeおすすめ拡張機能

- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync): 設定を別のマシンと同期できる
- [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight):TODOコメントをハイライトする
- markdownのプレビュー系
  - [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)
- [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack): ペアプロにオススメ

---

### VSCodeのPython拡張で使えるもの

Pythonを扱う時間が増えたらオススメ

VSCodeでサポートされてます

- [リンター](https://code.visualstudio.com/docs/python/linting#_general-linting-settings): flake8, pylint
- [自動フォーマット](hhttps://code.visualstudio.com/docs/python/editing#_formatting): black, yapf, autopep8
- 型チェック: [mypy](https://code.visualstudio.com/docs/python/linting#_mypy)
- そのほか
  - [isort](https://code.visualstudio.com/docs/python/editing#_sort-imports): importの並びを綺麗に

参考:[Python 3.7とVisual Studio Codeで型チェックが捗る内作Pythonアプリケーション開発環境の構築](https://qiita.com/shibukawa/items/1650724daf117fad6ccd#%E3%82%BF%E3%82%A4%E3%83%88%E3%83%AB%E3%81%AE%E6%84%8F%E5%91%B3)

---

### まとめ

- 試す環境:CUIで動かそう
- 書く環境:エディタやIDEでスクリプトを書こう

---

### 扱わなかったこと

- コードの履歴管理(gitなどのVCS)
- テスト環境(unittest, pytest)
- プロジェクト管理(githubなど）

---

### Python環境を作る

---

### 開発をするときは基本的に仮想環境がおすすめ

---

### Why?

- システムの環境に様々なパッケージを入れることで綺麗でなくなる
- 開発中はなるべく利用するパッケージを固定にしたい

---

### 依存管理ツールとは？

開発中にライブラリのバージョンを固定するメリット

- 同じ環境で開発し続けれる（別のPCで同じライブラリを入れやすい）
- 計画的な依存ライブラリのバージョンアップができる

---

### 仮想環境の種類

- ローカルの実行環境:ここを扱う => 仮想実行環境
- 仮想マシンでOSごと仮想化
  - コンテナ、dockerも
- ユーザーアカウント
  - ユーザーディレクトリにPythonを入れる

---

### Python仮想環境の選択肢

基本はvenv

開発が進む/チームで開発ならpipenv, poetry/flit など

- Pythonの各バージョン依存
  - python3 venv + pipのrrequirements.txt
- 複数バージョン
  - pipenv: 依存管理をしやすく
- その他
  - poetry, flit, pyenv

--- 

### venv

Pythonの実行環境に入る標準の仮想実行環境作成ツール

```sh
# プロジェクトフォルダを作って移動する
mkdir projname & cd projname

# 実行時のディレクトリに仮想実行環境を作成
python -m venv .venv

# activateコマンドで仮想環境へ切り替え
.venv¥Scripts¥activate.bat #Win
source .venv/bin/activate # Mac/Linux

# コマンドで仮想環境から抜ける
deactivate
```

---

### venv:pip+requirements.txt


```sh
# pipでインストールしたライブラリのバージョンを固定する
pip freeze > requirements.txt

# 別の開発環境で同じライブラリのバージョンをインストール
pip install -r requirements.txt
```
---

### pipenv

Pypa公式になったpipの依存管理ツール

[Pipfile/Pipfile.lockの必要性 -requirements.txtを用いる手法と比較して- - Qiita](https://qiita.com/miyashiiii/items/92e6f745a940c4df2ddd)

ぶっちゃけこちらが素晴らしい解説だったので ~~丸投げ~~ 参照

[Pipenv のご紹介 - Google スライド](https://docs.google.com/presentation/d/1tmdB8TpJKcRGk95PoD0Q0jzeMCsBv1EddJ-LVYLj_mY/edit#slide=id.p)

---

### pipenvの使い方例

```sh
pipenv --python 3.7 # Pipfileを作成、pythonのバージョン指定して仮想環境作成
pipenv install # ライブラリ管理に使う
pipenv shell # 仮想環境に移動
pipenv run python example.py # example.pyをpipenvの環境で実行する
```

---

### poetry

[sdispater/poetry](https://github.com/sdispater/poetry)

- venv, pipenvのように仮想環境作成
- 利用パッケージの依存関係の管理に加えて
- PyPI向けパッケージ作成をするときのファイル(setup.pyなど)も生成

パッケージ作成者ならこちらが使いやすいと思う（個人の感想です。）

---

### flit

[takluyver/flit](https://github.com/takluyver/flit)

- pyproject.tomlでパッケージ管理、pypi向けにビルド可能
- 仮想環境は作る必要がある

---

### おまけ:pyenv

pyenvは普段は使わない/ただ入れるのはオススメしないです

- pythonの複数バージョンをインストールしやすくする, 管理しやすくするものがコア
- 複数の実行環境が必要な人向け（特に2.7系, 3系の古いもの
- 今後必要になるかは不明
  - （特に2.7系は来年1/1にEOLです, 3.5まではEOLです）

---

### まとめ

- 基本: venv+pip/requirements.txt
- 最近の選択肢: Pipenv
- 第三の選択肢: poetry, flit
- 普通は使わなくても良い: pyenv

一先ずvenvの使い方を覚えるのが良いです
