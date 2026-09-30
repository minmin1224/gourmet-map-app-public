# 即席グルメMAP

ジャンル・予算・徒歩距離を選ぶと、現在地周辺のおすすめ飲食店を地図とリストで表示する個人用Webアプリです。

- インストール不要、ブラウザだけで動作します
- 会員登録・個人情報の入力は不要です
- 店舗検索はホットペッパーグルメAPI(リクルート)を利用し、Cloudflare Workers上の中継サーバー経由で呼び出します(APIキーはサーバー側にのみ保持)
- スマートフォンのホーム画面に追加してPWAとして利用できます

## 公開URL

`index.html` がランディングページ、`app/index.html` がアプリ本体です。GitHub Pagesではリポジトリのルート(このファイル)がそのまま公開されます。

## ローカルでの動作確認

```
python -m http.server 8000
```

その後 `http://localhost:8000/` を開いてください(位置情報とPWA機能はhttp(s)配信時のみ動作します)。

## 中継サーバー(Cloudflare Workers)

`app/index.html` 内の `WORKER_BASE` は、別途デプロイしたCloudflare Workerを指しています。Workerのソースはこのリポジトリには含めていません。
