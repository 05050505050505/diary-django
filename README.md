1.Python仮想環境の作成：
他の人が実行する際、仮想環境を使ってPythonパッケージのバージョンを揃えるのが良い方法です。
# プロジェクトのディレクトリで仮想環境を作成
python -m venv .venv

# 仮想環境をアクティブにする
# Windowsの場合
venv\Scripts\activate
# Mac/Linuxの場合
source .venv/bin/activate

# 2.必要なパッケージをインストールするための requirements.txt：
現在の環境でインストールされているパッケージをrequirements.txtに出力
pip freeze > requirements.txt
他の人はこの requirements.txt を使って、必要なパッケージをインストールする。
pip install -r requirements.txt

# 3. データベースの準備
Djangoのアプリケーションを動かすためには、データベースの設定も必要。他の人が初期状態から動かせるように、データベースのマイグレーションを行う必要がある。
データベースのマイグレーションを行う
python manage.py migrate
管理者アカウントの作成（任意）
python manage.py createsuperuser

# 4. 実行方法
Djangoの開発用サーバーを使って、プロジェクトを動かすことができる。
サーバーを起動
python manage.py runserver
http://127.0.0.1:8000 であなたのアプリケーションにアクセスできるようになる。
