# 話のネタ帳（データベース保存版）

メモをPostgreSQLへ保存するため、スマホやパソコンを変えても同じネタを表示できます。全利用者が同じノートを共有する構成です。

## GitHubへアップロードするファイル

このフォルダ内の `index.html`、`app.js`、`server.mjs`、`package.json` を、GitHubリポジトリの一番上にアップロードします。ZIPそのものや、外側のフォルダはアップロードしません。

## Neonで無料データベースを作る

1. https://neon.com/ でアカウントを作成します。
2. New Projectからプロジェクト名を `hanashi-no-netacho` として作成します。
3. Connect画面に表示される接続文字列（`postgresql://...`）をコピーします。
4. 接続文字列はパスワードと同じ秘密情報です。GitHubやチャットに貼らないでください。

## Renderの設定

Build Commandは `npm install`、Start Commandは `npm start` にします。

Environment Variablesには次の3つを登録します。

- `OPENAI_API_KEY`: 自分のOpenAI APIキー
- `APP_PASSWORD`: アプリを開くための長いパスワード
- `DATABASE_URL`: Neonでコピーした接続文字列

保存後、Manual DeployからDeploy latest commitを実行します。最初の起動時に必要なテーブルが自動作成されます。

## ログイン

ユーザー名は `user`、パスワードはRenderの `APP_PASSWORD` に登録した値です。同じログイン情報を使う全端末で、同じメモが表示されます。

旧版を使っていたブラウザで新版を最初に開くと、そのブラウザ内に残っている既存メモをデータベースへ自動移行します。別URL・別ブラウザに保存されたメモは自動では見つけられません。
