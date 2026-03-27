# Bộ prompt và luật cho Antigravity - báo cáo tiến độ RFAR

Bộ này được soạn để bạn dùng với agent Antigravity nhằm tạo một bản **báo cáo tiến độ** có độ dài kiểu chuyên khảo (60-80 trang) nhưng vẫn bám đúng **form LaTeX của `main.tex`/`main.pdf`** và đúng **nội dung bắt buộc trong `baocaotiendo.md`**.

## Điểm cần hiểu đúng trước khi chạy

Có **mâu thuẫn nguồn yêu cầu**:

1. `baocaotiendo.md` là mẫu **báo cáo tiến độ ngắn** (về bản chất chỉ vài trang).
2. `main.tex`/`main.pdf` là mẫu **báo cáo tổng kết/chuyên khảo dài** có bìa, mục lục, danh mục hình, danh mục bảng, từ viết tắt, tóm tắt, 3 chương, kết luận và tài liệu tham khảo.

Vì bạn yêu cầu **60-80 trang**, cách triển khai hợp lý là:

- **giữ nguyên hệ thống trình bày của `main.tex`**;
- **đổi nội dung học thuật theo tinh thần “báo cáo tiến độ”**;
- **không viết như báo cáo tổng kết hoàn tất**;
- chỉ báo cáo những gì **đã có căn cứ trong hai bài báo và tài liệu kèm theo**;
- các mục “công việc tiếp theo”, “hạn chế”, “đề xuất” phải tách riêng và viết rõ.

## Thứ tự dùng prompt

1. `prompt_01_khoi_tao.md`
2. `prompt_02_quet_nguon_va_lap_ban_do.md`
3. `prompt_03_lap_de_cuong_60_80_trang.md`
4. `prompt_04_viet_chuong_1.md`
5. `prompt_05_viet_chuong_2.md`
6. `prompt_06_viet_chuong_3.md`
7. `prompt_07_hoan_thien_frontmatter_refs.md`
8. `prompt_08_ra_soat_pdflatex.md`

## Kết quả mong muốn

- thư mục đích: `baocaochuachay/`
- tệp gốc: `baocaochuachay/main.tex`
- các chương để riêng trong `baocaochuachay/Chapters/`
- hình/bảng trích ra và dùng lại trong `baocaochuachay/Figure/`
- tài liệu tham khảo trong `baocaochuachay/references.bib`
- biên dịch bằng `pdflatex` + `bibtex` + `pdflatex` + `pdflatex`

## Lưu ý vận hành

- Không thay đổi package, lề, font, cỡ chữ, giãn dòng, cách đánh số, cách tổ chức TOC/LoF/LoT nếu không bắt buộc.
- Chỉ thay đổi phần chữ bắt buộc để biến mẫu từ “báo cáo tổng kết” thành “báo cáo tiến độ”, và đổi nội dung đề tài đúng năm học 2025-2026.
- Không bịa số liệu chưa xuất hiện trong bài báo hoặc tài liệu tham khảo phụ trợ.
- Ưu tiên dữ liệu, bảng, hình, công thức, quy trình, và kết quả trong `jsen.tex`, `jsen.pdf`, `RFAR_A_Real-Time_Firefighter_Activity_Recognition_System_Using_Wearable_Accelerometer.pdf`, sau đó mới mở rộng bằng tài liệu trong `Ref Docs/`.
