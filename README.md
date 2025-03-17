# 家族伝言板アプリ

複数のスマートフォンやデバイスから利用できる、家族向け伝言交換アプリです。

## 主な機能

- 家族メンバーごとのログイン機能
- 伝言の投稿・閲覧機能
- プライベート伝言機能（宛先のみ閲覧可能）
- 既読管理機能
- 複数デバイス間でのデータ同期（Firebase設定時）

## 使用方法

1. ログイン画面で家族メンバーを選択し、パスワードを入力してログインします
   （初期パスワードは全員「1234」に設定されています）
2. ログイン後、伝言の投稿や閲覧が可能になります
3. 「宛先のみ閲覧可能」にチェックを入れると、その伝言は宛先と送信者のみが閲覧できます

## 複数デバイス間でのデータ同期について

このアプリは以下の2つのモードで動作します：

1. **ローカルモード**（デフォルト）：
   - データは各デバイスのブラウザに個別に保存されます
   - インターネット接続は不要です
   - 複数デバイス間でデータは同期されません

2. **クラウドモード**（Firebase設定時）：
   - データはFirestoreデータベースに保存され、複数デバイス間で同期されます
   - インターネット接続が必要です
   - すべてのデバイスで同じデータを共有できます

## Firebase設定方法

クラウドモードを有効にするには：

1. [Firebase Console](https://console.firebase.google.com/)にアクセスし、新しいプロジェクトを作成します
2. Firestoreデータベースを作成します
3. Webアプリを追加し、設定情報を取得します
4. script_cloud.jsファイル内のfirebaseConfig変数を実際の値で置き換えます

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT_ID.appspot.com",
  messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

## 技術情報

- HTML/CSS/JavaScriptで構築
- Firebase Firestoreを使用したデータ同期（オプション）
- レスポンシブデザイン対応
