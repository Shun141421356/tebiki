# てびき PWA — セットアップガイド

## ファイル構成

```
tebiki/
├── index.html      ← メインアプリ
├── manifest.json   ← PWA設定
├── sw.js           ← Service Worker（オフライン対応）
├── icon-192.svg    ← アプリアイコン
└── icon-512.svg    ← アプリアイコン（大）
```

## ローカルで試す方法

ファイルをダブルクリックするだけでは Service Worker が動きません。
簡易HTTPサーバーが必要です。

### Python がある場合
```bash
cd tebiki
python3 -m http.server 8080
# ブラウザで http://localhost:8080 を開く
```

### Node.js がある場合
```bash
npx serve tebiki
```

## ホーム画面に追加する方法

### Android（Chrome）
1. ブラウザで開く
2. アプリ内に「ホーム画面に追加」バナーが表示される
3. 「追加する」をタップ

### iPhone（Safari）
1. Safari でページを開く
2. 下部の「共有」ボタン → 「ホーム画面に追加」
3. 「追加」をタップ

## 無料でネットに公開する方法（PWA本番運用）

### GitHub Pages（推奨・無料）
1. GitHub アカウントを作成
2. 新しいリポジトリを作成（名前例: `tebiki`）
3. このフォルダのファイルをすべてアップロード
4. Settings → Pages → Source: main ブランチを選択
5. `https://ユーザー名.github.io/tebiki/` でアクセス可能

### Netlify（ドラッグ&ドロップで公開）
1. https://netlify.com にアクセス
2. tebikiフォルダをドラッグ&ドロップ
3. 自動的にURLが発行される

## データについて

- すべてのてびきはブラウザの localStorage に保存されます
- ブラウザ/デバイスをまたいでの同期は現在非対応（今後の拡張予定）
- ブラウザのデータを消去すると削除されるため、定期的にPDFで書き出しておくことを推奨します
