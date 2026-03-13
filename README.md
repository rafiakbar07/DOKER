# WordPress Docker Compose

Project ini menjalankan WordPress menggunakan Docker Compose dengan MySQL sebagai database dan Redis sebagai object cache.

## Services

Project ini menggunakan 3 container:

- WordPress
- MySQL
- Redis

## Cara Menjalankan Project

1. Clone repository

2. Jalankan Docker Compose

docker compose up -d

3. Buka browser

http://localhost:8000

4. Install WordPress melalui halaman instalasi.

## Testing

### Cek Container

docker ps

Harus muncul 3 container:

- wordpress
- mysql
- redis

### Test Redis

docker exec -it redis redis-cli

Lalu ketik

ping

Output:

PONG

## Jawaban Pertanyaan

### Kenapa perlu volume untuk MySQL?
Volume digunakan agar data database tidak hilang ketika container dihentikan atau dihapus.

### Apa fungsi depends_on?
depends_on memastikan container WordPress dijalankan setelah container MySQL dan Redis.

### Bagaimana WordPress connect ke MySQL?
WordPress menggunakan environment variable WORDPRESS_DB_HOST=mysql untuk terhubung ke container MySQL melalui Docker network.

### Apa keuntungan Redis untuk WordPress?
Redis berfungsi sebagai object cache sehingga dapat mempercepat akses website dan mengurangi beban database.
