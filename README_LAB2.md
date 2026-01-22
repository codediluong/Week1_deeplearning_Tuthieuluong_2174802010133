# README – PHẦN 2: TRÌNH BÀY DỮ LIỆU

## 1. Mục tiêu

Phần này nhằm **mô tả và trình bày dữ liệu** của bộ dữ liệu xét tuyển đại học thông qua:

* Bảng tần số, tần suất
* Thống kê mô tả
* Biểu đồ trực quan
  Qua đó giúp hiểu rõ **đặc điểm nhân khẩu học** và **kết quả học tập/thi cử** của học sinh.

---

## 2. Dữ liệu sử dụng

* File: `processed_dulieuxettuyendaihoc.csv`
* Số quan sát: 100 học sinh
* Các biến chính:

  * GT: Giới tính
  * DT: Dân tộc
  * KV: Khu vực
  * KT: Khối thi
  * DH1, DH2, DH3: Điểm thi đại học
  * US_TBM1, US_TBM2, US_TBM3: Điểm trung bình quy đổi thang 4

---

## 3. Nội dung thực hiện

### 3.1. Trình bày biến GT

* Lập bảng tần số và tần suất
* Vẽ:

  * Biểu đồ tần số (cột)
  * Biểu đồ tần suất (tròn)
* Nhận xét cơ cấu giới tính trong dữ liệu

### 3.2. Trình bày các biến US_TBM1, US_TBM2, US_TBM3

* Thống kê mô tả (count, mean, min, max, std…)
* So sánh xu hướng kết quả học tập giữa các năm lớp 10, 11, 12

### 3.3. Trình bày biến DT với học sinh nam

* Lọc dữ liệu theo GT = Nam
* Lập bảng tần số và tần suất cho biến DT
* Nhận xét phân bố dân tộc trong nhóm học sinh nam

### 3.4. Trình bày biến KV với điều kiện

* Học sinh nam
* Dân tộc Kinh
* DH1 ≥ 5.0, DH2 ≥ 4.0, DH3 ≥ 4.0
* Lập bảng tần số và tần suất cho biến KV
* Nhận xét phân bố khu vực của nhóm đạt điều kiện

### 3.5. Trình bày DH1, DH2, DH3 (≥ 5.0) thuộc khu vực 2NT

* Lọc dữ liệu theo KV = 2NT và điểm đạt ngưỡng
* Thống kê mô tả các biến DH1, DH2, DH3
* Đánh giá sơ bộ chất lượng thí sinh khu vực 2NT

---

## 4. Công cụ sử dụng

* Ngôn ngữ: Python
* Thư viện:

  * pandas
  * matplotlib


# README – PHẦN 3: PHÂN TÍCH & THỐNG KÊ DỮ LIỆU

## 1. Mục tiêu

Phần 3 tập trung vào **phân tích thống kê mô tả và tổng hợp dữ liệu** nhằm:

* So sánh điểm thi đại học theo nhiều nhóm
* Đánh giá sự khác biệt giữa các khối thi, khu vực và dân tộc
* Làm rõ phân bố và mức độ phân tán của điểm thi DH1

---

## 2. Dữ liệu sử dụng

* File: `processed_dulieuxettuyendaihoc.csv`
* Các biến chính:

  * DH1: Điểm thi đại học môn 1
  * KT: Khối thi
  * KV: Khu vực
  * DT: Dân tộc

---

## 3. Nội dung thực hiện

### 3.1. Pivot-table DH1 theo KT và KV

* Thống kê các chỉ số:

  * count, sum, mean, median
  * min, max, std
  * Q1 (25%), Q2 (50%), Q3 (75%)
* Mục đích:

  * So sánh điểm DH1 giữa các khối thi trong từng khu vực
  * Đánh giá mức độ phân tán và chênh lệch điểm

### 3.2. Pivot-table DH1 theo KT, KV và DT

* Mở rộng phân tích bằng cách bổ sung biến DT
* Thống kê cùng các chỉ số như trên
* Mục đích:

  * Phân tích sâu hơn sự khác biệt điểm thi theo dân tộc
  * Quan sát ảnh hưởng kết hợp của khối thi, khu vực và dân tộc

---

## 4. Phương pháp phân tích

* Sử dụng **pivot-table** trong Pandas
* Áp dụng thống kê mô tả:

  * Trung bình, trung vị để đánh giá xu hướng
  * Độ lệch chuẩn và các tứ phân vị để đánh giá độ phân tán

---

## 5. Công cụ sử dụng

* Ngôn ngữ: Python
* Thư viện:

  * pandas
  * numpy

# README – PHẦN 4: XÉT TUYỂN & ĐÁNH GIÁ KẾT QUẢ

## 1. Mục tiêu

Phần 4 nhằm **xây dựng và phân tích kết quả xét tuyển đại học** của học sinh dựa trên:

* Khối thi (KT)
* Điểm thi đại học (DH1, DH2, DH3)

Qua đó xác định **trạng thái đậu/rớt** và đánh giá sơ bộ kết quả xét tuyển theo từng nhóm.

---

## 2. Dữ liệu sử dụng

* File: `processed_dulieuxettuyendaihoc.csv`
* Các biến chính:

  * KT: Khối thi
  * DH1, DH2, DH3: Điểm thi đại học
  * KQXT: Kết quả xét tuyển (1 = Đậu, 0 = Rớt)

---

## 3. Nội dung thực hiện

### 3.1. Xây dựng biến KQXT

* Áp dụng quy tắc xét tuyển theo từng khối:

  * Khối A, A1: môn 1 nhân hệ số 2
  * Khối B: môn 2 nhân hệ số 2
  * Khối khác: trung bình cộng 3 môn
* Ngưỡng xét tuyển: điểm ≥ 5.0
* Kết quả:

  * Đậu: 1
  * Rớt: 0

### 3.2. Thống kê kết quả xét tuyển

* Thống kê số lượng và tỷ lệ đậu/rớt
* So sánh kết quả xét tuyển giữa các khối thi

### 3.3. Phân tích theo nhóm (nếu mở rộng)

* So sánh KQXT theo:

  * Giới tính (GT)
  * Khu vực (KV)
  * Khối thi (KT)
* Đánh giá nhóm thí sinh có tỷ lệ đậu cao/thấp

---

## 4. Phương pháp

* Phân loại dựa trên **luật (rule-based classification)**
* Sử dụng các phép toán logic và thống kê mô tả trong Pandas

---

## 5. Công cụ sử dụng

* Ngôn ngữ: Python
* Thư viện:

  * pandas
  * numpy


