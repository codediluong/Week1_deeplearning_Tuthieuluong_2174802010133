# README — Lab 4 (Titanic) — Data Cleansing, Feature Engineering & EDA

## 1) Công nghệ sử dụng

* **Ngôn ngữ:** Python 3
* **Môi trường chạy:** Jupyter Notebook / Google Colab (`.ipynb`)
* **Thư viện chính:**

  * `pandas`: đọc dữ liệu, xử lý dữ liệu dạng bảng, tạo biến mới
  * `numpy`: hỗ trợ tính toán/điều kiện (một số bước)
  * `matplotlib`: trực quan hóa biểu đồ
  * `seaborn`: trực quan hóa (boxplot, heatmap, barplot, countplot)
* **Dataset:** `titanic_disaster.csv`

> Ghi chú cài đặt: Notebook có dùng `%pip install seaborn` để cài seaborn trong môi trường Notebook/Colab.

## 2) Cách hoạt động (Workflow trong notebook)

### PHẦN 1 — Data Cleansing & Feature Engineering

Notebook thực hiện các bước chính sau:

1. **Load dữ liệu Titanic**

   * Đọc file `titanic_disaster.csv` bằng `pandas.read_csv()`
   * Hiển thị một số dòng đầu để kiểm tra dữ liệu

2. **Rút gọn cột giới tính `Sex`**

   * Thay `male → M`, `female → F` để dữ liệu gọn và dễ phân tích hơn

3. **Xử lý thiếu dữ liệu `Age`**

   * Trực quan phân phối tuổi theo `Pclass` bằng **Boxplot**
   * Quyết định thay thế `Age` bị thiếu bằng **giá trị trung bình theo từng nhóm `Pclass`**
   * Trực quan lại tình trạng thiếu dữ liệu `Age` bằng **Heatmap** để xác nhận đã xử lý

4. **Tạo biến nhóm tuổi `Agegroup`**

   * Quy tắc:

     * `Age <= 12` → `Kid`
     * `12 < Age <= 18` → `Teen`
     * `18 < Age <= 60` → `Adult`
     * `Age > 60` → `Older`

5. **Tạo biến danh xưng xã hội `namePrefix`**

   * Tách các danh xưng **Mr, Mrs, Miss, Master** từ tên hành khách
   * Các danh xưng khác (nếu có) được gom nhóm để dễ phân tích

6. **Tạo biến quy mô gia đình `familySize`**

   * Công thức: `familySize = 1 + SibSp + Parch`

7. **Tạo biến `Alone` (đi một mình hay không)**

   * Dựa trên `familySize` để xác định hành khách đi cá nhân hay theo nhóm

8. **Tạo biến loại cabin `typeCabin`**

   * Lấy **chữ cái đầu tiên** của `Cabin` làm loại cabin
   * Cabin thiếu dữ liệu → gán `Unknown`

---

### PHẦN 2 — EDA (Khai thác thông tin hữu ích)

Notebook trực quan hóa mối liên hệ giữa **tỷ lệ sống sót (`Survived`)** và các đặc trưng quan trọng:

* (12) Sống sót theo **giới tính**
* (13) Sống sót theo **hạng vé (Pclass)**
* (14) Sống sót theo **giới tính + Pclass**
* (15) Sống sót theo **nhóm tuổi (Agegroup)**
* (16) Sống sót theo **giá vé (Fare)** (boxplot)
* (17) Số lượng sống/thiệt mạng theo **Pclass** và theo **cảng lên tàu (Embarked)** (countplot)

---

## 3) Kết quả (Output đạt được)

### 3.1 Kết quả xử lý dữ liệu

* Dữ liệu được chuẩn hóa và bổ sung feature phục vụ phân tích:

  * `Sex` được rút gọn thành `M/F`
  * `Age` thiếu được điền (impute) theo **mean từng `Pclass`**
  * Tạo các biến mới: `Agegroup`, `namePrefix`, `familySize`, `Alone`, `typeCabin`
  * Heatmap sau xử lý giúp kiểm tra trực quan trạng thái thiếu dữ liệu của `Age`

### 3.2 Kết quả EDA (nhận định chính rút ra)

* **Giới tính** ảnh hưởng mạnh đến sống sót: nhóm nữ thường có tỷ lệ sống sót cao hơn.
* **Hạng vé (Pclass)** liên quan rõ rệt đến sống sót: hạng cao có xu hướng sống sót cao hơn.
* **Giá vé (Fare)** thường phản ánh điều kiện/hạng vé, và có sự khác biệt giữa nhóm sống sót và không sống sót.
* **Nhóm tuổi (Agegroup)** cho thấy khác biệt nhất định về tỷ lệ sống sót giữa trẻ em/người lớn/người cao tuổi.
* **Cảng lên tàu (Embarked)** có thể liên quan đến cơ cấu hành khách và tỷ lệ sống sót.
