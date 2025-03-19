FROM python:3.10

# 標準出力のバッファリングを無効にする(ログの即時表示等、あると便利）
ENV PYTHONUNBUFFERED=1

# nginxとUNIXソケット通信用のファイルの保存場所作成
RUN mkdir -p tmp/sockets

# 作業ディレクトリを指定
WORKDIR /usr/src/app

# ローカルのrequirements.txtをコンテナの/usr/src/app直下に置く
COPY requirements.txt /usr/src/app

# 依存関係をインストール
RUN pip install --upgrade pip && pip install -r requirements.txt

# プロジェクトのコードをコピー
COPY . /usr/src/app

# Djangoのポートを開放（通常8000番ポート）
EXPOSE 8000

# アプリケーションを実行
CMD ["bash", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8000"]