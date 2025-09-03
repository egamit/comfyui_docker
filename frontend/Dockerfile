# 最新のLTS版Nodeイメージをベースとする
FROM node:lts

# 作業ディレクトリを設定
WORKDIR /app

# package.jsonとpackage-lock.jsonをコピー
COPY ./frontend/package*.json ./

# アプリケーションの依存関係をインストール
RUN npm install

# アプリケーションのソースコードをコピー
COPY ./frontend/ ./

# アプリケーションをビルド
RUN npm run build
