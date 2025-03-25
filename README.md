# VRWEB

Đây là mã nguồn và cấu hình triển khai của dự án **VRWEB**, một ứng dụng web thực tế ảo viết bằng Unity

## 🚀 Tính năng

- Ứng dụng web chạy qua máy chủ NGINX
- Sử dụng Docker để dễ dàng triển khai
- Triển khai tự động (CI/CD)

---

## 📁 Cấu trúc thư mục

```
vrweb/
├── WEB/                  # Mã nguồn frontend/web app
├── nginx/
│   └── ssl/              # Chứa chứng chỉ SSL
├── README.md             # Tệp hướng dẫn này
├── docker-compose.yml    # Cấu hình Docker Compose
├── nginx.conf            # Cấu hình NGINX
```

---

## 🐳 Chạy dự án cục bộ

Sử dụng Docker để chạy ứng dụng trên máy cá nhân:

```bash
docker-compose up --build
```

Sau đó truy cập tại: [http://localhost:8009](http://localhost:8009)

---

## 📦 Triển khai thủ công

Triển khai thủ công bằng SSH:

```bash
ssh codelab@101.96.66.219
cd ~/vrweb
git pull origin main
docker-compose down
docker-compose up -d --build
```

---

## 🤖 CI/CD tự động (GitHub Actions)

Mỗi khi có commit mới lên nhánh `main`, GitHub Actions sẽ tự động:

1. SSH vào server
2. Pull mã nguồn mới nhất
3. Khởi động lại container Docker
