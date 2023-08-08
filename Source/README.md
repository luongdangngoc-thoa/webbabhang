## ローカル環境構築

```
# クローン
git clone URL

# composer更新
composer update

# エラー「Please provide a valid cache path.」
# エラー「file_put_contents(xxxx/project-name/storage/framework/sessions/xxxxxx): failed to open stream: No such file or directory」「Please provide a valid cache path.」の対処法。キャッシュ用のディレクトリが存在しないことが原因なので手動作成
mkdir -p storage/framework/cache/data/
mkdir -p storage/framework/app/cache
mkdir -p storage/framework/sessions
mkdir -p storage/framework/views

# .env.exampleコピーして .envにリネーム (ローカルの環境に合わせる DB名:)
cp .env.example .env

# .env key値生成
php artisan key:generate

# シンボリック
php artisan storage:link
#ErrorException  : symlink(): No such file or directory 対策
rm public/storage

# パッケージインストール
npm install && npm run dev

# DBマイグレーション(利用時)
php artisan migrate (マイグレーションに変更あるときのみ)
php artisan migrate:fresh --seed (初期化してシーダーを実行する。)


# サーバ立ち上げ(ローカル)
php artisan serve
php artisan serve --host=0.0.0.0 #ホスト指定
```

## 開発環境

```
・言語: PHP8.0, JavaScript、SCSS
・DB: MySQL8.0
・フレームワーク: Laravel8

```

## 導入したプラグイン、パッケージ、ライブラリ

```
#--デバッグバー--
barryvdh/laravel-debugbar 
$ composer require barryvdh/laravel-debugbar
```
