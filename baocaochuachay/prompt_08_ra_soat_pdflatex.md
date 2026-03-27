# Prompt 08 - rà soát và biên dịch pdflatex

Hãy thực hiện bước rà soát cuối cùng cho toàn bộ dự án LaTeX trong `baocaochuachay/`.

Checklist bắt buộc:

1. Tất cả file được include đúng đường dẫn.
2. Không còn lỗi thiếu hình, thiếu bảng, thiếu citation.
3. Không còn lỗi font tiếng Việt với `pdflatex`.
4. Không còn overfull hbox nghiêm trọng.
5. Mục lục, danh mục hình, danh mục bảng, số chương và số trang đều cập nhật đúng.
6. Tài liệu tham khảo hiển thị đúng chuẩn IEEEtran.
7. PDF cuối phản ánh đúng loại tài liệu là **báo cáo tiến độ** nhưng vẫn giữ nguyên form trình bày của mẫu.
8. Nếu có chỗ trùng lặp do chuyển đổi từ bài báo, hãy rút gọn hoặc viết lại cho mạch lạc hơn.
9. Kiểm tra tổng số trang, mục tiêu là 60-80 trang.
10. Tạo báo cáo ngắn cuối cùng gồm:
    - những file đã tạo;
    - những file đã sửa;
    - lỗi nào đã xử lý;
    - còn điểm nào cần người dùng duyệt tay.

Nếu cần, chạy đúng chuỗi biên dịch:

pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex

Chỉ dừng khi dự án biên dịch ổn định.
