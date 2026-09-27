# GitHubへ登録する手順（初めての方向け）

## 方法A：GitHubのWeb画面から登録する

1. GitHubで新しいリポジトリを作成します。
2. リポジトリ名を決めます。
3. READMEを自動作成する設定は、今回のパッケージにREADME.mdが入っているので不要です。
4. リポジトリを作成したら「Add file」→「Upload files」を選びます。
5. このフォルダーの**中身**をまとめてアップロードします。
6. `index.html` がリポジトリの一番上の階層にあることを確認します。
7. 「Commit changes」で登録します。

### 大切な注意

ZIPファイルそのものをGitHub Pages用の本体として置くのではありません。

次のような構成になるようにしてください。

```text
リポジトリ/
├─ index.html
├─ README.md
├─ MANUAL.md
├─ START_HERE.md
├─ SECURITY.md
├─ CHANGELOG.md
├─ QA.md
└─ RELEASE_CHECKLIST.md
```

## GitHub PagesでWeb公開する場合

`index.html` がルートにあるので、GitHub Pagesの公開元をリポジトリの `main` ブランチ・ルート（`/`）に設定します。

公開後は、生成されたPagesのURLをChrome/Edgeで開いて動作を確認してください。

## 方法B：Gitを使う場合

PowerShellなどで、このフォルダーをカレントフォルダーにして次のように登録できます。

```powershell
git init
git add .
git commit -m "Release v46"
git branch -M main
git remote add origin https://github.com/あなたのユーザー名/あなたのリポジトリ.git
git push -u origin main
```

## 個人情報について

**実際の児童生徒のJSON、Excel、バックアップファイルはGitHubへアップロードしないでください。**

このパッケージには、個人データを含む `.json`、`.xlsx`、`.xls` を誤って追加しないための `.gitignore` も入れています。

## 最初の公開確認

公開後、次の順番で確認してください。

1. PagesのURLを開く
2. 「10分で始める」を開く
3. テスト用のダミー計画を1件作る
4. 保存状態を確認する
5. Excel取込を1回確認する
6. Excel出力→再取込を確認する
7. JSONバックアップ→復元を確認する
8. テスト後に不要な個人情報が残っていないことを確認する
