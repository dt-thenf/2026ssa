+:----------------------------:+:-------------------------------------:+
| **TRƯỜNG ĐẠI HỌC PHENIKAA**  | **CỘNG HÒA XÃ HỘI CHỦ NGHĨA VIỆT      |
|                              | NAM**                                 |
| **KHOA ĐIỆN -- ĐIỆN TỬ**     |                                       |
|                              | **Độc lập -- Tự do -- Hạnh phúc**     |
+------------------------------+---------------------------------------+
|                              | *Hà Nội, ngày ... tháng ... năm 2026* |
+------------------------------+---------------------------------------+

**BÁO CÁO TIẾN ĐỘ THỰC HIỆN ĐỀ TÀI SINH VIÊN**

**NGHIÊN CỨU KHOA HỌC NĂM HỌC 2025 - 2026**

**Kính gửi:** - **Ban Giám hiệu**

> **- Ban Khoa học Công nghệ**
>
> **- Ban Chủ nhiệm Khoa Điện -- Điện tử**

**I. THÔNG TIN CHUNG**

\- Tên đề tài: Nghiên cứu, thiết kế hệ thống RFAR ứng dụng TinyML trên
thiết bị biên phục vụ công tác phân tích hoạt động lính cứu hỏa theo
thời gian thực trong tình huống khẩn cấp.

\- Chủ nhiệm đề tài: Bùi Việt Hoàn Lớp, Khoa: K15 KTYS, Khoa Điện --
Điện tử

\- Cán bộ hướng dẫn: ThS. Đào Tô Hiệu

**II. TIẾN ĐỘ THỰC HIỆN ĐỀ TÀI**

1\. Các công việc đã hoàn thành:

- Xây dựng cơ sở dữ liệu: Thiết lập bộ dữ liệu riêng biệt mô phỏng các
  hoạt động đặc thù của lính cứu hỏa (bao gồm 11 hoạt động như bò,
  trườn, ngã, leo cầu thang\...) với sự tham gia của 20 tình nguyện
  viên.

- Thiết kế hệ thống phần cứng: Phát triển thiết bị đeo tích hợp cảm biến
  gia tốc 3 trục ADXL345 và vi điều khiển hiệu năng thấp ESP32, đảm bảo
  tính nhỏ gọn (trọng lượng dưới 200g) và khả năng vận hành liên tục
  trong 24 giờ.

- Đề xuất quy trình xử lý dữ liệu mới: Xây dựng đường ống xử lý tín hiệu
  kết hợp kỹ thuật cửa sổ trượt và thuật toán phát hiện chỉ số bất
  thường, giúp nhận diện chính xác các trạng thái chuyển tiếp và hành vi
  ngã.

- Tối ưu hóa mô hình học máy: Lựa chọn và tinh chỉnh thuật toán Random
  Forest để triển khai trực tiếp trên vi điều khiển có tài nguyên hạn
  chế. Mô hình đã được tối ưu hóa để có kích thước dưới 1 MB nhưng vẫn
  duy trì hiệu suất cao.

- Đánh giá và thực nghiệm: Hệ thống đã được kiểm chứng trên bộ dữ liệu
  riêng và ba bộ dữ liệu công cộng (SFDLA, MobiFall, UniMiB-SHAR), đạt
  điểm F1-score 96,2% trong các kịch bản mô phỏng cứu hộ thực tế tại
  Việt Nam.

2\. Các công việc dự kiến thực hiện trong thời gian tới:

- Tối ưu hóa thiết kế công nghiệp: Cải thiện cấu trúc phần cứng từ dạng
  lắp ráp thủ công sang thiết kế tích hợp chuyên nghiệp, nhằm giảm kích
  thước thiết bị và tăng tính thuận tiện khi gắn lên trang phục bảo hộ.

- Nâng cao tính phổ quát của mô hình: Mở rộng thu thập dữ liệu và điều
  chỉnh thuật toán để tăng khả năng thích nghi của hệ thống với nhiều
  nhóm đối tượng có đặc điểm thể chất khác nhau, bao gồm nhân sự nữ.

- Tích hợp hệ thống định vị và cảnh báo: Nghiên cứu tích hợp thêm tính
  năng xác định vị trí trong nhà và cơ chế phát tín hiệu khẩn cấp tự
  động khi phát hiện lính cứu hỏa gặp nạn hoặc bất tỉnh.

- Phát triển mạng lưới giám sát tập trung: Xây dựng giao thức truyền tải
  dữ liệu cho phép trung tâm chỉ huy theo dõi trạng thái hoạt động của
  nhiều nhân sự cùng lúc trong môi trường thực thi nhiệm vụ phức tạp.

**III. KIẾN NGHỊ, ĐỀ XUẤT (nếu có)**

  -----------------------------
  **CHỦ NHIỆM ĐỀ TÀI**
  -----------------------------

  -----------------------------
