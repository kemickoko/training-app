FROM python:3.12.4

# 作業ディレクトリを作成
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
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]