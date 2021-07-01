# 情報科学演習 I,II レポート　テンプレート

## 基本的な使い方

1. テンプレートリポジトリをコピーして自分のリポジトリーを作る
2. 自分のリポジトリーで、作業用ブランチを作成する
3. 作業用ブランチ上でレポートを作成（更新）する
4. Pull Request を送る
5. Pull Request を送ったことを教員にメールする（本来は不要だが、4. の作業で設定が不足すると通知が飛ばないから）
6. 次の作業用ブランチを作成する
7. 教員から OK のリプライが来たら、完成物をサーバにアップロード。NG だった場合は、教員からのリプライにしたがって、6. で作成した新しい作業用ブランチ上でレポートを更新。
8. 再度 Pull Request を送る(4. に戻る)

## 具体的な作業内容

### 自分用のリモートリポジトリの作成

1. ブラウザで[このリポジトリー](https://github.com/smkwlab/ise-report)にアクセスし `Use this template`  ボタンをクリック
1. リポジトリ作成画面になるので、`Owner` は `smkwlab` のまま。 `Repository name` は、 `k99rs999-ise-report1` のように、
　自分の学籍番号を入れて情報科学演習1(あるいは2)のレポートであることが分かるような名前にする。
    - 前期の **情報科学演習1** と後期の **情報科学演習2** では別のリポジトリーを作る
1. 公開範囲は `Private`' のまま
1. `Create repository from template` ボタンをクリック

### リポジトリをローカルにコピーし、作業用ワーキングディレクトリを作成

1. 作成されたリポジトリーの画面で `Code` ボタンをクリック
1. `Open with GitHub Desktop` をクリック
1. 自分のPCでリポジトリーを置くディレクトリを確認して `Clone` ボタンをクリック

### 作業用ブランチを作成

1. GitHub Desktop で、![ブランチボタン](GitHubDesktop-branch.png) をクリック
1. `New branch` ボタンをクリック
1. `name` を **1st-draft** とする。*草稿第1版*という意味
1. `create branch` ボタンをクリック
1. `Publish branch` ボタンをクリック
1. 先程の、`Current branch`が、`main` ではなく `1st-draft` に変わっていることを確認

### 編集作業

1. 現在の草稿用ブランチが選択されていることを確認して index.html を編集
   - `Open in Visual Studio Code` をクリックして Visual Studio Code で作業
   - このとき、Visual Studio Code の左下に、ブランチの名前が表示されている
   - 必要に応じて別のファイル（画像など）を追加したり、スタイルファイルを変更して良い
1. VScode のプレビューなどで、問題ないことを確認したら、GitHub Desktop で commit
1. `Push origin` をクリックして、リモートリポジトリーに Push
1. `Create Pull Request` をクリックして、**Pull Request** を作成
1. ブラウザが開くので、変更点などを記述。
1. 右側の `Reviewers` をクリックし、`Type or choose a user` フィールドに `toshi0806` を入力して下川のアカウントにチェックが入るのを確認
1. `Create pull request` ボタンをクリック
1. 念のため、下川 <toshi@is.kyusan-u.ac.jp> 宛に提出したことをメールで連絡
1. 次の草稿用に新しいブランチを作成する
   1. `Current branch` ボタンをクリック
   1. `New branch` ボタンをクリック
   1. `name` を **2nd-draft** など、次の版であることが分かる名前にする
   1. 下の `Create branch based on...` は直前の草稿のブランチ (次が 2nd なら前は 1st) を選択
   1. `Create branch` ボタンをクリック
   1. `Publish branch` ボタンをクリック
1. 下川からの返事を待つ
1. OK ならば、index.html や画像ファイルなどをサーバにアップロードし、下川にアップロード完了のメールを送信
   1. これでアップロード確認のメールが来たら提出終了
   1. アップロードに不備があったら、再度アップロードし直して下川にメール送信
1. NG ならば現在の草稿上で編集 (1. に戻る)
