# 情報科学演習 I,II レポート　テンプレート

- [基本的な使い方](#基本的な使い方)
- [具体的な作業内容](#具体的な作業内容)
  - [自分用のリモートリポジトリの作成](#自分用のリモートリポジトリの作成)
  - [リポジトリをローカルにコピーし作業用ワーキングディレクトリを作成](#リポジトリをローカルにコピーし作業用ワーキングディレクトリを作成)
  - [作業用ブランチを作成](#作業用ブランチを作成)
  - [編集作業](#編集作業)
- [レポートの書き方](#レポートの書き方-indexhtml-の更新)
  - [日本語的な注意事項](#日本語的な注意事項)
  - [HTML的な注意事項](#html的な注意事項)
- [発展的な使い方](#発展的な使い方)

## 基本的な使い方

1. テンプレートリポジトリをコピーして自分のリポジトリーを作る
1. 自分のリポジトリーで、作業用ブランチを作成する
   - 今後、作業用ブランチは下川への提出毎に新たに作成する
1. 作業用ブランチ上でレポートを作成（更新）する
1. 完成したレポートをサーバにアップロードする
1. Pull Request を送る
1. Pull Request を送ったことを下川にメールする（本来は不要だが、5. の作業で設定が不足すると通知が飛ばないから）
1. 提出したので、次の作業用ブランチを作成する
1. 下川から OK のリプライが来たら終了。NG だった場合は、下川からのリプライにしたがって、7. で作成した**新しい作業用ブランチ**上でレポートを更新(3. に戻る)

## 具体的な作業内容

### 自分用のリモートリポジトリの作成

1. ブラウザで[このリポジトリー](https://github.com/smkwlab/ise-report-template)にアクセスし `Use this template`  ボタンをクリック
1. リポジトリ作成画面になる
   - `Owner` は `smkwlab` のまま
   - `Repository name` は、 `k99rs999-ise-report1` のように自分の学籍番号を入れ、さらに情報科学演習I(あるいはII)のレポートであることが分かるような名前にする
     - 前期の **情報科学演習I** と後期の **情報科学演習II** では別のリポジトリーを作る
   - 公開範囲は `Private` のまま
1. `Create repository from template` ボタンをクリック

### リポジトリをローカルにコピーし、作業用ワーキングディレクトリを作成

1. 作成されたリポジトリーの画面で `Code` ボタンをクリック
1. `Open with GitHub Desktop` をクリック
1. 自分のPCでリポジトリーを置くディレクトリを確認して `Clone` ボタンをクリック

### 作業用ブランチを作成

1. GitHub Desktop で![Current Branch](GitHubDesktop-branch.png)ボタンをクリック
1. `New Branch` ボタンをクリック
1. `Name` を **1st-draft** とする。*草稿第1版*という意味
1. `create branch` ボタンをクリック
1. `Publish branch` ボタンをクリック
1. 先程の `Current Branch`が、`main` ではなく `1st-draft` に変わっていることを確認

### 編集作業

1. 現在の草稿用ブランチが選択されていることを確認して index.html を編集
   - `Open in Visual Studio Code` をクリックして Visual Studio Code で作業
   - このとき、Visual Studio Code の左下に、ブランチの名前が表示されている
   - 必要に応じて別のファイル（画像など）を追加したり、スタイルファイルを変更して良い
1. VScode のプレビューなどで、問題ないことを確認したら、GitHub Desktop で commit
1. `Push origin` をクリックして、リモートリポジトリーに Push
1. 作成したレポートを www-st のレポートのディレクトリにアップロードする
   1. アップロードには WinSCP または FFFTP などを利用する
   1. 学外からアップロードする際には KIND VPN を利用する
   1. アップロードするディレクトリは、自分のホームディレクトリ/public_html/semi3a/ （後期は semi3b）
   1. ブラウザで、正常に閲覧できることを確認
1. `Create Pull Request` をクリックして、**Pull Request** を作成
1. ブラウザが開くので、`Write` タブに変更点などを記述
1. 右側の `Reviewers` をクリックし、`Type or choose a user` フィールドに `toshi0806` を入力して下川のアカウントにチェックが入るのを確認
   - 2回目以降の Pull Request では、toshi0806 の右横の `Request` をクリックするだけで良い
1. `Create pull request` ボタンをクリック
1. 念のため、下川 <toshi@is.kyusan-u.ac.jp> 宛に提出したことをメールで連絡
1. 次の草稿用に新しいブランチを作成する
   1. `Current Branch` ボタンをクリック
   1. `New Branch` ボタンをクリック
   1. `Name` を **2nd-draft** など、次の版であることが分かる名前にする
   1. 下の `Create branch based on...` は直前の草稿のブランチ (次が 2nd なら前は 1st) を選択
   1. `Create branch` ボタンをクリック
   1. `Publish branch` ボタンをクリック
1. 下川からの返事を待つ
1. 返事の内容は、リモートリポジトリの `Pull Requests` タブの中にある
   - そこにも見当たらなければ `1 Closed` のようなリンクをクリックすると見えるはず
   - 見当たらなければ下川に問い合わせる
   - 下川は、添削結果を返信する際に、皆さんの草稿用ブランチの内容を main ブランチに反映させる作業(merge) もしている
   - したがって、返信が来たときには、リポジトリ上の main ブランチは提出した草稿と同じ内容に更新されている
1. OK ならば以下の通り
   - 最終版の原稿に `final` というタグを打つ
      - GitHub Desktop の `History` で一番上にある履歴を右クリック
      - `Create Tag...` をクリック
      - `Name` に **final** と入力し `Create Tag` ボタンをクリック
      - 提出終了。お疲れ様。
1. NG ならば現在の草稿上で編集 (1. に戻る)

## レポートの書き方 (index.html の更新)

### 情報科学演習x のレポートとしての注意事項
- 情報科学演習I のレポートにおけるプログラミングテストに関する記述では、すべての問題について記述すること

### 日本語的な注意事項
- である体で書くこと
- 長い文を書かず、適切に文を分割すること
  - 「が」で続けるのは良くない
- 適切な内容で段落を分割すること
- 文の途中に箇条書きを入れないこと
- すべての図や表は本文中で参照すること
- まとめは感想ではない。
  - 今後の課題を除いて、それ以前の本文で記述されていないことを、まとめに書いてはいけない

### HTML的な注意事項
- title 要素と h1 要素にレポートのタイトルを記述
- header 要素中の author クラスが指定された p 要素に著者情報を記述
- 報告書本体は h2 以下のレベル (h2, h3, h4,...) で構造を作る
  各 hX 要素には自動で採番される
  - h2 の構成については、このまま変更なしで問題ないと思われる
- 日本語のレポートらしくするために p 要素については先頭行の行頭に空白が入るようにしてある
  - しかし、これが気に入らない場合はスタイルを変更してよい
- 図や表にはキャプションを入れる。入れ方はサンプルの index.html を参考にすること
- プログラムを記述する際には、< の後に空白を入れるように注意すること。空白がないと HTML の開始タグと誤認識され表示が乱れる。
- 段落を書くときも、1文1行で記述すること
  - 差分が見やすいし、編集指示も出しやすい

## 発展的な使い方
`WSL2` と `Docker Desktop` をインストールしておくと、
`textlint` というツールを使って日本語の表記について機械的なチェックができる。

1. [ドキュメント](https://github.com/smkwlab/latex-environment/blob/main/SETUP-DevContainer.md)にしたがって、`WSL2`と`Docker Desktop` をインストール
   -  このドキュメントには `LaTeX 処理環境の構築` と書いてあるが無視して良い
1. `VScode` でファイルを保存する度に「問題」ウィンドウに `textlint` の実行結果が表示される
1. 指摘内容にしたがって、文章を推敲