# 話のネタ帳・公開用

GitHubにアップロードするのは、このフォルダ内の `index.html` と `server.mjs` です。ZIPそのものではありません。
RenderのWeb Serviceで Build Command: `echo ready`、Start Command: `node server.mjs`。Environment に `OPENAI_API_KEY` と `APP_PASSWORD` を設定してください。APIキーやパスワードをGitHubに置かないでください。

公開URLにアクセスするとログイン画面が出ます。ユーザー名は `user`、パスワードは設定した `APP_PASSWORD` です。共有した相手はAI APIの利用を生じさせるため、共有相手に合わせた利用制限を設定してください。

ブラウザごとにメモが保存されます。公開サイトはローカルの `localhost:3000` とは別の保存領域なので、既存メモは自動的に引き継がれません。
