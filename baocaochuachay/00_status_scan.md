# 00_STATUS_SCAN — Giai đoạn 1: Quét nguồn và chuẩn bị workspace

**Đề tài:** Nghiên cứu, thiết kế hệ thống RFAR ứng dụng TinyML trên thiết bị biên phục vụ công tác phân tích hoạt động lính cứu hỏa theo thời gian thực trong tình huống khẩn cấp  
**Ứng viên:** Bùi Việt Hoàn — K15 KTYS, Khoa Điện – Điện tử, ĐH Phenikaa  
**Giảng viên hướng dẫn:** ThS. Đào Tô Hiệu  
**Ngày quét:** 27/03/2026  
**Trạng thái:** GIAI ĐOẠN 1 HOÀN THÀNH — Sẵn sàng chuyển Giai đoạn 2

---

## 1. NGUỒN CHÍNH (Ưu tiên cao nhất)

| File | Loại | Vai trò |
|---|---|---|
| `mau_bao_cao/Accepted_26.07.2025/Sensors-91454-2025_Latex/jsen.tex` | LaTeX bài báo IEEE Sensors (106 KB, 1058 dòng) | NGUỒN NỘI DUNG SO 1 — Toàn bộ kỹ thuật: kiến trúc hệ thống, dataset, pipeline xử lý, RF model, kết quả thực nghiệm (4 dataset) |
| `mau_bao_cao/Accepted_26.07.2025/Sensors-91454-2025_Latex/jsen.bbl` | Bibliography (249 entries) | Danh sách 61 tài liệu tham khảo trực tiếp từ bài báo RFAR |
| `mau_bao_cao/RFAR_A_Real-Time_Firefighter_Activity_Recognition_System_Using_Wearable_Accelerometer.pdf` | PDF bài báo RFAR (3.95 MB) | Bản đầy đủ để xác minh nội dung khi cần |
| `mau_bao_cao/scientific_research_cap_bo_2025_templates/main.tex` | LaTeX template (13 KB, 330 dòng) | TEMPLATE BAT BUOC GIU NGUYEN — class, packages, style, formatting |
| `mau_bao_cao/scientific_research_cap_bo_2025_templates/references.bib` | BibTeX (45 KB, 1104 dòng) | ~56 tài liệu tham khảo của đề tài gốc — dùng làm nền, bổ sung bằng jsen.bbl |

---

## 2. NGUỒN PHỤ (Bổ sung tổng quan, thảo luận, tài liệu tham khảo)

| File | Loại | Ghi chú sử dụng |
|---|---|---|
| `mau_bao_cao/baocaotiendo.md` | Markdown — Form báo cáo tiến độ | Thông tin chung: tên đề tài, nhóm nghiên cứu, tiến độ đã hoàn thành, công việc dự kiến |
| `mau_bao_cao/Ref Docs/Efficient Real-Time Devices Based on Accelerometer Using Machine Learning.pdf` | PDF tham khảo HAR | Bổ sung tổng quan TinyML/HAR trên MCU |
| `mau_bao_cao/Ref Docs/Human_activity_sleep.pdf` | PDF tham khảo HAR | Bổ sung context về HAR monitoring |
| `mau_bao_cao/Ref Docs/conference_icmlant_2025.pdf` | PDF conference proceedings | Tham khảo thêm về HAR cho lính cứu hỏa |
| `mau_bao_cao/Ref Docs/dao2023design.pdf` | PDF journal paper | Liên quan đến thiết kế hệ thống đeo (tác giả Đào Tô Hiệu) |
| `mau_bao_cao/Ref Docs/JBHI-01060-2025_Proof_hi.pdf` | PDF proof IEEE JBHI | Bổ sung kết quả nghiên cứu mở rộng |
| `mau_bao_cao/AIO_Step-by-Step_Random Forest.pdf` | PDF tutorial RF | Bổ sung giải thích thuật toán Random Forest |
| `mau_bao_cao/AIO_Step-by-Step_XGBoost.pdf` | PDF tutorial XGBoost | Bổ sung phân tích so sánh model |

---

## 3. FIGURE / TABLE TÁI SỬ DỤNG

### 3.1 Hình từ bài báo RFAR (IEEE Sensors) — Nguồn số 1
Vị trí: `baocaochuachay/Figure/` (đã copy)

| File | Nội dung | Chuong su dung |
|---|---|---|
| `FirefighterSystemfull.png` | Kiến trúc tổng thể hệ thống RFAR + màn hình chỉ huy | Chuong 2: He thong de xuat |
| `pipeline.png` | Pipeline xử lý dữ liệu mới (sliding window + AIx detection) | Chuong 2: Phuong phap xu ly |
| `find parameter.png` | Biểu đồ tối ưu F1 vs. model size (6 models) | Chuong 3: Ket qua toi uu model |
| `RFmatrix.png` | Ma trận nhầm lẫn (confusion matrix) trên 5 dataset | Chuong 3: Danh gia ket qua |
| `nhan dang hanh dong.png` | Minh họa nhận dạng hoạt động thực tế | Chuong 2 hoac 3 |
| `demo realtime.png` (20 MB) | Ảnh thực nghiệm trên tình nguyện viên tại cơ sở PCCC | Chuong 3: Thuc nghiem |
| `ml_on_mcu.PNG` | Sơ đồ triển khai ML trên MCU (TinyML) | Chuong 2: Trien khai |
| `accurracyonwindow.png` | Ảnh hưởng kích thước cửa sổ đến độ chính xác | Chuong 2: Thiet lap thuc nghiem |
| `graph linh cuu hoa.png` | Biểu đồ thống kê hoạt động lính cứu hỏa | Chuong 1: Tong quan |
| `Suyluan.png` | Sơ đồ suy luận | Chuong 2 hoac 3 |

### 3.2 Hình từ template gốc — Tái sử dụng có chọn lọc

| File | Quyet dinh |
|---|---|
| `tinh_hinh_chay_no.pdf` | DUNG — bổ sung Chương 1 (thống kê cháy nổ VN) |
| `loai_hinh_xay_ra_chay.pdf` | DUNG — bổ sung Chương 1 |
| `nguyen_nhan_chan_thuong.pdf` | DUNG — bổ sung Chương 1 (chấn thương lính cứu hỏa) |
| `graphical_abstract.pdf` | KHONG DUNG — thay bằng FirefighterSystemfull.png |
| `overview_method.pdf` | KHONG DUNG — thay bằng pipeline.png |
| `confusion_matrices.pdf` | KHONG DUNG — thay bằng RFmatrix.png |

### 3.3 Bảng biểu từ bài báo RFAR — Tái sử dụng trực tiếp

| Ten bang trong jsen.tex | Noi dung | Chuong |
|---|---|---|
| `Table_firemanActivityRecognition` | Overview HAR studies (wearable devices, 2016–2024) | Chuong 1: Tong quan |
| `table_hardware` | Cấu hình phần cứng và nền tảng thực nghiệm | Chuong 2: He thong de xuat |
| `table_activity_description` | Mô tả 11 hoạt động lính cứu hỏa + số mẫu | Chuong 2: Dataset |
| `table_feature` | 30 đặc trưng được lựa chọn (time-domain) | Chuong 2: Trich xuat dac trung |
| `table_model_config` | Cấu hình tham số tối ưu 6 model ML | Chuong 3: Ket qua so sanh |
| `table_RF_private_realtime` | Metrics RF trên dataset riêng + thực nghiệm RT | Chuong 3: Danh gia |
| `table:evaluation_public` | Hiệu suất RF trên 3 dataset công khai | Chuong 3: Danh gia tong quat |

---

## 4. RỦI RO BIÊN DỊCH

| # | Rui ro | Muc do | Bien phap xu ly |
|---|---|---|---|
| R1 | File anh `demo realtime.png` (20 MB) — qua lon | Cao | Nen xuong <3 MB truoc khi dung |
| R2 | Ten file PNG chua khoang trang (`find parameter.png`, v.v.) | Cao | Doi ten thanh `find_parameter.png`, v.v. |
| R3 | Package `vntex` voi UTF-8 — ky tu Unicode khong chuan | Trung binh | Kiem tra encoding UTF-8 toan bo file .tex |
| R4 | `RFmatrix.png` — `width=1.05\textwidth` co the tran le | Trung binh | Dat trong `figure*` hoac dung `\resizebox` |
| R5 | Comment `=== SURVEY ===` trong references.bib — khong chuan BibTeX | Thap | Xoa truoc khi bien dich |
| R6 | `dsfont` package — co the khong co san tren moi ban LaTeX | Thap | Neu loi, thay bang `amssymb` |
| R7 | `notoccite` package — co the khong co san | Thap | Neu loi, xoa khoi preamble |

---

## 5. DE XUAT CAU TRUC 60-80 TRANG

| Phan | Noi dung | Trang |
|---|---|---|
| Trang bia 1 | BO GIAO DUC VA DAO TAO (tikz border) | 1 |
| Trang bia 2 | TRUONG DH PHENIKAA + Ten sinh vien/GVHD | 1 |
| Muc luc | Tu dong | 2-3 |
| DMHA | Danh muc hinh anh (12-14 hinh) | 1 |
| DMBP | Danh muc bang bieu (8-10 bang) | 1 |
| DMTV | Danh muc tu viet tat RFAR (~30 tu) | 2 |
| TOM TAT | Bot canh / Muc tieu / Phuong phap / Ket qua / Ket luan | 2-3 |
| CHUONG 1: TONG QUAN | Thuc trang; Nghien cuu QT; Nghien cuu trong nuoc; HAR nguoi cao tuoi; HAR linh cuu hoa; TinyML tren MCU; Muc tieu de tai | 18-22 |
| CHUONG 2: VAT LIEU VA PHUONG PHAP | He thong RFAR; Dataset; Xu ly du lieu; Pipeline AIx; Gan nhan; Trich xuat dac trung; Toi uu RF; Trien khai TinyML ESP32 | 20-25 |
| CHUONG 3: KET QUA VA THAO LUAN | Phuong phap danh gia; Ket qua dataset rieng; Thuc nghiem RT; Ket qua 3 dataset cong khai; So sanh; Han che; Huong PT | 15-18 |
| KET LUAN VA KIEN NGHI | Tom tat dong gop; Danh gia tien do; Kien nghi giai doan tiep theo | 3-4 |
| TAI LIEU THAM KHAO | IEEE style (>=45 tai lieu) | 5-8 |
| Tong cong du kien | | 65-78 trang |

---

## 6. CAY THU MUC WORKSPACE

```
baocaochuachay/
├── main.tex                       <- KHUNG CHINH (da tao, dua template)
├── references.bib                <- BibTeX goc (copy tu template)
├── references_sensors.bib        <- BibTeX tu bai bao Sensors (bo sung)
├── 00_status_scan.md             <- FILE NAY
├── Chapters/
│   ├── abstract.tex              <- TOM TAT (viet lai cho RFAR)
│   ├── abbreviations.tex         <- Tu viet tat (can cap nhat RFAR terms)
│   ├── literature_review.tex     <- CHUONG 1 (viet lai - nguon: jsen.tex Sec I-II)
│   ├── materials_and_methods.tex <- CHUONG 2 (viet lai - nguon: jsen.tex Sec III)
│   ├── results_and_discussion.tex<- CHUONG 3 (viet lai - nguon: jsen.tex Sec IV)
│   ├── conclusion.tex            <- KET LUAN (viet lai - nguon: jsen.tex Sec V)
│   └── [cac file phu tu template - giu de tham khao]
└── Figure/
    ├── FirefighterSystemfull.png  <- Chuong 2 [DUNG]
    ├── pipeline.png               <- Chuong 2 [DUNG]
    ├── find parameter.png         <- Chuong 3 [DOI TEN!]
    ├── RFmatrix.png               <- Chuong 3 [DUNG]
    ├── nhan dang hanh dong.png    <- Chuong 2/3 [DOI TEN!]
    ├── demo realtime.png          <- Chuong 3 [DOI TEN! + NEN!]
    ├── ml_on_mcu.PNG              <- Chuong 2 [DUNG]
    ├── accurracyonwindow.png      <- Chuong 2 [DUNG]
    ├── graph linh cuu hoa.png     <- Chuong 1 [DOI TEN!]
    ├── Suyluan.png                <- Chuong 2/3 [DUNG]
    ├── tinh_hinh_chay_no.pdf      <- Chuong 1 [DUNG]
    ├── loai_hinh_xay_ra_chay.pdf  <- Chuong 1 [DUNG]
    └── nguyen_nhan_chan_thuong.pdf <- Chuong 1 [DUNG]
```

---

## 7. VIEC CAN LAM NGAY (Giai doan 2)

1. [URGENT] Doi ten cac file anh co khoang trang trong Figure/
2. [URGENT] Nen demo_realtime.png xuong <3MB
3. Xoa comment `=== SURVEY ===` trong references.bib  
4. Merge references.bib + jsen.bbl thanh file bib thong nhat
5. Cap nhat abbreviations.tex cho RFAR
6. Viet abstract.tex (TOM TAT)
7. Viet literature_review.tex (CHUONG 1)
8. Viet materials_and_methods.tex (CHUONG 2)
9. Viet results_and_discussion.tex (CHUONG 3)
10. Viet conclusion.tex (KET LUAN)
11. Bien dich thu va sua loi

---

## 8. SO LIEU XAC NHAN TU BAI BAO

- F1-score tren dataset rieng: 96.1% (F1_mi), 97.0% (F1_ma)
- F1-score thuc nghiem thoi gian thuc: 96.2%
- F1-score tren SFDLA: 96.6%
- F1-score tren MobiFall: 96.6%
- F1-score tren UniMiB-SHAR: 78.2%
- Kich thuoc model RF: 0.921709 MB (< 1 MB)
- Tham so toi uu: n_estimators=17, max_depth=14
- So tinh nguyen vien: 20 (nam, 22-35 tuoi, 60-80 kg, 1.6-1.8 m)
- Thoi gian thu thap du lieu: 371 phut
- So mau toan bo: >100 MB
- So bieu cat: 11 hoat dong (WA, ST, LY, SI, JO, WS, CR, SL, FA, DS, US)
- Thoi gian suy luan: ~3.95 microseconds/prediction

*File nay duoc tao tu dong trong Giai doan 1 — San sang de chuyen sang Giai doan 2.*
