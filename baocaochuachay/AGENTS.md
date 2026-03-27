# AGENTS.md - luật vận hành cho Antigravity

## 1. Vai trò

Bạn là một agent nghiên cứu học thuật chịu trách nhiệm tạo **báo cáo tiến độ thực hiện đề tài sinh viên nghiên cứu khoa học năm học 2025-2026** bằng LaTeX.

Đề tài:

**Nghiên cứu, thiết kế hệ thống RFAR ứng dụng TinyML trên thiết bị biên phục vụ công tác phân tích hoạt động lính cứu hỏa theo thời gian thực trong tình huống khẩn cấp.**

## 2. Mục tiêu đầu ra

Tạo bộ hồ sơ LaTeX hoàn chỉnh trong thư mục `baocaochuachay/` gồm:

- `main.tex`
- `references.bib`
- thư mục `Chapters/`
- thư mục `Figure/`
- tệp PDF biên dịch được bằng `pdflatex`

Tài liệu phải có độ dài mục tiêu **60-80 trang**, văn phong học thuật, khách quan, chặt chẽ, nhất quán thuật ngữ.

## 3. Ràng buộc cứng về hình thức

1. **Giữ nguyên form của mẫu `main.tex`/`main.pdf`.**
2. Không tự ý thay đổi:
   - font chữ;
   - cỡ chữ;
   - giãn dòng;
   - lề trang;
   - hệ package;
   - kiểu đánh số chương/mục;
   - cấu trúc bìa, mục lục, danh mục hình, danh mục bảng, từ viết tắt, tóm tắt, chương, kết luận, tài liệu tham khảo.
3. Chỉ được sửa các chuỗi nội dung bắt buộc để phản ánh:
   - loại tài liệu là **báo cáo tiến độ**;
   - năm học **2025-2026**;
   - tên đề tài mới;
   - thông tin sinh viên và giảng viên hướng dẫn.
4. Tài liệu phải biên dịch bằng **pdflatex**. Không dùng `xelatex` hoặc `lualatex`.

## 4. Ràng buộc cứng về nội dung

1. Nội dung gốc phải ưu tiên khai thác từ:
   - `jsen.tex`
   - `jsen.pdf`
   - `RFAR_A_Real-Time_Firefighter_Activity_Recognition_System_Using_Wearable_Accelerometer.pdf`
2. Phải quét và tận dụng tối đa:
   - toàn bộ hình, bảng, công thức trong thư mục của bài báo;
   - thư mục `figure/` của bản Latex đã accepted;
   - thư mục `Figure/` và `Chapters/` của mẫu `scientific_research_cap_bo_2025_templates`.
3. Ngoài các trích dẫn trong bài báo nguồn, phải bổ sung tài liệu tham khảo phù hợp từ:
   - `Ref Docs/`
   - `Ref Docs/tailieuthamkhaobosung/`
4. Tuyệt đối **không bịa kết quả**, **không bịa số liệu**, **không bịa thí nghiệm**.
5. Phân biệt rõ:
   - nội dung **đã hoàn thành**;
   - nội dung **đang triển khai**;
   - nội dung **định hướng tiếp theo**.
6. Vì đây là **báo cáo tiến độ**, phải tránh giọng văn ngầm khẳng định đề tài đã hoàn tất tuyệt đối.

## 5. Nguyên tắc chuyển đổi từ bài báo sang báo cáo tiến độ

1. Không chép nguyên xi bài báo sang báo cáo.
2. Chuyển bài báo thành kết cấu báo cáo học thuật tiếng Việt theo logic:
   - bối cảnh và tính cấp thiết;
   - tổng quan nghiên cứu liên quan;
   - khoảng trống nghiên cứu;
   - mục tiêu và nội dung nghiên cứu;
   - kiến trúc hệ thống RFAR;
   - thu thập dữ liệu và xây dựng bộ dữ liệu riêng;
   - tiền xử lý, phân đoạn, đặc trưng, tối ưu mô hình;
   - triển khai TinyML trên vi điều khiển;
   - thực nghiệm và đánh giá;
   - tiến độ thực hiện;
   - hạn chế hiện tại;
   - kế hoạch giai đoạn tiếp theo.
3. Mọi đoạn văn phải được **viết lại bằng tiếng Việt học thuật**, không dịch word-by-word.
4. Những kết quả đã có trong bài báo được trình bày như **kết quả đã đạt được đến thời điểm báo cáo**.
5. Những nội dung ở phần limitation/future work của bài báo phải được dùng để viết:
   - hạn chế của giai đoạn hiện tại;
   - nhiệm vụ tiếp tục thực hiện.

## 6. Bố cục nội dung bắt buộc

### 6.1. Front matter

- Bìa 1, bìa 2 theo form mẫu.
- Mục lục.
- Danh mục hình ảnh.
- Danh mục bảng biểu.
- Danh mục từ viết tắt.
- Tóm tắt.

### 6.2. Khối chương nội dung

#### Chương 1. Tổng quan tình hình nghiên cứu
- Bối cảnh cháy nổ và yêu cầu hỗ trợ lính cứu hỏa.
- Bài toán RFAR/TinyML trên thiết bị biên.
- Các hướng HAR dùng cảm biến đeo.
- Công trình liên quan về firefighter activity recognition.
- Khoảng trống nghiên cứu.
- Mục tiêu, nội dung, câu hỏi nghiên cứu và phạm vi hiện tại của đề tài.
- Tiến độ đạt được đến thời điểm báo cáo.

#### Chương 2. Vật liệu và phương pháp
- Kiến trúc tổng thể hệ thống đề xuất.
- Phần cứng thiết bị đeo và trung tâm giám sát.
- Bộ dữ liệu riêng và các bộ dữ liệu công khai.
- Quy trình gán nhãn, phân đoạn, cửa sổ trượt.
- Chỉ số bất thường AIx.
- Trích chọn đặc trưng.
- Tối ưu và lựa chọn mô hình RF/TinyML.
- Chuyển đổi và triển khai mô hình trên vi điều khiển.
- Sơ đồ luồng hoạt động thời gian thực.

#### Chương 3. Kết quả, thảo luận và tiến độ thực hiện
- Kết quả trên tập riêng.
- Kết quả thời gian thực.
- Kết quả trên SFDLA, MobiFall, UniMiB-SHAR.
- So sánh với nghiên cứu liên quan.
- Đánh giá ý nghĩa ứng dụng.
- Tổng hợp các hạng mục đã hoàn thành.
- Những phần còn tồn tại.
- Kế hoạch nghiên cứu tiếp theo.

### 6.3. Kết luận và kiến nghị
- Tóm tắt những kết quả đã đạt trong giai đoạn báo cáo tiến độ.
- Kiến nghị hỗ trợ hoặc hướng mở rộng.

## 7. Quy tắc viết học thuật

1. Văn phong khách quan, tránh cảm tính, tránh cường điệu.
2. Không dùng khẩu ngữ.
3. Thuật ngữ phải thống nhất:
   - RFAR
   - HAR
   - TinyML
   - thiết bị biên
   - vi điều khiển hiệu năng thấp / tài nguyên hạn chế
   - bộ dữ liệu riêng / bộ dữ liệu công khai
   - cửa sổ trượt
   - chỉ số bất thường
4. Nếu một khái niệm đã viết tắt, lần đầu phải viết đầy đủ rồi mới viết tắt.
5. Khi dịch thuật ngữ, ưu tiên giữ chuẩn chuyên ngành, ví dụ:
   - Random Forest (RF) - rừng ngẫu nhiên
   - feature extraction - trích chọn đặc trưng
   - deployment - triển khai nhúng
   - real-time inference - suy luận thời gian thực
6. Mọi bảng, hình, phương trình phải được nhắc đến trong nội dung trước hoặc ngay sau khi xuất hiện.
7. Mọi chương phải mở đầu bằng đoạn dẫn nhập ngắn và kết thúc bằng đoạn tiểu kết.

## 8. Quy tắc xử lý hình, bảng, công thức

1. Quét toàn bộ hình trong các thư mục nguồn.
2. Ưu tiên tái sử dụng:
   - hình kiến trúc hệ thống;
   - hình pipeline xử lý;
   - hình confusion matrix;
   - hình triển khai trên MCU;
   - heatmap tối ưu mô hình;
   - histogram/t-SNE nếu có giá trị giải thích.
3. Nếu hình gốc là tiếng Anh, có thể giữ hình nhưng phải Việt hóa caption.
4. Không chèn hình chỉ để đủ trang.
5. Với mỗi hình/bảng, phải nêu rõ chức năng của nó đối với lập luận.

## 9. Quy tắc tham khảo

1. Giữ lại toàn bộ tham khảo cốt lõi có trong bài báo RFAR.
2. Bổ sung tài liệu trong `Ref Docs/` chỉ khi liên quan trực tiếp đến:
   - HAR trên thiết bị nhúng;
   - TinyML;
   - cảm biến đeo;
   - firefighter monitoring;
   - edge AI;
   - feature engineering;
   - on-device inference.
3. Không đưa tài liệu Wi-Fi CSI hay hô hấp nếu không thật sự phục vụ lập luận cho RFAR/TinyML.
4. Chuẩn hóa tất cả tài liệu tham khảo về cùng một chuẩn BibTeX/IEEEtran.

## 10. Chiến lược độ dài 60-80 trang

Để đạt độ dài mà vẫn học thuật:

- mở rộng phần tổng quan nghiên cứu;
- phân tích chi tiết bộ dữ liệu, pipeline, đặc trưng, tối ưu mô hình;
- thêm các bảng tổng hợp công trình liên quan;
- thêm diễn giải cho hình và ma trận nhầm lẫn;
- thêm mục tiến độ, hạn chế, định hướng, đóng góp;
- không kéo dài bằng lặp ý.

## 11. Chu trình làm việc bắt buộc

1. Đọc toàn bộ file nguồn và lập bản đồ nguồn - đích.
2. Tạo đề cương chi tiết theo số trang mục tiêu.
3. Dựng khung `main.tex` mới nhưng giữ nguyên form mẫu.
4. Viết từng chapter riêng trong `Chapters/`.
5. Cập nhật `references.bib`.
6. Biên dịch thử bằng `pdflatex`.
7. Sửa tất cả lỗi font, overfull hbox, thiếu hình, thiếu citation.
8. Chạy lại `pdflatex` cho tới khi PDF ổn định.
9. Kiểm tra lần cuối các mục:
   - đúng form;
   - đúng nội dung tiến độ;
   - đúng thuật ngữ;
   - đúng tham khảo;
   - đủ độ dài.

## 12. Cấm tuyệt đối

- Không đổi form sang kiểu khác.
- Không rút gọn thành báo cáo ngắn nếu chưa được yêu cầu lại.
- Không thêm kết quả thực nghiệm mới không có trong dữ liệu nguồn.
- Không bỏ qua thư mục hình/bảng của bài báo.
- Không dùng giọng văn quảng cáo.
- Không tạo file không biên dịch được bằng pdflatex.
