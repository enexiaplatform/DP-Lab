# DP Lab — Landing Page

Trang giới thiệu chính thức của **DP Lab** (Development – Passion), nhà phân phối môi trường nuôi cấy vi sinh **CulturaLab** tại Việt Nam.

Đáp ứng tiêu chuẩn ISO · USP · EP cho phòng QC dược phẩm, thực phẩm, nước và mỹ phẩm.

---

## Stack

Tĩnh — không build step.

- `index.html` — toàn bộ landing page (HTML + CSS + JS inline)
- `assets/` — logo và ảnh sản phẩm
- `vercel.json` — cấu hình Vercel (cache headers, security headers)

Lý do giữ tĩnh: load nhanh, deploy đơn giản, không phụ thuộc framework, dễ tinh chỉnh trực tiếp.

## Chạy local

Mở `index.html` bằng trình duyệt là được. Hoặc serve qua HTTP để form modal hoạt động chính xác:

```bash
# Python 3
python -m http.server 8080

# Node (nếu cài npx)
npx serve .
```

Mở http://localhost:8080

## Push lên GitHub

Repo: https://github.com/enexiaplatform/DP-Lab

```bash
cd "DP Lab"
git init
git add .
git commit -m "feat: landing page v1"
git branch -M main
git remote add origin https://github.com/enexiaplatform/DP-Lab.git
git push -u origin main
```

## Deploy lên Vercel

1. Vào https://vercel.com/new
2. Import repo `enexiaplatform/DP-Lab`
3. Framework Preset: **Other** (Vercel sẽ tự nhận diện tĩnh)
4. Build Command: để trống
5. Output Directory: để trống (root)
6. Deploy

Mỗi lần `git push` lên `main` sẽ tự động deploy preview + production.

## Cấu trúc

```
DP Lab/
├── index.html         # Landing page
├── assets/
│   ├── dp-lab-logo.png
│   ├── dehydrated.png
│   ├── ready-to-use.png
│   ├── bagged.png
│   ├── rtu-overview.png
│   ├── multi-format.png
│   └── rtu-catalog.png
├── vercel.json
├── .gitignore
└── README.md
```

## Sections trên trang

1. **Hero** — heading, CTA, flask SVG với badge ISO/USP/EP, hiệu ứng phân tử
2. **Stats bar** — 30+ sản phẩm · 3 dòng · ISO/USP/EP · 100% QC
3. **Về chúng tôi** — giới thiệu DP Lab + CulturaLab
4. **3 dòng sản phẩm chính** — Dehydrated · Ready-to-Use · Bagged
5. **Sản phẩm tiêu biểu** — showcase ảnh thật
6. **Lợi thế** — 6 điểm mạnh
7. **Ứng dụng** — Y tế · Thực phẩm · Nước · Dược phẩm
8. **CTA** — yêu cầu báo giá
9. **Footer** — logo, liên kết, copyright

## TODO khi có thêm thông tin

- Cập nhật thông tin liên hệ (số điện thoại, email, địa chỉ) trong section Footer
- Kết nối form báo giá với email/CRM (hiện tại chỉ `console.log`). Gợi ý: Formspree, Resend, hoặc Vercel Functions
- Thêm Google Analytics / Vercel Analytics nếu cần đo lường
- Bổ sung trang chi tiết từng dòng sản phẩm khi danh mục mở rộng
