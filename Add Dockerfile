# Pythonの軽量イメージをベースにする
FROM python:3.11-slim

# 作業ディレクトリを作成
WORKDIR /app

# 必要なライブラリをインストールするための準備
COPY requirements.txt .

RUN apt-get update && apt-get install -y default-libmysqlclient-dev gcc \
    && pip install --no-cache-dir -r requirements.txt

# プロジェクトのコードをコピー
COPY . .

# コンテナの8000番ポートを開放
EXPOSE 8000

# Djangoの開発用サーバーを起動
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
