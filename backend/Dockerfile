FROM python:3.12-slim

WORKDIR /app

# uvを公式イメージからコピー
COPY --from=ghcr.io/astral-sh/uv:latest /uv /usr/local/bin/uv

# uvが正しくインストールされたか確認
RUN uv --version

# 依存関係ファイルをコピー
COPY backend/pyproject.toml ./

# 依存関係をインストール
RUN uv sync --no-install-project

# アプリケーションコードをコピー
COPY backend/ .

# プロジェクトを同期
RUN uv sync