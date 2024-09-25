# LineBotForGPTCore(Only for o1-Preview)

このリポジトリは、LINE上で動作するo1-Preview向けのPythonベースのチャットボットです。このボットはChatGPT APIを使用して、ユーザからのメッセージに対してレスポンスを生成します。

## 機能
以下の機能を持っています。：

- Web設定: パラメーターをWeb画面で設定可能です。コードを変更する必要はありません。
- ボット会話: 設定したキャラクター性でChatGPTと会話できます。グループチャットにも対応します。

## セットアップ
以下のステップに従ってセットアップしてください：
1. Google Cloud Runでデプロイします：Google Cloud Consoleでプロジェクトを作成しCloud Run APIを有効にし、本レポジトリを指定してデプロイします。 デプロイの際は以下の環境変数を設定する必要があります。
2. 同じプロジェクト内でFirestoreを有効にします：左側のナビゲーションメニューで「Firestore」を選択し、Firestoreをプロジェクトで有効にします。
3. データベースを作成します：Firestoreダッシュボードに移動し、「データベースの作成」をクリックします。「ネイティブ」モードを選択します。
6. Cloud RunのURLに「/login」を付与して管理画面にログインし、パラメータを設定します
7. LINE Developerにログインします：https://account.line.biz/login
8. チャネルを作成し、webhookの宛先にCloud RunのサービスURLを指定します。

## 環境変数
- OPENAI_API_KEY: OpenAI APIのAPIキー。ChatGPTとWhisperで使用する。
- CHANNEL_ACCESS_TOKEN:LINEで発行したチャネルアクセストークンを設定してください。
- CHANNEL_SECRET:LINEで発行したチャンネルシークレットキーを設定してください。
- ADMIN_PASSWORD: 管理者パスワード。
- SECRET_KEY: DBに保存するメッセージの暗号化と復号化に使用される秘密鍵。
- DATABASE_NAME:FireStoreのデータベース名を指定してください。

## 注意
このアプリケーションはFlaskベースで作成されています。そのため、任意のウェブサーバー上にデプロイすることが可能ですが、前提としてはGoogle Cloud runでの動作を想定しています。デプロイ方法は使用するウェブサーバーによります。

Google Cloud run以外で動作させる場合はFirestoreとの紐づけが必要になります。

## ライセンス
このプロジェクトはMITライセンスの下でライセンスされています。
