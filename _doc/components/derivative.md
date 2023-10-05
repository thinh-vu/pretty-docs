---
title: Chứng khoán phái sinh
sections:
    - Dữ liệu giá lịch sử
---

## Dữ liệu giá lịch sử

> Xem chi tiết mục [3.4.1 📈 Truy xuất dữ liệu giá lịch sử](#341--truy-xuất-dữ-liệu-giá-lịch-sử) cùng với thông tin giá chứng khoán cơ sở.

### Dữ liệu khớp lệnh lịch sử

<details>

<summary>Minh họa bảng dữ liệu khớp lệnh Phái sinh - CK Rồng Việt </summary>

![livedragon_derivative_match](https://raw.githubusercontent.com/thinh-vu/vnstock/beta/resources/images/livedragon_derivative_history_match.png)

</details>

Để truy vấn dữ liệu từ hàm này, bạn cần có cookie người dùng (không cần đăng nhập) của chứng khoán Rồng Việt. Các bước thực hiện như sau:
  1. Truy cập `https://livedragon.vdsc.com.vn/all/all.rv`
  2. Mở `Developer Tools` trên trình duyệt, sử dụng F12 hoặc `Ctrl` + `Shift` + `I` trên Windows hoặc `Cmd` + `Option` + `I` trên macOS
  3. Chuyển đến tab `Network` và chọn mục `Fetch/XHR`
  4. Mở bất kỳ mục request nào trong tab này, tìm mục `Header` của request
  5. Tìm và copy giá trị của `Cookie` trong request này để điền vào bước tiếp theo dưới đây trước khi gọi hàm

```python
cookie = 'GIÁ TRỊ COOKIE CẦN PASTE VÀO ĐÂY'
derivatives_historical_match (symbol='VN30F2308', date='2023-07-24', cookie=cookie)
```