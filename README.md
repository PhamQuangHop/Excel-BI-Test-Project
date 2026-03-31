# Excel BI Test Project

Dự án này tập trung vào xử lý dữ liệu, xây dựng mô hình phân tích và trực quan hóa báo cáo bằng **Excel, Power Pivot, PivotTable, PivotChart và DAX** nhằm giải quyết 2 bài toán chính:

- Phân tích **Doanh số & Target** các tháng 4, 5, 6
- Phân tích **Tồn kho tháng 7** và dự báo lượng tồn cuối tháng

---

## 1. Giới thiệu dự án

Trong các bài toán Business Intelligence, dữ liệu thực tế thường chưa sẵn sàng để phân tích ngay mà cần trải qua các bước làm sạch, chuẩn hóa, mô hình hóa và tính toán chỉ số nghiệp vụ.

Project này được thực hiện như một bài test BI thực chiến, với mục tiêu:

- Làm sạch và chuẩn hóa dữ liệu từ nhiều nguồn
- Xây dựng data model phục vụ phân tích
- Tạo các chỉ số KPI bằng DAX
- Thiết kế dashboard trực quan để hỗ trợ ra quyết định
- Đưa ra insight và đề xuất chiến lược từ dữ liệu

---

## 2. Mục tiêu dự án

### Bài toán 1: Doanh số & Target
- Chuẩn hóa dữ liệu doanh số và target theo tháng
- Xây dựng mô hình dữ liệu để so sánh doanh số thực tế với chỉ tiêu
- Phân tích mức độ hoàn thành target theo nhân sự quản lý (PIC) và nhóm ngành hàng
- Xây dựng dashboard tương tác hỗ trợ theo dõi hiệu suất

### Bài toán 2: Tồn kho tháng 7
- Làm sạch và tích hợp dữ liệu tồn kho
- Xây dựng chỉ số đo lường tốc độ bán hàng
- Dự báo lượng tồn kho đến cuối tháng
- Xác định sản phẩm/danh mục cần được ưu tiên xử lý

---

## 3. Công cụ sử dụng

- **Microsoft Excel**
- **Power Pivot**
- **PivotTable**
- **PivotChart**
- **DAX**
- **Google Sheets** (nguồn dữ liệu ban đầu)

---

## 4. Quy trình thực hiện

## 4.1 Tiền xử lý dữ liệu

### Dữ liệu Doanh số & Target
- Import dữ liệu từ Google Sheets vào Excel
- Làm sạch và chuẩn hóa các lỗi định dạng cơ bản
- Sử dụng kỹ thuật **Unpivot** để chuyển các cột dữ liệu theo tháng về cấu trúc chuẩn
- Chuẩn hóa bảng Target và bảng Doanh số để sẵn sàng cho việc modeling

### Dữ liệu Tồn kho tháng 7
- Chuẩn hóa text bằng cách:
  - chuyển tên sản phẩm về chữ in hoa
  - loại bỏ khoảng trắng thừa
- Bổ sung cột phân loại để gán đúng danh mục sản phẩm
- Gom nhóm dữ liệu theo:
  - Danh mục
  - Tên sản phẩm
  - Giá bán
- Loại bỏ dữ liệu trùng lặp nhưng vẫn giữ các dòng khác giá như các SKU riêng biệt
- Tạo cột **Flag tồn kho**:
  - `Đã kiểm kê`
  - `Chưa kiểm kê`
- Xử lý missing values:
  - điền `0` cho các cột số lượng bán và nhập

---

## 5. Xây dựng mô hình dữ liệu

Đối với bài toán Doanh số & Target, mô hình dữ liệu được xây dựng theo hướng phân tách:

### Dimension Tables
- `Dim_Danh_muc`
- `Dim_Thoi_gian`

### Fact Tables
- Bảng Doanh số
- Bảng Target đã chuẩn hóa

Các bảng được kết nối bằng **Power Pivot Relationships** để phục vụ việc tính toán KPI và phân tích đa chiều.

---

## 6. Tính toán nghiệp vụ

Dự án sử dụng **DAX** để xây dựng các chỉ số phục vụ phân tích.

### Một số nhóm chỉ số chính
- Doanh số thực tế
- Target
- Tỷ lệ hoàn thành target
- Chênh lệch giữa thực tế và mục tiêu
- KPI theo PIC
- KPI theo nhóm ngành hàng
- Tốc độ bán hàng trung bình
- Dự báo tồn kho cuối tháng

Các measure được thiết kế để hỗ trợ dashboard tương tác và phân tích theo nhiều góc nhìn khác nhau.

---

## 7. Trực quan hóa dữ liệu

Dự án sử dụng:

- **PivotTable** để tổng hợp dữ liệu
- **PivotChart** để trực quan hóa xu hướng và hiệu suất
- **Slicer** để tăng khả năng tương tác dashboard

### Dashboard : Sales & Target Dashboard
Dashboard thể hiện:
- doanh số thực tế theo tháng
- target theo tháng
- tỷ lệ hoàn thành target
- hiệu suất theo PIC
- hiệu suất theo ngành hàng

### Charts: Inventory Dashboard
Thể hiện:
- tồn kho theo danh mục
- tồn kho theo sản phẩm
- tốc độ bán hàng
- dự báo tồn cuối tháng
- sản phẩm/danh mục cần ưu tiên xử lý

---

## 8. Phân tích và insight

### Với bài toán Doanh số & Target
Từ dashboard có thể:
- đánh giá mức độ hoàn thành mục tiêu theo từng PIC
- xác định nhóm ngành hàng đạt hoặc chưa đạt target
- so sánh hiệu suất giữa các tháng
- nhận diện khu vực cần cải thiện hiệu quả bán hàng

### Với bài toán Tồn kho
Từ phân tích tồn kho có thể:
- xác định sản phẩm bán chậm
- phát hiện danh mục có nguy cơ tồn dư cao
- theo dõi những dòng hàng cần xử lý sớm
- hỗ trợ ra quyết định nhập hàng, đẩy bán hoặc tối ưu phân bổ tồn

---

## 9. Giá trị mang lại từ dự án

- Chuẩn hóa dữ liệu phục vụ phân tích BI
- Tăng khả năng theo dõi KPI kinh doanh bằng Excel
- Hỗ trợ nhà quản lý đánh giá hiệu suất nhanh hơn
- Đưa ra góc nhìn dữ liệu về doanh số và tồn kho
- Tạo nền tảng cho việc mở rộng sang Power BI hoặc hệ thống BI chuyên sâu hơn

---

## 10. Kỹ năng thể hiện trong dự án

Dự án này thể hiện các kỹ năng:

- Data Cleaning
- Data Transformation
- Data Modeling
- Excel BI
- Power Pivot
- DAX
- Dashboard Design
- Business Analysis
- Inventory Analysis
- Sales Performance Analysis

---

