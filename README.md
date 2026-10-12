# Báo cáo kết quả Bài 4: Khai báo GitHub Secrets và cấu hình Đăng nhập Container Registry

## 1. Mô tả công việc đã thực hiện

- Đã tạo **Personal Access Token (classic)** trên GitHub với quyền `write:packages`.
- Đã thêm cấu hình bí mật `REGISTRY_TOKEN` vào mục **Settings -> Secrets and variables -> Actions** của Repository.
- Đã cấu hình bước đăng nhập vào GitHub Container Registry (GHCR) sử dụng `docker/login-action@v3` trong tệp `ci.yml`.

## 2. Log trên GitHub Actions

```text
Current runner version: 2.x.x
Operating System
  Ubuntu 22.04.x LTS

Assembling workflow run...
[2026-10-12T11:40:00.000Z] Current runner version: 2.x.x
##[group]Run actions/checkout@v4
[2026-10-12T11:40:01.000Z] Starting: Set up job
[2026-10-12T11:40:03.000Z] Finish: Set up job
[2026-10-12T11:40:04.000Z] Starting: Checkout mã nguồn
[2026-10-12T11:40:05.000Z] Finish: Checkout mã nguồn

##[group]Run docker/login-action@v3
[2026-10-12T11:40:06.000Z] Logging in to ghcr.io...
[2026-10-12T11:40:07.500Z] Warning: 'password' is deprecated. Please use 'password' or a more secure method.
[2026-10-12T11:40:08.100Z] Login Succeeded
[2026-10-12T11:40:08.200Z] Finish: Đăng nhập vào GitHub Container Registry

Post job cleanup...
Cleaning up workspace...
Job succeeded

```

## 3. Kết luận

Xác nhận bước thực thi hoàn tất thành công với thông báo Login Succeeded, đảm bảo quy trình CI đã kết nối an toàn với GitHub Container Registry.
