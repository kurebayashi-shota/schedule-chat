# Schedule Chat App

LINE WORKS風の勤怠チャットアプリ（Laravel + Inertia.js + React + Vite）

## 📦 必要な環境

- PHP 8.4
- Composer
- Node.js 18+
- npm
- Docker / Docker Compose（任意）
- Git
- MySQL or PostgreSQL

---

## 🛠 セットアップ手順

### 1. リポジトリをクローン

```bash
git clone git@github.com:kurebayashi-shota/schedule-chat.git
cd schedule-chat
cp .env.example .env
//.envを修正
docker compose up -d
docker exec -it php_app -bash
composer install
exit
npm install

or

# 1. リポジトリをクローン
git clone git@github.com:kurebayashi-shota/schedule-chat.git
cd schedule-chat

# 2. .envファイルを作成
cp .env.example .env

# 3. .env を自分の環境に合わせて編集（DB_HOST=mysql など）

# 4. Docker コンテナを起動（初回ビルド込み）
docker compose up -d --build

# 5. PHPコンテナに入って依存関係をインストール
docker exec -it php_app bash
composer install
php artisan key:generate
php artisan migrate --seed
exit

# 6. Node依存関係をインストール（ホスト側）
npm install

# 7. Vite開発サーバーを起動（ホスト側）
npm run dev
