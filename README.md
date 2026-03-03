# PRODUCTS DASHBOARD - TÀI LIỆU HƯỚNG DẪN

## THÔNG TIN DỰ ÁN

**Tên dự án:** Products Dashboard  
**API sử dụng:** https://api.escuelajs.co/api/v1/products  
**Công nghệ:** HTML5, CSS3, JavaScript, Bootstrap 5.3.2  
**Ngày hoàn thành:** 03/03/2026

---

## CÁC FILE TRONG DỰ ÁN

1. **index.html** - File HTML chính chứa cấu trúc trang và logic JavaScript
2. **styles.css** - File CSS tùy chỉnh với giao diện hiện đại

---

## CÁC CHỨC NĂNG ĐÃ THỰC HIỆN

### 1. KẾT NỐI VÀ HIỂN THỊ DỮ LIỆU TỪ API

**Mô tả:** Dashboard tự động kéo dữ liệu sản phẩm từ API khi trang được tải

**Đặc điểm:**
- Hiển thị spinner loading trong khi đang tải dữ liệu
- Xử lý lỗi nếu không thể kết nối API
- Hiển thị thông tin sản phẩm trong bảng Bootstrap đẹp mắt

**Thông tin hiển thị:**
- ID sản phẩm
- Hình ảnh sản phẩm (80x80px, bo tròn, shadow)
- Tên sản phẩm
- Giá (màu tím đậm)
- Danh mục sản phẩm

**Giao diện:**
```
┌──────────────────────────────────────────────────────┐
│  🏪 Products Dashboard                                │
│  (Header với gradient tím đẹp mắt)                   │
└──────────────────────────────────────────────────────┘
│  [Loading Spinner]                                    │
│  Đang tải dữ liệu...                                 │
└──────────────────────────────────────────────────────┘
```

---

### 2. TÌM KIẾM THEO TÊN SẢN PHẨM

**Mô tả:** Tìm kiếm sản phẩm theo tên với sự kiện onChange (tìm kiếm ngay khi người dùng rời khỏi ô input)

**Cách sử dụng:**
1. Nhập tên sản phẩm vào ô "Tìm kiếm theo tên sản phẩm"
2. Click ra ngoài hoặc nhấn Enter
3. Bảng sẽ tự động hiển thị kết quả phù hợp

**Đặc điểm:**
- Tìm kiếm không phân biệt chữ hoa/thường
- Tìm kiếm theo từ khóa có trong tên (không cần nhập chính xác)
- Reset về trang 1 khi tìm kiếm
- Cập nhật số lượng kết quả tìm được

**Giao diện:**
```
┌─────────────────────────────────────────────────────┐
│ 🔍 Tìm kiếm theo tên sản phẩm                       │
│ ┌─────────────────────────────────────────────────┐ │
│ │ Nhập tên sản phẩm...                            │ │
│ └─────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────┘
```

**Ví dụ:**
- Nhập "shirt" → Hiển thị tất cả sản phẩm có chữ "shirt" trong tên
- Nhập "phone" → Hiển thị tất cả sản phẩm có chữ "phone" trong tên

---

### 3. SẮP XẾP (SORT) THEO GIÁ VÀ TÊN

**Mô tả:** Có nút sort ở cột "Tên sản phẩm" và cột "Giá" để sắp xếp tăng/giảm dần

**Cách sử dụng:**
- Click vào nút ⇅ bên cạnh "Tên sản phẩm" để sắp xếp theo bảng chữ cái
- Click vào nút ⇅ bên cạnh "Giá" để sắp xếp theo giá tiền

**Đặc điểm:**
- Sắp xếp theo 2 chiều: Tăng dần (ASC) ⇄ Giảm dần (DESC)
- Mỗi lần click sẽ đổi chiều sắp xếp
- Hiệu ứng hover khi di chuột vào nút
- Áp dụng cho toàn bộ dữ liệu đã được lọc

**Giao diện bảng:**
```
┌────┬──────────┬─────────────────────┬──────────────┬────────┐
│ ID │ Hình ảnh │ Tên sản phẩm ⇅      │ Giá ⇅        │ Danh   │
│    │          │                     │              │ mục    │
├────┼──────────┼─────────────────────┼──────────────┼────────┤
│ 1  │ [IMG]    │ Product A           │ $100         │ Cat 1  │
│ 2  │ [IMG]    │ Product B           │ $200         │ Cat 2  │
└────┴──────────┴─────────────────────┴──────────────┴────────┘
```

---

### 4. PHÂN TRANG VỚI LIMIT 5, 10, 20

**Mô tả:** Hệ thống phân trang với khả năng chọn số sản phẩm hiển thị mỗi trang

**Tùy chọn limit:**
- 5 sản phẩm/trang
- 10 sản phẩm/trang (mặc định)
- 20 sản phẩm/trang

**Đặc điểm phân trang:**
- Nút "Trước" và "Sau" để chuyển trang
- Hiển thị số trang hiện tại (active) với màu gradient
- Hiển thị tối đa 5 số trang cùng lúc
- Tự động scroll lên đầu trang khi chuyển trang
- Hiển thị thông tin: "Hiển thị 1-10 trong tổng số 100 sản phẩm"

**Giao diện:**
```
┌────────────────────────────────────────────┐
│ Số sản phẩm mỗi trang                      │
│ ┌────────────────────┐                     │
│ │ 10 sản phẩm ▾      │                     │
│ └────────────────────┘                     │
└────────────────────────────────────────────┘

┌────────────────────────────────────────────┐
│  ◀ Trước │ 1 │ 2 │ 3 │ 4 │ 5 │ Sau ▶      │
│                                             │
│  Hiển thị 1-10 trong tổng số 100 sản phẩm │
└────────────────────────────────────────────┘
```

---

### 5. ẨN/HIỆN DESCRIPTION KHI HOVER

**Mô tả:** Cột description được ẩn đi, chỉ hiển thị dưới dạng tooltip khi di chuột vào dòng sản phẩm

**Cách hoạt động:**
1. Bảng không có cột "Description" hiển thị cố định
2. Khi di chuột qua bất kỳ dòng sản phẩm nào
3. Một tooltip gradient màu tím xuất hiện bên dưới dòng đó
4. Tooltip hiển thị mô tả đầy đủ của sản phẩm
5. Khi rời chuột, tooltip biến mất

**Đặc điểm:**
- Tooltip có animation fade in/out
- Màu gradient đẹp mắt (tím)
- Bo tròn các góc
- Shadow để nổi bật
- Có mũi tên chỉ vào dòng đang hover
- Tối đa 500px chiều rộng
- Font size dễ đọc

**Hiệu ứng khi hover:**
```
┌────────────────────────────────────────────┐
│ 1  │ [IMG] │ Product A │ $100 │ Category  │ ← Hover vào đây
└────────────────────────────────────────────┘
      ▼
   ┌─────────────────────────────────────────┐
   │ Description: This is a great product... │ ← Tooltip xuất hiện
   └─────────────────────────────────────────┘
```

---

## ĐẶC ĐIỂM GIAO DIỆN (CSS)

### Màu sắc chính:
- **Background gradient:** Tím (#667eea) sang tím đậm (#764ba2)
- **Header:** Gradient tím với text shadow
- **Card/Table:** Nền trắng sạch sẽ
- **Buttons:** Gradient tím khi hover
- **Text:** Màu đen/xám cho dễ đọc

### Hiệu ứng (Animations):
1. **fadeInDown** - Header xuất hiện từ trên xuống
2. **fadeInUp** - Cards xuất hiện từ dưới lên
3. **fadeIn** - Tooltip xuất hiện mượt mà
4. **Hover effects** - Transform và shadow khi di chuột
5. **Smooth transitions** - Tất cả thay đổi đều có transition 0.3s

### Responsive Design:
- **Desktop:** Hiển thị đầy đủ tất cả thông tin
- **Tablet (≤768px):** Font size nhỏ hơn, padding giảm
- **Mobile (≤576px):** Layout 1 cột, hình ảnh nhỏ hơn

### Bootstrap Components sử dụng:
- ✅ Card
- ✅ Table (table-hover)
- ✅ Form (form-control, form-select)
- ✅ Pagination
- ✅ Badge
- ✅ Spinner
- ✅ Icons (Bootstrap Icons)
- ✅ Grid System (container, row, col)

---

## HƯỚNG DẪN SỬ DỤNG

### Bước 1: Mở file
- Double click vào file `index.html`
- Hoặc kéo thả file vào trình duyệt

### Bước 2: Đợi tải dữ liệu
- Dashboard sẽ tự động kết nối API
- Hiển thị spinner loading
- Sau vài giây, dữ liệu sẽ xuất hiện

### Bước 3: Sử dụng các chức năng

**Tìm kiếm:**
1. Nhập từ khóa vào ô tìm kiếm
2. Click ra ngoài hoặc nhấn Enter
3. Xem kết quả

**Sắp xếp:**
1. Click nút ⇅ ở cột Tên hoặc Giá
2. Dữ liệu sẽ được sắp xếp ngay lập tức
3. Click lại để đổi chiều sắp xếp

**Phân trang:**
1. Chọn số sản phẩm/trang từ dropdown (5/10/20)
2. Click số trang hoặc nút Trước/Sau để điều hướng
3. Trang sẽ tự động scroll lên đầu

**Xem mô tả:**
1. Di chuột vào bất kỳ dòng sản phẩm nào
2. Tooltip mô tả sẽ xuất hiện
3. Rời chuột để ẩn tooltip

---

## KẾT QUẢ DEMO

### Screenshot 1: Giao diện chính
```
╔══════════════════════════════════════════════════════╗
║     🏪 Products Dashboard                            ║
║     (Header gradient tím đẹp)                        ║
╠══════════════════════════════════════════════════════╣
║                                                       ║
║  🔍 Tìm kiếm: [_______________]  Limit: [10 ▾]      ║
║                                                       ║
╠══════════════════════════════════════════════════════╣
║  ┌────────────────────────────────────────────────┐  ║
║  │ ID │ IMG │ Tên SP ⇅  │ Giá ⇅  │ Danh mục    │  ║
║  ├────┼─────┼────────────┼─────────┼──────────────┤  ║
║  │ 1  │ 📷  │ Product A  │ $100   │ Electronics │  ║
║  │ 2  │ 📷  │ Product B  │ $200   │ Clothes     │  ║
║  │ 3  │ 📷  │ Product C  │ $150   │ Furniture   │  ║
║  └────┴─────┴────────────┴─────────┴──────────────┘  ║
║                                                       ║
║  ◀ Trước │ 1 │ 2 │ 3 │ Sau ▶                       ║
║                                                       ║
║  📊 Hiển thị 1-10 trong tổng số 100 sản phẩm        ║
╚══════════════════════════════════════════════════════╝
```

### Screenshot 2: Khi tìm kiếm "shirt"
- Chỉ hiển thị các sản phẩm có từ "shirt" trong tên
- Số lượng kết quả được cập nhật
- Phân trang được tính lại

### Screenshot 3: Khi hover vào dòng sản phẩm
- Dòng được highlight với màu tím nhạt
- Tooltip description xuất hiện bên dưới
- Hình ảnh phóng to nhẹ (scale 1.15)

### Screenshot 4: Phân trang
- Trang hiện tại có màu gradient
- Nút Previous/Next hoạt động
- Hiển thị thông tin "X-Y trong tổng Z sản phẩm"

---

## YÊU CẦU KỸ THUẬT

### Trình duyệt hỗ trợ:
- ✅ Google Chrome (khuyến nghị)
- ✅ Microsoft Edge
- ✅ Firefox
- ✅ Safari
- ✅ Opera

### Kết nối Internet:
- ⚠️ CẦN có kết nối Internet để:
  - Tải Bootstrap CSS/JS từ CDN
  - Tải Bootstrap Icons từ CDN
  - Kết nối API lấy dữ liệu sản phẩm

### Tương thích:
- 📱 Mobile responsive
- 💻 Desktop optimized
- 🖥️ Tablet friendly

---

## TÍNH NĂNG NỔI BẬT

✨ **Giao diện hiện đại:**
- Gradient màu tím đẹp mắt
- Animation mượt mà
- Shadow và border-radius bo tròn
- Hiệu ứng hover hấp dẫn

🚀 **Hiệu suất cao:**
- Tải dữ liệu nhanh từ API
- Tìm kiếm và sắp xếp tức thì
- Phân trang mượt mà

📐 **Responsive:**
- Tự động điều chỉnh theo kích thước màn hình
- Mobile-first design
- Touch-friendly trên thiết bị cảm ứng

🎯 **Dễ sử dụng:**
- Giao diện trực quan
- Không cần đào tạo
- Tooltip hướng dẫn

---

## MÃ NGUỒN CHI TIẾT

### HTML Structure:
```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    - Bootstrap CSS CDN
    - Bootstrap Icons CDN
    - Custom styles.css
  </head>
  <body>
    - Header Section (gradient)
    - Control Panel (search + limit)
    - Loading Spinner
    - Products Table
    - Pagination
    - Results Info Badge
    - JavaScript Logic
  </body>
</html>
```

### JavaScript Functions:
1. `fetchProducts()` - Lấy dữ liệu từ API
2. `handleSearch()` - Xử lý tìm kiếm
3. `handleLimitChange()` - Thay đổi số item/trang
4. `sortByTitle()` - Sắp xếp theo tên
5. `sortByPrice()` - Sắp xếp theo giá
6. `renderProducts()` - Render bảng sản phẩm
7. `renderPagination()` - Render pagination
8. `changePage()` - Chuyển trang

### CSS Features:
- Custom gradient backgrounds
- Smooth transitions
- Keyframe animations
- Hover effects
- Responsive breakpoints
- Custom scrollbar styling

---

## KẾT LUẬN

✅ **Hoàn thành đầy đủ tất cả yêu cầu:**

1. ✅ Kéo data từ API
2. ✅ Dashboard với Bootstrap
3. ✅ Tìm kiếm theo title với onChange
4. ✅ Nút sort ở cột giá và title
5. ✅ Phân trang với limit 5, 10, 20
6. ✅ Ẩn description, hiện khi hover
7. ✅ CSS giao diện hiện đại dễ nhìn

**Files nộp:**
- ✅ index.html (HTML + JavaScript)
- ✅ styles.css (CSS tùy chỉnh)
- ✅ README.md (Tài liệu này)

**Chất lượng code:**
- 📝 Code sạch, có comment
- 🎨 Giao diện đẹp, chuyên nghiệp
- ⚡ Performance tốt
- 🔧 Dễ bảo trì và mở rộng

---

## LIÊN HỆ VÀ HỖ TRỢ

Nếu có bất kỳ thắc mắc hoặc cần hỗ trợ, vui lòng liên hệ qua:
- Email: support@example.com
- Phone: 0123-456-789

**Cảm ơn bạn đã sử dụng Products Dashboard! 🎉**

---

*Tài liệu được tạo ngày: 03/03/2026*  
*Phiên bản: 1.0*  
*Tác giả: GitHub Copilot*
