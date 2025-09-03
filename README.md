# react_express_template
React-Expressのテンプレートです

# 説明
React、Expressを使いd-in-d環境での開発を簡単に始められるテンプレートです。

# docker-composeについて
## 開発環境
### docker-compose.yml
- 開発環境用のdocker-composeファイルです。
- Reactもnode上で動かします。

## 本番環境
### docker-compose.prod.yml
- 本番環境用のdocker-composeファイルです。
- Reactはbuildしたうえでnginxで動かします。nginx.confの設定は最低限のものになっていますので実際に使う時は見直してください
- テンプレートから作成しただけだと動かせません。こちらのファイルから起動する前に以下を行ってください
1. npmで環境を再作成
- ターミナルでfrontendディレクトリへ移動
- rm -rf node_modules package-lock.json ← 今の構成を一旦削除します
- npm install ← nodeの環境を再作成
2. ビルドします
- npm run build
- 権限エラーが出た場合は以下を実行してから再度ビルドしてください
- sudo chown -R codespace:codespace /workspaces/{環境に合わせたリポジトリ名}/frontend/build

# dockerコマンドメモ
## 起動
- テスト：docker compose up -d
- 本番：docker-compose -f docker-compose.prod.yml up -d

## 停止
- テスト：docker compose stop
- 本番：docker-compose -f docker-compose.prod.yml stop