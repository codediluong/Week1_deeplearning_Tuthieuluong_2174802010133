# Week1_deeplearning_Tuthieuluong_2174802010133

# Bai 7:
1. Công nghệ sử dụng

Python 3

Pandas: thư viện xử lý và phân tích dữ liệu dạng bảng

CSV: định dạng lưu trữ dữ liệu đầu vào (100 học sinh)

2. Cách hoạt động

Đọc dữ liệu từ file dulieuxettuyendaihoc.csv vào DataFrame.

Xác định các cột điểm tương ứng cho từng năm học:

Lớp 10: T1, L1, H1, S1, V1, X1, D1, N1

Lớp 11: T2, L2, H2, S2, V2, X2, D2, N2

Lớp 12: T6, L6, H6, S6, V6, X6, D6, N6

Tính tổng điểm 8 môn cho mỗi học sinh.

Áp dụng công thức:

TBM=10T+L+H+S+V+X+D+N

# Bai 8:
1. Công nghệ sử dụng

Python

Pandas: xử lý dữ liệu dạng bảng (CSV), tính toán và tạo biến mới

NumPy (hỗ trợ): gán điều kiện xếp loại học lực

2. Cách hoạt động

Đọc dữ liệu của 100 học sinh từ file CSV bằng Pandas

Tính TBM1, TBM2, TBM3 lần lượt cho các năm lớp 10, 11, 12 bằng cách:

Cộng điểm trung bình 8 môn mỗi năm

Chuẩn hoá theo công thức đề bài (chia cho 10)

Dựa trên các TBM, tạo biến XL1, XL2, XL3 để xếp loại học lực:

Y, TB, K, G, XS theo các khoảng điểm đã cho

Toàn bộ xử lý được thực hiện tự động, theo từng học sinh (theo hàng dữ liệu)

# Bai 9:
1. Công nghệ sử dụng

Python

Pandas: xử lý và phân tích dữ liệu dạng bảng (DataFrame)

NumPy: hỗ trợ xử lý điều kiện và chuẩn hoá dữ liệu

CSV file: lưu trữ dữ liệu điểm của 100 học sinh

2. Cách hoạt động

Đọc dữ liệu từ file CSV bằng Pandas

Tính TBM1, TBM2, TBM3 cho các năm lớp 10, 11, 12 bằng cách cộng điểm các môn theo từng học sinh (sum(axis=1)) và chia theo công thức đề bài

Dựa vào TBM, phân loại học lực từng năm thành XL1, XL2, XL3 (Y, TB, K, G, XS) bằng các khoảng giá trị xác định

Áp dụng Min–Max Normalization để chuyển điểm trung bình từ thang 10 sang thang 4, tạo các biến US_TBM1, US_TBM2, US_TBM3

# Bai 10:
1. Công nghệ sử dụng

Python

Pandas: xử lý và tính toán dữ liệu dạng bảng

NumPy: xử lý điều kiện logic và phân loại kết quả

2. Cách hoạt động

Đọc dữ liệu học sinh từ file CSV

Tính điểm trung bình môn (TBM1, TBM2, TBM3) cho các năm lớp 10, 11, 12

Xếp loại học lực (XL1, XL2, XL3) dựa trên thang điểm quy định

Chuyển điểm TBM từ thang 10 sang thang 4 (US_TBM) bằng Min–Max Normalization

Xét tuyển đại học (KQXT) theo từng khối thi (A, A1, B, khối khác) dựa trên điểm DH1, DH2, DH3



	​


