# 🚗 App Tính Giá Thuê Xe

Ứng dụng web (PWA) giúp tính giá thuê xe VinFast VF3 2026 và theo dõi doanh thu.
Cài được vào màn hình chính điện thoại như một app thật và **chạy được khi không có mạng**.

## Tính năng

- **Tính giá** (`index.html`): nhập khách, biển số, ngày thuê, đơn giá, tiền cọc và các
  loại phụ phí (vượt km, quá giờ, sạc pin, vệ sinh, khử mùi, VETC...). Tự tính tổng tiền,
  tiền trả khi nhận xe và số còn lại phải thu. Lưu đơn vào máy.
- **Doanh thu** (`doanhthu.html`): tổng hợp các đơn đã lưu, lọc theo Hôm nay / Tháng này /
  Chọn tháng, xem tổng doanh thu, xuất file Excel/CSV, xoá đơn.
- **Cài như app (PWA)**: có nút "Cài đặt" trên trình duyệt hỗ trợ; chạy offline nhờ service worker.
- **Dữ liệu lưu cục bộ** trên trình duyệt/thiết bị (localStorage) — không cần server, không gửi đi đâu.

## Cách dùng

### Chạy thử trên máy
Vì có service worker nên cần mở qua một web server (không mở trực tiếp file://):

```bash
# Python (có sẵn trên hầu hết máy)
python3 -m http.server 8080
# rồi mở http://localhost:8080
```

### Cài vào điện thoại
1. Mở trang web (sau khi deploy) bằng Chrome/Safari trên điện thoại.
2. Bấm nút **Cài đặt** hiện trên app, hoặc menu trình duyệt → "Thêm vào màn hình chính".

## Triển khai (deploy)
Đây là web tĩnh, có thể deploy lên bất kỳ hosting tĩnh nào: GitHub Pages, Vercel, Netlify...
Chỉ cần đẩy toàn bộ thư mục lên là chạy.

## Cấu trúc

| File | Vai trò |
|------|---------|
| `index.html` | Trang tính giá thuê xe |
| `doanhthu.html` | Trang doanh thu / thống kê |
| `manifest.json` | Khai báo PWA (tên, icon, màu...) |
| `sw.js` | Service worker — chạy offline |
| `icon.svg` | Icon của app |
