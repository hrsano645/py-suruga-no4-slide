### Python駿河 4回目

#### 2019/08/24 @Bivi藤枝

---

---

### お前誰よ

- Twitter:＠hrs_sano645
- 普段は家業の自動車金型機械設計の設計以外の何でも屋
- ~~最近家電が壊れまくってお財布も壊れた~~
- 8月の #pyhack 行ってきました。めちゃくちゃ楽しかった！

---

### アンケート

1. Python初めて~触って数ヶ月
2. 入門的書籍を通して終えれてる
3. 実際に趣味/業務でスクリプトとして利用してる
4. パッケージや業務のサービスとして稼働してる
5. サービスをリリースして運用している

---

### この中で下3つの方は正直みる必要ないですw

---

### 本日の内容

- Pythonの開発環境を作ろう
    - Pythonをいい感じで始める為の準備
- 寄ってたかって教える会
- LTがあればLTします

---

### Pythonの開発環境を作ろう

---

### ぶっちゃけ誰かこういうまとめをブログかQiitaにあげてほしい

---

### 目次

- Pythonをどう入れるか
- Pythonを書く環境は？
- Pythonの実行環境を用意(仮想環境

---

### Pythonをどう入れるか

### 各種OS向け

- win:公式パッケージ一択
- Mac: 標準だとpython2系なので、公式パッケージ, Homebrew, MacPortなどのパッケージマネージャー経由
- linux: デフォで入ってるし、いくつかのバージョンはLinuxのパッケージマネージャー(apt/yum などなど)経由でインストール可能


---

### 他の手段
- ソースコードからビルド
    - 公式パッケージは基本的に最新版のみがバイナリしかないので必要なら
    - Python2系は2019/01/01にEOLです
- docker: [python - Docker Hub](https://hub.docker.com/_/python)
- anaconda
    - pythonというか科学分野向けの統合ディストリビューション
    - こちらを入れた場合は、後ほど出てくるpip->condaが基本です
    - 正直使ってないので使った方がいればフォローください

---

### pythonを動かす、書く環境

---

### Pythonを動かす環境

- CUI(command user interface:コマンドを1回ずつ実行して結果を見る環境）
    - - Pythonの1行ごと実行できる対話インターフェイスをつかう（REPL）
- スクリプトファイル(.py ファイル)
    - テキスト形式でコードを書いて実行
    - `python zikkou-sitai-file.py`

### CUIで動かす:Win

- コマンドプロンプト（cmd）が基本
- powershell（ps）は使えるらしいけど、自分は使ったことない
- WSL(Windows Subsystem for Linux) はWinの公式のインストーラーのものではなくLinux側の扱いになるので注意
- ターミナルアプリケーションの存在
	- hyper
	- windows terminal:MS公式のターミナルアプリ cmd, psやwslを一つの画面上で同時に利用できる
- そのほか cygwinとかmsys2とか色々ありますが割愛！

---

### CUIで動かす:macOS, Linux

- macOS
	- 標準のターミナルが一番やりやすい
	- iterm2という高機能なターミナルもおすすめ
- LInux
	- デスクトップ環境がある場合はその環境のターミナル(gnome terminal, lxterminal, などなど）
	- cuiならそもそもコマンドを叩けます。
---

### スクリプトファイルを書くエディタを用意する
---

### クロスプラットフォーム
	- VSCode, Atom: WEB系の技術で作られたエディタ(nodejs,electron)  
    利用者多いのとPython開発のサポートや拡張機能があります
		- ほかにもadobe系のBracketsとか
	- Sublime Text3 （有償）
	- PyCharm(intellij系): jetbreain社の統合開発環境（IDE） 
	- vim/emacs: わかる人に聞いてください（サーバー上ならこちらの方が良い場合）
	- Eclipse + pydev

---

### ほかOSごと

- Win
	- NotePad++
	- サクラエディタ
- Mac
	- 基本クロスプラットフォームのものが良さげ
	- [Coda](https://panic.com/jp/coda/)
		- [Panic - Nova](https://panic.com/jp/nova/)
	- [TextMate: Text editor for macOS](https://macromates.com/)
	- Xcodeはむりだったかな？
- Linux:割愛（すみません。。クロスプラットフォーム向けは良い選択肢）
- Python向けのエディタも沢山あります
	- そのほかたくさんあるので、気に入ったものを探すと良いです
    - **linkを用意**

---
### おまけ:VS Codeでおすすめの拡張機能


- Python for VSCode:
    - MS公式提供の拡張機能。コード補完やデバッグ, 開発で利用するパッケージを統合サポートしてくれる（テスト, 静的解析）
---

### おまけ:VSCodeでおすすめの拡張機能

- setting sync
- [TODO Highlight - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
- markdownのプレビュー系
- liveshare: ペアプロするのにオススメ

---

### Python for VS Codeで使うとオススメなライブラリ

Pythonのコードを扱う時間が増えてきたらオススメなライブラリ

- flake8
- autopep8(自動フォーマット): black, yapf
- mypy:  
- isort: 

### まとめ

- 試す環境:CUIとか
- 書く環境:エディタ IDE

---

---

### Python環境を作る

---

### 開発をするときは基本的に仮想環境がおすすめ

---

### Why?

- システムの環境に様々なパッケージを入れることで綺麗でなくなる
- 開発中はなるべく利用するパッケージを固定にしたい

---

### 仮想環境の種類

- ユーザーアカウント
- ローカルの実行環境:ここを扱う => 仮想実行環境
- 仮想マシンでOSごと
    - コンテナも -> dockerとかも

---

### Python仮想環境の選択肢

- Pythonの各バージョン依存
	- python3のvenv
- 複数バージョン
	- pipenv:依存問題に対処しやすい
	- virtualeenv:pipenvでも使われてる
- その他
	- flit, poetry, pyenv

--- 

### vent

Pythonの実行環境に入る標準の仮想実行環境作成ツール

`python -m vena .venv` で実行時のディレクトリに仮想実行環境を作成

Win: `.venv¥Scripts¥activate.bat`

Mac/Linux: `source .venv/bin/activate`

 にて仮想実行環境に入る

抜けるとき: `deactivate`

---

### pipenv

Pypa公式になったpipの依存管理ツール

依存管理ツールとは？

開発中にバージョンを固定してやりたい。

バージョン固定 -> 同じ環境で開発し続けれる -> 計画的な依存ライブラリのバージョンアップができる

pipにも requirements.txtがある

ただ不便な面がある -> [Pipfile/Pipfile.lockの必要性 -requirements.txtを用いる手法と比較して- - Qiita](https://qiita.com/miyashiiii/items/92e6f745a940c4df2ddd)

別の環境（例えば本番環境と開発環境が分かれてるとき）でも同じ環境が作れる

ぶっちゃけこちらが素晴らしい解説だったので ~~丸投げ~~ 参照

[Pipenv のご紹介 - Google スライド](https://docs.google.com/presentation/d/1tmdB8TpJKcRGk95PoD0Q0jzeMCsBv1EddJ-LVYLj_mY/edit#slide=id.p)

まとめ[これいらないかも]

Pip/requiments.txtだと依存ライブラリの更新管理が面倒（できるけど）
Pipenvだと、pipfileをいじることで完結する。lock処理が遅い

---

### そのほか

Poetry: [sdispater/poetry](https://github.com/sdispater/poetry)

利用パッケージの依存関係の管理に加えて、パッケージ作成をするときのファイル(setup.pyなど)も生成してくれる。


パッケージ作成者ならこちらが使いやすいラシイ

Flit

pyproject.tomlでパッケージ管理、ビルド可能。仮想環境は作る必要がある

[takluyver/flit: Simplified packaging of Python modules](https://github.com/takluyver/flit)

---

### pyenv

- pythonの複数バージョンをインストールしやすくする, 管理しやすくするものがコア
- わかっている人向けで、複数の実行環境が必要な人向け（特に2.7系, 3系の古いもの
- 今後必要になるかは不明（特に2.7系は来年1/1にEOLです, 3.5まではEOLです）
- そもそもWinで使えない

---
pyenv使い方ミスるといつのまにかわけわからなくなるからおススメしません！
（3.7つかってるとおもったら3.5を入れてたり、pyenv側のコマンド使わない方が安全かもしれない）

---

### まとめ

---

### 終わり

---

### LT用

---

### おまけ: iPad ProでPythonの開発環境を作る

---

### ええ、iPad ProでPython開発環境？

---

### Why?
---

### iPad Proは軽くてパワフル。軽さは正義

---

### 以上

---

### 作り方

---

### pythonistaがあればよくない ？

---

### まあそうなんだけど
---

### ディストリビューションに縛られず

---

### デスクトップやサーバー環境と同じがいい

---
### 今のところこうしてる

- 適当なサーバー+VPN
- エディタ
- sshクライアント
- Gitクライアント

---

適当なサーバー:家（というか事務所）に

クラウドとかでもよし(AWS, MS, Google)
使いたい時に動かして接続

---

接続？
Sshクライアント

***

とか

***

---

どうやってPython書くの？

Vim/Emacでも

iPadのエディタ

Textatic おすすめ

ほかにも色々

---

### コードの管理は？

（そもそもそんなにコード書けるのか？）

Githubにあるコードをローカルでみたい時に

Gitクライアント

workingcopy

---

### おまけのおまけ

---

### ちなみにAndroidだと

### Termuxというアプリ

サンドボックス+コンテナでAndroidでLinuxが動く！！！

なので、1台で割と開発環境ができる。裏やしい

### もっといいもの

Chromebook

- chromeOS+Linux+Androidアプリ動く（ざっというとそういうもの）
- Pixelbookが日本に来たら欲しかった！😂

---

### 今後

---

### リモート環境だとちょっとネット環境心配...

---

### 

- SBCをもつ！つまりラズパイとか！！
- ラズパイ4来たら勝つのでは？（メモリ最大4GB積むのでかなり動くと思う）
- ラズパイ+ssh/リモートデスクトップ+キーボード, マウス, あれ、ラズパイとモニターがあればよくね -> iPad Proいらなくね？


---

### まとめ

---

### iPad ProでPython開発はできるがネットがないと辛い

---

### 

---
### iOS13だとよりデスクトップ環境らしくなるのでさらに期待！

- WEB IDEが動く可能性あり, 
    - VSCode for cloud的なもの
