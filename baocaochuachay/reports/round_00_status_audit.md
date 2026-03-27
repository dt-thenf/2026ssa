# ROUND 00 — KIỂM TRA TOÀN DIỆN TRẠNG THÁI DỰ ÁN

**Ngày:** 27/03/2026  
**Vòng:** 0 — Khảo sát trạng thái, không thay đổi source code

---

## A. MỤC TIÊU CỦA VÒNG

Khảo sát toàn diện trạng thái workspace `baocaochuachay/` để xác định:
1. Trạng thái hiện tại của từng file `.tex` (đã viết hay còn trống / kế thừa template cũ)
2. Trạng thái `references.bib` (đã merge hay chưa)
3. Trạng thái `Figure/` (tên file, kích thước)
4. Rủi ro biên dịch hiện tại
5. Xác định vòng tiếp theo cần làm gì

---

## B. FILE ĐÃ ĐỌC / VÙNG NỘI DUNG ĐÃ KHAI THÁC

| File | Kích thước | Trạng thái |
|---|---|---|
| `main.tex` | 302 dòng, 11.762 bytes | ĐÃ HOÀN CHỈNH |
| `Chapters/abstract.tex` | 11 dòng, 4.250 bytes | ĐÃ VIẾT CHO RFAR |
| `Chapters/literature_review.tex` | 119 dòng, 17.003 bytes | ĐÃ VIẾT CHO RFAR |
| `Chapters/materials_and_methods.tex` | 341 dòng, 23.165 bytes | ĐÃ VIẾT CHO RFAR |
| `Chapters/results_and_discussion.tex` | 287 dòng, 20.631 bytes | ĐÃ VIẾT CHO RFAR |
| `Chapters/conclusion.tex` | 27 dòng, 4.799 bytes | ĐÃ VIẾT CHO RFAR |
| `Chapters/abbreviations.tex` | 99 dòng, 6.528 bytes | ĐÃ CẬP NHẬT CHO RFAR (51 mục) |
| `references.bib` | 623 dòng, 21.810 bytes | ĐÃ MERGE (56 entries, IEEE style) |
| `references_sensors.bib` | 52.623 bytes | File dự phòng từ jsen.bbl |
| `00_status_scan.md` | Giai đoạn 1 | HOÀN THÀNH |
| `01_outline_mapping.md` | Giai đoạn 2 | HOÀN THÀNH |
| `main.pdf` | 33,37 MB | ĐÃ BIÊN DỊCH THÀNH CÔNG |
| `baocaotiendo.md` (nguồn) | 85 dòng | ĐÃ ĐỌC |

### Các file Chapter cũ (từ template gốc — KHÔNG sử dụng trong main.tex hiện tại):

| File | Ghi chú |
|---|---|
| `method_har.tex` (45KB) | Nội dung cũ từ đề tài template |
| `method_positioning.tex` (19KB) | Nội dung cũ |
| `method_altitude.tex` (3KB) | Nội dung cũ |
| `method_orientation.tex` (3.8KB) | Nội dung cũ |
| `proposed_system.tex` (4.5KB) | Nội dung cũ |
| `result_har.tex` (27KB) | Nội dung cũ |
| `result_positioning.tex` (21KB) | Nội dung cũ |
| `mathematical_symbols.tex` (28B) | Gần trống |

---

## C. NỘI DUNG RÚT TRÍCH ĐƯỢC

### C.1 Trạng thái nội dung các chương

| Chương | Trang ước tính | So với đề cương 01 | Nhận xét |
|---|---|---|---|
| TÓM TẮT (`abstract.tex`) | ~1.5 trang | Đề cương: 2–3 trang | **CẦN MỞ RỘNG** — hiện chỉ 11 dòng, chưa đủ chi tiết bối cảnh và kết luận |
| CH1 (`literature_review.tex`) | ~7–8 trang | Đề cương: 18–22 trang | **THIẾU ĐÁNG KỂ** — cần bổ sung thêm 10–14 trang nữa |
| CH2 (`materials_and_methods.tex`) | ~14–16 trang | Đề cương: 20–25 trang | **THIẾU VỪA** — cần bổ sung 4–9 trang |
| CH3 (`results_and_discussion.tex`) | ~12–14 trang | Đề cương: 15–18 trang | **GẦN ĐỦ** nhưng cần bổ sung 1–4 trang |
| KẾT LUẬN (`conclusion.tex`) | ~2 trang | Đề cương: 3–4 trang | **THIẾU NHẸ** — cần thêm ~1 trang |
| DANH MỤC TỪ VIẾT TẮT | ~2 trang | OK | ĐẠT |
| TÀI LIỆU THAM KHẢO | ~4–5 trang | Đề cương: 5–8 trang | ĐẠT (56 entries) |
| **TỔNG ƯỚC TÍNH** | **~45–50 trang** | **Mục tiêu: 60–80** | **THIẾU 15–30 TRANG** |

### C.2 Trạng thái Figure/

| File | Kích thước | Tên OK? | Có sử dụng? |
|---|---|---|---|
| `FirefighterSystemfull.png` | 2.73 MB | ✅ | ✅ CH2 |
| `pipeline.png` | 442 KB | ✅ | ✅ CH2 |
| `find_parameter.png` | 571 KB | ✅ ĐÃ ĐỔI TÊN | ✅ CH2 |
| `RFmatrix.png` | 313 KB | ✅ | ✅ CH3 |
| `Suyluan.png` | 670 KB | ✅ | ✅ CH2 |
| `accurracyonwindow.png` | 146 KB | ✅ | ✅ CH3 |
| `ml_on_mcu.PNG` | 158 KB | ✅ | ⚠️ CHƯA dùng trong .tex |
| `demo_realtime.png` | **20.39 MB** | ✅ ĐÃ ĐỔI TÊN | ✅ CH3, **CẦN NÉN** |
| `graph_linh_cuu_hoa.png` | 3.00 MB | ✅ ĐÃ ĐỔI TÊN | ⚠️ CHƯA dùng trong .tex |
| `nhan_dang_hanh_dong.png` | 6.70 MB | ✅ ĐÃ ĐỔI TÊN | ⚠️ CHƯA dùng trong .tex |
| `tinh_hinh_chay_no.pdf` | 122 KB | ✅ | ✅ CH1 |
| `loai_hinh_xay_ra_chay.pdf` | 307 KB | ✅ | ⚠️ CHƯA dùng |
| `nguyen_nhan_chan_thuong.pdf` | 145 KB | ✅ | ✅ CH1 |

**Hình ảnh ĐÃ dùng trong .tex:** 9/12 hình theo đề cương  
**Hình ảnh CHƯA dùng:** 3 (`ml_on_mcu.PNG`, `graph_linh_cuu_hoa.png`, `nhan_dang_hanh_dong.png`, `loai_hinh_xay_ra_chay.pdf`)

### C.3 Trạng thái `references.bib`

- **56 entries**, đã merge từ jsen.bbl + template
- Phân nhóm rõ ràng: Lính cứu hỏa (12), HAR wearable (10), DL-HAR (8), TinyML (7), Dataset (6), Feature/tối ưu (5), So sánh (8)
- Theo đề cương cần ≥45 → **ĐẠT**
- Không còn comment `=== SURVEY ===` lỗi → đã sửa

### C.4 Rủi ro biên dịch hiện tại

| # | Rủi ro | Trạng thái |
|---|---|---|
| R1 | `demo_realtime.png` 20 MB | ⚠️ CHƯA NÉN — có thể gây lỗi khi biên dịch |
| R2 | Tên file có khoảng trắng | ✅ ĐÃ SỬA (find_parameter, demo_realtime, graph_linh_cuu_hoa, nhan_dang_hanh_dong) |
| R3 | Unicode/vntex | ⚠️ CẦN KIỂM TRA — log cũ từng có lỗi |
| R4 | `dsfont` package | ✅ Đã khai báo trong main.tex |
| R5 | `notoccite` package | ✅ Đã khai báo |
| R6 | `main.pdf` 33.37 MB | ⚠️ Quá lớn — chủ yếu do demo_realtime.png |

---

## D. ĐỀ XUẤT THAY ĐỔI VÀO BÁO CÁO

**KHÔNG thay đổi gì trong vòng 0.** Đây là vòng khảo sát thuần túy.

### Danh sách công việc cần thực hiện theo thứ tự ưu tiên:

| TT | Nhiệm vụ | File ảnh hưởng | Trang bổ sung ước tính | Ưu tiên |
|---|---|---|---|---|
| 1 | **Nén `demo_realtime.png`** xuống < 3 MB | Figure/ | 0 | CRITICAL |
| 2 | **Mở rộng CH1 (literature_review.tex)** — bổ sung 10–14 trang | literature_review.tex | 10–14 | CAO NHẤT |
| 3 | **Mở rộng CH2 (materials_and_methods.tex)** — bổ sung 4–9 trang | materials_and_methods.tex | 4–9 | CAO |
| 4 | **Mở rộng CH3 (results_and_discussion.tex)** — bổ sung 1–4 trang | results_and_discussion.tex | 1–4 | TRUNG BÌNH |
| 5 | **Mở rộng TÓM TẮT (abstract.tex)** — bổ sung 0.5–1.5 trang | abstract.tex | 0.5–1.5 | TRUNG BÌNH |
| 6 | **Mở rộng KẾT LUẬN (conclusion.tex)** — bổ sung 1 trang | conclusion.tex | 1 | TRUNG BÌNH |
| 7 | **Thêm hình chưa sử dụng** vào các chương | literature_review.tex, materials_and_methods.tex | +1 | THẤP |
| 8 | **Biên dịch cuối — kiểm tra lỗi** | main.tex, tất cả | 0 | SAU CÙNG |

### Đề xuất vòng tiếp theo (Vòng 1):

**Nén `demo_realtime.png`** — giải quyết rủi ro nghiêm trọng nhất trước khi mở rộng nội dung.

---

## E. RỦI RO / ĐIỂM CẦN NGƯỜI DÙNG REVIEW

1. **Ước tính số trang hiện tại (~45–50) cách xa mục tiêu (60–80).** Cần xác nhận liệu người dùng muốn ưu tiên mở rộng chương nào trước.

2. **`demo_realtime.png` (20 MB)** — Có đồng ý nén bằng công cụ tự động hay người dùng muốn cung cấp bản nén thủ công?

3. **3 hình ảnh chưa dùng** (`ml_on_mcu.PNG`, `graph_linh_cuu_hoa.png`, `nhan_dang_hanh_dong.png`, `loai_hinh_xay_ra_chay.pdf`) — Người dùng muốn bổ sung vào chương nào?

4. **Các file chapter cũ** (method_har.tex, proposed_system.tex, v.v.) — Có nên xóa khỏi thư mục Chapters/ để tránh nhầm lẫn?

5. **Chương 1 thiếu nhiều nhất** (~10–14 trang cần bổ sung). Liệu người dùng có thêm nguồn tham khảo mới hay sử dụng hoàn toàn từ jsen.tex và Ref Docs hiện có?

---

*Vòng 0 hoàn thành — Không thay đổi source code.*
