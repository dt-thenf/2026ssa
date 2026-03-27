# 01_OUTLINE_MAPPING — Giai đoạn 2: Đề cương chi tiết 60–80 trang

**Ngày lập:** 27/03/2026  
**Trạng thái:** GIAI ĐOẠN 2 — Sẵn sàng chuyển Giai đoạn 3 (viết LaTeX)

---

## A. BẢN ĐỒ ÁNH XẠ: Ý TRONG BÀI BÁO → MỤC TRONG BÁO CÁO TIẾN ĐỘ

| Nguồn (jsen.tex / baocaotiendo.md) | Mục trong báo cáo tiến độ |
|---|---|
| jsen.tex §Abstract — bối cảnh, mục tiêu, kết quả tóm tắt | TÓM TẮT: Bối cảnh, Mục tiêu, Phương pháp, Kết quả, Kết luận |
| jsen.tex §I Introduction — thực trạng cháy nổ, thương vong lính cứu hỏa | CH1 §1.1 Thực trạng và tính cấp thiết |
| jsen.tex §I — hạn chế thông tin liên lạc truyền thống, nhu cầu HAR | CH1 §1.2 Tính cấp thiết của hệ thống giám sát |
| jsen.tex §II.A Related works — HAR cho người cao tuổi, wearable sensor | CH1 §1.3 Tổng quan nghiên cứu HAR |
| jsen.tex §II.B — FAR systems, nghiên cứu về lính cứu hỏa | CH1 §1.4 Tổng quan HAR cho lính cứu hỏa |
| jsen.tex §I contributions (4 bullet points) | CH1 §1.5 Đóng góp chính của đề tài |
| baocaotiendo.md §I Thông tin chung | TÓM TẮT + Trang bìa |
| jsen.tex §III.A System architecture | CH2 §2.1 Kiến trúc hệ thống RFAR |
| jsen.tex §III.B Dataset — private + 3 public | CH2 §2.2 Cơ sở dữ liệu |
| jsen.tex §III.C Data processing — downsampling, sliding window | CH2 §2.3 Quy trình xử lý dữ liệu |
| jsen.tex §III.C New pipeline for fall detection (AIx) | CH2 §2.4 Pipeline phát hiện ngã mới |
| jsen.tex §III labelling | CH2 §2.5 Gán nhãn dữ liệu |
| jsen.tex §III.D Feature extraction (30 features, 13 types) | CH2 §2.6 Trích xuất đặc trưng |
| jsen.tex §III.E Optimization of RF on microcontrollers | CH2 §2.7 Tối ưu hóa mô hình trên vi điều khiển |
| jsen.tex §IV.A Evaluation method (ACC, SEN, SPE, PRE, F1) | CH3 §3.1 Phương pháp đánh giá |
| jsen.tex §IV.B Results — private dataset | CH3 §3.2 Kết quả trên tập dữ liệu riêng |
| jsen.tex §IV.B — on-device deployment + real-time | CH3 §3.3 Thực nghiệm thời gian thực |
| jsen.tex §IV.B — SFDLA, MobiFall, UniMiB results | CH3 §3.4 Kết quả trên tập dữ liệu công khai |
| jsen.tex §V Discussion — comparison with other models | CH3 §3.5 So sánh với các nghiên cứu liên quan |
| jsen.tex §V.B — window size & sampling freq analysis | CH3 §3.6 Phân tích ảnh hưởng tham số |
| jsen.tex §V.C — feature ablation study | CH3 §3.6 (tiếp) Phân tích đặc trưng |
| jsen.tex §V.D Limitation and future work | CH3 §3.7 Hạn chế và hướng phát triển |
| jsen.tex §VI Conclusion | KẾT LUẬN §A Tổng kết kết quả |
| baocaotiendo.md §II.1 Công việc đã hoàn thành | KẾT LUẬN §B Tiến độ thực hiện |
| baocaotiendo.md §II.2 Công việc dự kiến | KẾT LUẬN §C Kế hoạch tiếp theo |
| baocaotiendo.md §III Kiến nghị, đề xuất | KẾT LUẬN §D Kiến nghị |

---

## B. ĐỀ CƯƠNG CHI TIẾT 60–80 TRANG

### TRANG BÌA VÀ FRONT MATTER (5–6 trang, roman numerals)

```
[Trang bìa 1]  BỘ GIÁO DỤC VÀ ĐÀO TẠO — tikz border (1 trang)
[Trang bìa 2]  TRƯỜNG ĐẠI HỌC PHENIKAA — thông tin sinh viên/GVHD (1 trang)
[i–ii]         Mục lục (2 trang)
[iii]          Danh mục hình ảnh (1 trang)
[iv]           Danh mục bảng biểu (1 trang)
[v–vi]         Danh mục từ viết tắt (2 trang)
```

---

### TÓM TẮT (trang 1–3, ~2–3 trang)

**Nguồn:** jsen.tex §Abstract + baocaotiendo.md §I

| Mục | Nội dung | Ước trang |
|---|---|---|
| Bối cảnh | Thực trạng cháy nổ, thách thức an toàn lính cứu hỏa, nhu cầu giám sát hoạt động thời gian thực | 0.5 |
| Mục tiêu | Xây dựng hệ thống RFAR nhận dạng 11 hoạt động lính cứu hỏa trên thiết bị đeo có tài nguyên hạn chế | 0.3 |
| Phương pháp | Thiết bị đeo gia tốc kế ADXL345 + ESP32; pipeline xử lý mới tích hợp AIx; Tối ưu RF model <1MB | 0.5 |
| Kết quả | F1=96.2% thực nghiệm; 96.6% SFDLA/MobiFall; 78.2% UniMiB; Model 0.92MB; latency ~9.6ms | 0.5 |
| Kết luận | Tiến độ thực hiện, tiềm năng ứng dụng, hướng mở rộng | 0.3 |

---

### CHƯƠNG 1: TỔNG QUAN VÀ TÍNH CẤP THIẾT (trang 4–25, ~18–22 trang)

**Nguồn chính:** jsen.tex §I, §II | **Nguồn phụ:** Ref Docs, tinh_hinh_chay_no.pdf

#### 1.1 Thực trạng cháy nổ và an toàn lính cứu hỏa (~3 trang)
- Tình hình cháy nổ tại Việt Nam và thế giới
  - Số liệu thống kê: NFPA 2023 — 63,175 thương vong; 89 tử vong trong khi thi hành nhiệm vụ
  - 87% thương vong xảy ra khi chữa cháy trong nhà (structural fires)
  - Xu hướng gia tăng số vụ cháy do đô thị hóa và hạ tầng xuống cấp
  - **Figure:** `tinh_hinh_chay_no.pdf` — Tình hình cháy nổ tại Việt Nam
  - **Figure:** `loai_hinh_xay_ra_chay.pdf` — Phân loại loại hình cháy
- Thách thức đặc thù của môi trường chữa cháy
  - Nhiệt độ cực cao, khói độc, không gian hẹp, nguy cơ sập đổ công trình
  - Hạn chế tầm nhìn và thông tin liên lạc trong môi trường khẩn cấp
  - **Figure:** `nguyen_nhan_chan_thuong.pdf` — Nguyên nhân chấn thương lính cứu hỏa

#### 1.2 Tính cấp thiết của hệ thống giám sát hoạt động thời gian thực (~2 trang)
- Hạn chế của phương tiện liên lạc truyền thống (bộ đàm 2 chiều)
  - Chỉ cung cấp thông tin phân mảnh, không giám sát liên tục từng cá nhân
  - Không phát hiện được trạng thái bất tỉnh hoặc bất động của lính cứu hỏa
- Tiềm năng của hệ thống HAR cho lính cứu hỏa
  - Cung cấp dữ liệu khách quan, liên tục về trạng thái hoạt động
  - Hỗ trợ ra quyết định kịp thời cho trung tâm chỉ huy
  - Phát hiện sớm các tình huống nguy hiểm (ngã, bất động)
- Khoảng trống nghiên cứu hiện tại
  - Phần lớn nghiên cứu tập trung phát hiện ngã, ít nghiên cứu nhận dạng toàn diện hoạt động đặc thù lính cứu hỏa
  - Thiếu dataset công khai cho lính cứu hỏa
  - Chưa có giải pháp tối ưu triển khai trên MCU công suất thấp

#### 1.3 Tổng quan nghiên cứu HAR sử dụng cảm biến đeo (~5 trang)
- Phân loại phương pháp HAR: Computer vision vs. Wearable sensor
  - Ưu/nhược điểm của từng phương pháp
  - Lý do chọn cảm biến đeo: nhỏ gọn, chi phí thấp, không phụ thuộc môi trường
- Các vị trí đặt cảm biến: thắt lưng, cổ tay, đùi, v.v.
- Machine Learning truyền thống trong HAR
  - DT (Thu et al., 2022): 99% acc trên ESP8266
  - RF (Hong et al., 2023): 99.2% acc, 4 hoạt động
  - GBDT, KNN, SVM (Lu et al., 2020): 93% acc
  - Wang et al. (2018): Hierarchical structure, RF+SVM, 90.4% acc
- Deep Learning trong HAR
  - CNN, LSTM, ResNet — ưu điểm học đặc trưng tự động
  - Nhược điểm: tài nguyên tính toán cao, không phù hợp MCU hạn chế
  - CNN-DCT (Xu et al., 2023), HARMamba, CLS-CNN-ResNest (Qin et al., 2024)
- **Bảng:** `Table_firemanActivityRecognition` — Overview HAR studies (wearable, 2016–2024)
- Kết luận: ML truyền thống vẫn thực tế hơn với thiết bị nhúng có tài nguyên hạn chế

#### 1.4 Tổng quan HAR cho lính cứu hỏa (~4 trang)
- FAR systems: yêu cầu đặc thù về môi trường khắc nghiệt
- Geng et al. (2016): RF signal + SVM, 7 hoạt động, 88.7% acc
  - Hạn chế: cửa sổ 10s, chậm phản hồi
- Pham et al. (Thanhfire2019): Phát hiện ngã + CO monitoring, 100% acc riêng; 97.9% public
- Dang et al. (2022): Accelerometer + CO, phát hiện ngã 93%, nhạy 96.5%
- Chai et al. (2021): LSTM 3 lớp, 5 vị trí cảm biến, 94.1% acc
- Chai et al. (2024/CHAI_FIRE2024): Sensor fusion, EMG + IMU, 8 hoạt động, Hybrid ML
- Phân tích khoảng trống:
  - Thiếu nhận dạng toàn diện (bò, trườn, đi khom, v.v.)
  - Chưa xử lý chuyển tiếp giữa các hoạt động
  - Chưa tối ưu cho MCU công suất thấp

#### 1.5 TinyML và triển khai trên vi điều khiển (~3 trang)
- Khái niệm TinyML: ML inference trên thiết bị biên công suất thấp
- Thách thức: RAM/Flash hạn chế (~1MB), xử lý thời gian thực
- Các giải pháp: model compression, feature optimization, quantization
- RF trên MCU: micromlgen library, header file deployment
  - Vi et al. (2024): RF trên MCU hiệu suất thấp
  - Dao et al. (2022): HAR trên MCU hiệu suất vừa
- Tại sao chọn ESP32 + ADXL345: tài nguyên đủ, chi phí thấp, cộng đồng rộng

#### 1.6 Mục tiêu, phạm vi và đóng góp của đề tài (~2 trang)
- Mục tiêu chung: Hệ thống RFAR hoạt động thời gian thực trên thiết bị biên
- Đóng góp 1: Dataset riêng 11 hoạt động lính cứu hỏa (20 tình nguyện viên, 371 phút)
- Đóng góp 2: Pipeline xử lý tín hiệu mới tích hợp sliding window + AIx detection
- Đóng góp 3: Hệ thống RFAR với RF model tối ưu (<1MB) trên MCU trễ ~9.6ms
- Đóng góp 4: Thiết bị đeo <200g, hoạt động 24h liên tục, F1>96% trong thực nghiệm
- Phạm vi: giai đoạn tiến độ — đã hoàn thành phần nghiên cứu cốt lõi, đang mở rộng

---

### CHƯƠNG 2: NỘI DUNG NGHIÊN CỨU ĐÃ THỰC HIỆN (trang 26–50, ~20–25 trang)

**Nguồn chính:** jsen.tex §III (System, Dataset, Data processing, Feature, Optimization)

#### 2.1 Kiến trúc hệ thống RFAR đề xuất (~3 trang)
- Tổng quan hệ thống: thiết bị đeo + trung tâm chỉ huy
  - **Figure:** `FirefighterSystemfull.png` — Kiến trúc tổng thể hệ thống
- Thiết bị đeo (Wearable device)
  - ADXL345: cảm biến gia tốc 3 trục
  - ESP32: 520KB RAM, 448KB ROM, 4MB Flash
  - Module truyền thông: 433MHz, 8000m, 2.4Kbps
  - Pin Li-ion 2000mAh — hoạt động >24h
  - Kích thước nhỏ gọn, trọng lượng <200g
  - Đặt tại vùng thắt lưng — ổn định tín hiệu
- Thiết bị trung tâm (Central device)
  - ESP32 nhận dữ liệu từ nhiều thiết bị đeo
  - Hiển thị trạng thái hoạt động từng lính cứu hỏa theo thời gian thực
- **Bảng:** `table_hardware` — Cấu hình phần cứng chi tiết
- Quy trình hoạt động 3 giai đoạn: Thu thập → Trích xuất đặc trưng → Nhận dạng

#### 2.2 Xây dựng cơ sở dữ liệu (~4 trang)
##### 2.2.1 Dataset riêng (private dataset)
- Đối tượng: 20 tình nguyện viên nam, 22–35 tuổi, 1.6–1.8m, 60–80kg
- Đơn vị: ĐH Phenikaa + ĐH Phòng cháy Chữa cháy Việt Nam
- Tần số lấy mẫu: 100Hz, 3 trục gia tốc (đơn vị g)
- Thời gian thu thập: 371 phút (~6.2 giờ), dataset >100MB
- 11 hoạt động đặc thù lính cứu hỏa:
  - WA (đi bộ), ST (đứng), LY (nằm), SI (ngồi), JO (chạy bộ)
  - WS (đi khom), CR (bò tay-gối), SL (trườn sát đất)
  - FA (ngã), DS (xuống thang), US (lên thang)
- **Bảng:** `table_activity_description` — Mô tả + số mẫu từng hoạt động
- Phân chia tập huấn luyện/kiểm tra: 60%/40%

##### 2.2.2 Tập dữ liệu công khai
- MobiFall: 4 loại ngã + 9 hoạt động sinh hoạt
- SFDLA: Bộ dataset ngã và hoạt động tại Bilkent University
- UniMiB-SHAR: 17 hoạt động từ smartphone đặt trong túi
- Lý do chọn 3 dataset này: chứa các hoạt động tương đồng, đa dạng đối tượng, phổ biến trong cộng đồng nghiên cứu

#### 2.3 Quy trình xử lý dữ liệu (~4 trang)
##### 2.3.1 Giảm tần số lấy mẫu
- Từ 100Hz → 50Hz bằng moving average filter
- Công thức: a_k[n] = (ā_k[2n-1] + ā_k[2n]) / 2
- Lý do: tiết kiệm tài nguyên tính toán, năng lượng; không giảm đáng kể độ chính xác

##### 2.3.2 Phân đoạn tín hiệu — Sliding window
- Cửa sổ thời gian cố định Δt = 3 giây (150 mẫu tại 50Hz)
- Phân tích ảnh hưởng kích thước cửa sổ: 1s giảm ~15%, 6s tốt nhất nhưng trễ cao
- 3s: cân bằng thực tế giữa độ chính xác (~96%) và tốc độ phản hồi
- Phân chia dữ liệu thành N_Δt cửa sổ

##### 2.3.3 Pipeline phát hiện ngã mới (AIx Detection) — [Đóng góp chính]
- **Figure:** `pipeline.png` — Sơ đồ pipeline mới (nổi bật màu xanh đậm)
- Bước 1: Tính chỉ số bất thường AIx
  - Biến đổi tín hiệu s[n] → Δs[n] (độ lệch kết hợp 3 trục khỏi giá trị trung bình)
  - AIx = Δs[n₀] nếu > threshold = 1.8g (theo Thanh et al.)
  - Cửa sổ phát hiện nhỏ ΔW = 0.5s
- Bước 2: Thu thập dữ liệu xung quanh sự kiện bất thường
  - Cửa sổ dữ liệu: [n₀ - 3·Fs, n₀ + 3·Fs] = 6 giây xung quanh điểm ngã
- Bước 3: Phân tích và phân loại
  - Kết hợp đặc trưng signal variation để xác định FA vs. hoạt động khác
- Khác biệt so với phương pháp truyền thống: cửa sổ động thay vì cửa sổ trượt cố định

##### 2.3.4 Gán nhãn dữ liệu
- 11 nhãn tương ứng 11 hoạt động (0–10)
- Quy trình 3 bước: xác định nhãn → phân đoạn tuần tự → gán nhãn cho từng cửa sổ
- Giám sát bởi 2 người quan sát → đảm bảo tính chính xác

#### 2.4 Trích xuất đặc trưng (~3 trang)
- Lý do chọn đặc trưng time-domain: phù hợp MCU, không cần FFT tốn kém
- 16 loại đặc trưng được xem xét ban đầu
- Phương pháp lựa chọn: loại bỏ đặc trưng quan trọng < 0.01 (ngưỡng = 0.5 × σ importance)
- **Figure:** `pipeline.png` (panel d) — Feature importance distribution
- Kết quả: 30 đặc trưng tối ưu từ 13 loại:
  - Energy (x,y), MAD (x,y,z), SMA (x,y,z), Mean (x,y,z), SD (x,y,z)
  - SSI (x,y,z), AAC (x,y,z), Max (x,z), MEAD (x,z), IQR (x,y)
  - Hjorth Complexity (z), Range (x,y,z)
- **Bảng:** `table_feature` — 30 đặc trưng với công thức toán học

#### 2.5 Tối ưu hóa mô hình Random Forest trên vi điều khiển (~4 trang)
- Bài toán tối ưu: F1_mi cao + kích thước model < 1MB
- Hai siêu tham số: n_estimators (1–50) và max_depth (1–50)
- **Algorithm:** `OptimizationRandomForest` — Pseudocode tìm tham số tối ưu
- Kết quả tối ưu RF: n_estimators=17, max_depth=14, size=0.9217MB
- So sánh 6 model: RF, XGB, DT, GBDT, SVM, LBM
  - **Figure:** `find_parameter.png` — F1_mi và kích thước theo tham số của 6 model
  - **Bảng:** `table_model_config` — Cấu hình tối ưu và kết quả tất cả model
- Triển khai trên ESP32:
  - Chuyển đổi: Python `micromlgen.port(clf)` → C header file `random_forest.h`
  - Tích hợp: `#include "random_forest.h"` trong firmware
  - Khởi tạo: `Eloquent::ml::port::RF rf;`
  - Suy luận: `rf.predict(feat_j)`
- Hiệu năng trên phần cứng:
  - Feature extraction: ~8,858 μs (84,507 instruction lines)
  - Inference: ~733–738 μs (140,838 instruction lines)
  - Tổng latency mỗi nhận dạng: ~9.561–9.596ms
  - **Figure:** `Suyluan.png` — Kết quả triển khai inference trên MCU

---

### CHƯƠNG 3: KẾT QUẢ BƯỚC ĐẦU, THẢO LUẬN VÀ ĐỊNH HƯỚNG TIẾP THEO (trang 51–68, ~15–18 trang)

**Nguồn chính:** jsen.tex §IV, §V

#### 3.1 Phương pháp đánh giá (~1.5 trang)
- Các chỉ số: ACC, SEN, SPE, PRE, F1-score micro (F1_mi), F1-score macro (F1_ma)
- Công thức toán học cho từng chỉ số (Eq. 18–27)
- K-fold cross-validation: k=5 trên tập dữ liệu đầy đủ
- Ký hiệu: TP, FP, TN, FN

#### 3.2 Kết quả trên tập dữ liệu riêng (~2 trang)
- **Bảng:** `table_model_config` (trình bày lại, tập trung vào RF)
- RF đạt: acc=99.3%, sen=97.0%, spe=99.6%, pre=97.1%, F1_mi=96.1%, F1_ma=97.0%
- So sánh RF vs. XGB vs. LBM vs. DT vs. SVM vs. GBDT
- **Figure:** `RFmatrix.png` (panel a) — Confusion matrix trên dataset riêng
- Phân tích nhầm lẫn: DS↔US (cùng pattern leo thang), WA↔JO
- **Bảng:** `table_RF_private_realtime` (phần a) — Metrics từng hoạt động

#### 3.3 Thực nghiệm thời gian thực trên thiết bị nhúng (~2.5 trang)
- **Figure:** `demo_realtime.png` — Thực nghiệm tại cơ sở PCCC Việt Nam
- Cài đặt thực nghiệm: 20 tình nguyện viên thực hiện lặp lại các hoạt động
- Step size bình thường: 3s (tiết kiệm năng lượng)
- Step size khi AIx > threshold: 0.5s (tăng tần suất nhận dạng)
- **Figure:** `RFmatrix.png` (panel b) — Confusion matrix thực nghiệm RT
- **Bảng:** `table_RF_private_realtime` (phần b) — Metrics thực nghiệm RT
- Kết quả: acc=99.4%, F1_mi=96.2% — tương đương với dataset offline
- Phân tích: sai lệch <1% so với dataset riêng → mô hình tổng quát tốt

#### 3.4 Kết quả trên 3 tập dữ liệu công khai (~3 trang)
##### 3.4.1 Tập SFDLA
- Xử lý: loại bỏ dữ liệu nữ, loại vị trí không phù hợp, giữ waist sensor
- **Figure:** `RFmatrix.png` (panel c) — Confusion matrix SFDLA
- Kết quả: acc=99.4%, F1_mi=96.6%
- **Bảng:** `table:evaluation_public`

##### 3.4.2 Tập MobiFall
- Xử lý: loại BSC, CSI, CSO; loại dữ liệu nữ
- **Figure:** `RFmatrix.png` (panel d) — Confusion matrix MobiFall
- Kết quả: acc=99.2%, F1_mi=96.6%
- Thách thức: DS↔US confusion do pattern tương tự

##### 3.4.3 Tập UniMiB-SHAR
- 17 hoạt động (AF17): ADL + 8 loại ngã
- Thách thức: smartphone orientation thay đổi → preprocessing alignment
- **Figure:** `RFmatrix.png` (panel e) — Confusion matrix UniMiB
- Kết quả AF17: acc=97.4%, F1_mi=78.2%
- Kết quả AF2 (fall vs. non-fall): acc=100%, F1_mi=100%

#### 3.5 So sánh với các nghiên cứu liên quan (~2.5 trang)
- **Bảng:** `tab:Comparison_UniMiB` — So sánh trên UniMiB-SHAR
  - Proposed (78.2%) vs CNN-DCT (79.7%) vs CNN-TSFDU-LW (78.6%)
  - AF2: Proposed (100%) vs Al-qaness (99.95%) vs Kanjilal (98.86%)
- **Bảng:** `tab:fall_detection_model` — So sánh phát hiện ngã cho lính cứu hỏa
  - Proposed vs Dang (99.49%) vs Chai (94.1%) vs Thanh (97.96%)
  - Ưu thế: 100% tất cả metrics, cơ chế AIx giảm false positive
- **Bảng:** `tab_Comparison_Fall_SFDLA_MobiFall` — So sánh SFDLA và MobiFall
  - Proposed 100% trên cả hai dataset
- Phân tích ưu điểm: nhẹ hơn (RF vs LSTM), thực tế hơn (wearable vs multi-sensor)

#### 3.6 Phân tích tham số và đặc trưng (~2 trang)
##### 3.6.1 Ảnh hưởng kích thước cửa sổ và tần số lấy mẫu
- **Figure:** `accurracyonwindow.png` — F1_mi theo Fs và window size (6 model)
- Kết luận: 50Hz + 3s là cân bằng tối ưu cho thực tế
- Tăng lên 100Hz chỉ cải thiện 0.2–0.3% nhưng tiêu tốn gấp đôi năng lượng

##### 3.6.2 Phân tích đặc trưng (ablation study)
- **Bảng:** `table_changefeature` — F1_mi khi loại từng đặc trưng
- Kết quả: 13 loại đặc trưng (30 feature values) cho F1_mi=96.1% — tốt nhất
- Loại mean → giảm 3.5%; loại energy → giảm 2.7%
- So sánh với Chai (26 types: 95.6%), Wang (16 types: 92.9%), Vi (5 types: 85.7%)

#### 3.7 Hạn chế hiện tại và hướng phát triển (~2 trang)
##### 3.7.1 Hạn chế đã xác định
- Thiết bị lắp ráp thủ công → cồng kềnh, chưa tích hợp được vào trang phục bảo hộ
- Đối tượng thu thập dữ liệu: 100% nam, 22–35 tuổi → hạn chế tính đại diện
- Chưa tích hợp định vị trong nhà và cảnh báo khẩn cấp
- Phân biệt các loại ngã cụ thể còn hạn chế (F1_mi=78.2% trên UniMiB)

##### 3.7.2 Kế hoạch nghiên cứu tiếp theo
- Tối ưu hóa thiết kế công nghiệp: tích hợp vào trang phục bảo hộ, giảm kích thước
- Mở rộng dataset: bổ sung tình nguyện viên nữ, đa dạng thể trạng
- Tích hợp định vị trong nhà (Indoor Positioning System)
- Xây dựng mạng lưới giám sát tập trung: theo dõi nhiều lính cứu hỏa đồng thời
- Cơ chế cảnh báo khẩn cấp tự động khi phát hiện bất động/ngã

---

### KẾT LUẬN VÀ KIẾN NGHỊ (trang 69–72, ~3–4 trang)

**Nguồn:** jsen.tex §VI Conclusion + baocaotiendo.md §II, §III

#### A. Tổng kết đóng góp khoa học (~1 trang)
- Dataset riêng 11 hoạt động lính cứu hỏa — đóng góp cho cộng đồng nghiên cứu
- Pipeline xử lý mới (AIx) — cải thiện nhận dạng chuyển tiếp và ngã
- RFAR system: RF <1MB, F1>96%, latency ~9.6ms — phù hợp thiết bị nhúng
- Thực nghiệm thực tế tại cơ sở PCCC — xác thực tính khả thi ứng dụng

#### B. Đánh giá tiến độ thực hiện đề tài (~1 trang)
- Các công việc đã hoàn thành (từ baocaotiendo.md):
  - Thu thập dữ liệu: 20 tình nguyện viên, 11 hoạt động, 371 phút
  - Thiết kế phần cứng: ADXL345 + ESP32, <200g, hoạt động 24h
  - Quy trình xử lý dữ liệu mới: sliding window + AIx detection
  - Tối ưu hóa mô hình: RF <1MB, F1_mi=96.2%
  - Đánh giá và thực nghiệm: 4 dataset, xác nhận thực tế tại cơ sở PCCC

#### C. Kế hoạch công việc tiếp theo (~1 trang)
- Các công việc dự kiến (từ baocaotiendo.md):
  - Tối ưu hóa thiết kế công nghiệp (tích hợp vào trang phục bảo hộ)
  - Nâng cao tính phổ quát của mô hình (mở rộng dữ liệu, bao gồm nhân sự nữ)
  - Tích hợp hệ thống định vị và cảnh báo
  - Phát triển mạng lưới giám sát tập trung

#### D. Kiến nghị và đề xuất (~0.5 trang)
- Đề xuất hỗ trợ mở rộng thu thập dữ liệu tại nhiều cơ sở PCCC
- Kiến nghị hợp tác với ĐH Phòng cháy Chữa cháy cho giai đoạn thực nghiệm mở rộng
- Đề xuất tích hợp với đề án an toàn lính cứu hỏa cấp bộ

---

### TÀI LIỆU THAM KHẢO (trang 73–80, ~5–8 trang)

**Style:** IEEEtran (giữ nguyên theo template)  
**Số lượng dự kiến:** 45–55 tài liệu

---

## C. DANH SÁCH FIGURE/TABLE VÀ NGUỒN GỐC

### Hình ảnh (12 hình)

| STT | Label trong LaTeX | File | Nguồn | Chương |
|---|---|---|---|---|
| 1.1 | fig:tinh_hinh_chay | `tinh_hinh_chay_no.pdf` | Template gốc | CH1 §1.1 |
| 1.2 | fig:loai_hinh_chay | `loai_hinh_xay_ra_chay.pdf` | Template gốc | CH1 §1.1 |
| 1.3 | fig:nguyen_nhan | `nguyen_nhan_chan_thuong.pdf` | Template gốc | CH1 §1.1 |
| 2.1 | fig:system | `FirefighterSystemfull.png` | jsen.tex Fig.1 | CH2 §2.1 |
| 2.2 | fig:pipeline | `pipeline.png` | jsen.tex Fig.3 | CH2 §2.3–2.4 |
| 2.3 | fig:ml_mcu | `ml_on_mcu.PNG` | jsen.tex (concept) | CH2 §2.5 |
| 2.4 | fig:suyluan | `Suyluan.png` | jsen.tex Fig.6 | CH2 §2.5 |
| 3.1 | fig:findparam | `find_parameter.png` | jsen.tex Fig.5 | CH3 §3.2 |
| 3.2 | fig:rfmatrix | `RFmatrix.png` | jsen.tex Fig.4 | CH3 §3.2–3.4 |
| 3.3 | fig:demo | `demo_realtime.png` | jsen.tex Fig.7 | CH3 §3.3 |
| 3.4 | fig:window | `accurracyonwindow.png` | jsen.tex Fig.8 | CH3 §3.6 |
| 3.5 | fig:nhan_dang | `nhan_dang_hanh_dong.png` | jsen.tex (concept) | CH3 §3.3 |

### Bảng biểu (9 bảng)

| STT | Label trong LaTeX | Nội dung | Nguồn | Chương |
|---|---|---|---|---|
| 1.1 | tab:har_overview | Tổng quan HAR wearable (Table_firemanActivityRecognition) | jsen.tex Tab.I | CH1 §1.3 |
| 2.1 | tab:hardware | Cấu hình phần cứng (table_hardware) | jsen.tex Tab.II | CH2 §2.1 |
| 2.2 | tab:activity | Mô tả 11 hoạt động (table_activity_description) | jsen.tex Tab.III | CH2 §2.2 |
| 2.3 | tab:feature | 30 đặc trưng tối ưu (table_feature) | jsen.tex Tab.IV | CH2 §2.4 |
| 3.1 | tab:model_config | Cấu hình tối ưu 6 model (table_model_config) | jsen.tex Tab.V | CH3 §3.2 |
| 3.2 | tab:rf_results | Metrics theo hoạt động — riêng + RT (table_RF_private_realtime) | jsen.tex Tab.VI | CH3 §3.2–3.3 |
| 3.3 | tab:public | Kết quả 3 dataset công khai (table:evaluation_public) | jsen.tex Tab.VII | CH3 §3.4 |
| 3.4 | tab:unimib | So sánh UniMiB (tab:Comparison_UniMiB) | jsen.tex Tab.VIII | CH3 §3.5 |
| 3.5 | tab:fall_compare | So sánh phát hiện ngã (tab:fall_detection_model + tab_Comparison_Fall) | jsen.tex Tab.IX-X | CH3 §3.5 |
| 3.6 | tab:features_ablation | Ablation đặc trưng (table_changefeature) | jsen.tex Tab.XI | CH3 §3.6 |

---

## D. DANH SÁCH TÀI LIỆU THAM KHẢO

### D.1 Tài liệu giữ nguyên từ references.bib (đề tài gốc — dùng có chọn lọc)

Các tài liệu sau từ references.bib liên quan trực tiếp đến RFAR:
- `campbell2024firefighter` — NFPA statistics 2023, firefighter injuries
- `dinh2022simple` — Dang et al. 2022, accelerometer + CO sensor
- `van2017novel`, `nguyen2021adaptive` — step counter, PDR (nền tảng positioning)
- `pham2018highly`, `ho2016step` — step length estimation

### D.2 Tài liệu từ jsen.bbl — TOÀN BỘ 61 entries (ưu tiên cao nhất)

Các tài liệu quan trọng nhất cần giữ:

**Nhóm: Lính cứu hỏa và an toàn**
- `Clarke2021firefighter`, `Fialho_Fire2024`, `FirefighterImportant2022`
- `Firefighterhealthcare2024`, `Firefighter_toxis`, `carmona2024firefighters`
- `Thanhfire2019`, `Firefighter_Falling_2023`, `CHAI_FIRE2024`, `Chai2021`, `Dang2022`
- `Xu_fire2020`, `wearableFirefirefighter2015`, `wearableFirefirefighter2018`

**Nhóm: HAR — wearable sensor**
- `HARvision2020`, `Accelerometer2021`, `DaoHieu2022`, `ViManhTuyen2024`
- `HongNhung2023`, `Thu2022`, `Lu2020`, `Wang2018`, `Geng2016`
- `preece2008_leutheuser2013_Lu2020`, `HumanActivityRecognition2022`

**Nhóm: Deep Learning HAR**
- `HAR_CNN_2024`, `HAR_DCT_deeplearning2023`, `HAR_CNN_2025`, `HAR_CNN_2022`
- `DeepLearningHAR2022`, `DL2021_HAR_wearable`, `HAR_DL_sensor2023`
- `HAR1_DL_2021`

**Nhóm: TinyML và MCU**
- `TinyML2023`, `MLforMicrocontroller2022`, `SurveyTinyML2023`
- `Tiny_machine_on_microcontroller`, `TinyMLOnEmbedded2025`, `RIOT_tinyML2025`
- `DeepLearning_latency2020`

**Nhóm: Dataset**
- `MobiFall2015`, `SFDLAdataset2016`, `UniMiB_SHAR_2017`
- `Elder_Falling_2019`, `Fall_Elder2022`, `Fall_Elder2019`

**Nhóm: Tối ưu RF và feature**
- `ImportandFeature2023`, `featureSelection2021`
- `Tuning_RandomForest2023`, `Tuning_RandomForest2024`

**Nhóm: So sánh kết quả**
- `UniMiFall2024`, `HAR_deeplearning2021`, `HMM_UniMiB2021`
- `SFDLA_CNN_LSTM_fall2022`, `MobiFall2024`, `MobiFall2019`
- `MobiFall_Yi_2024`

### D.3 Tài liệu bổ sung từ Ref Docs (nếu cần)

| File | Thêm vào mục |
|---|---|
| `dao2023design.pdf` | CH2 §2.1 (thiết kế hệ thống đeo) |
| `conference_icmlant_2025.pdf` | CH1 §1.4 (HAR lính cứu hỏa) |
| `JBHI-01060-2025_Proof_hi.pdf` | CH3 §3.5 (nghiên cứu mở rộng) |
| `Efficient Real-Time Devices...pdf` | CH1 §1.5 (TinyML trên MCU) |

---

## E. DỰ TRÙ SỐ TRANG CHI TIẾT

| Phần | Nội dung | Trang bắt đầu | Số trang |
|---|---|---|---|
| Bìa 1 | BỘ GIÁO DỤC | — | 1 |
| Bìa 2 | TRƯỜNG ĐH PHENIKAA | — | 1 |
| Mục lục | Auto | i | 2 |
| DMHA | 12 hình | iii | 1 |
| DMBP | 9 bảng | iv | 1 |
| DMTV | ~35 từ | v | 2 |
| TÓM TẮT | 5 phần | 1 | 2–3 |
| CH1 §1.1 | Thực trạng cháy nổ | 4 | 3 |
| CH1 §1.2 | Tính cấp thiết HAR | 7 | 2 |
| CH1 §1.3 | Tổng quan HAR wearable | 9 | 5 |
| CH1 §1.4 | Tổng quan HAR lính cứu hỏa | 14 | 4 |
| CH1 §1.5 | TinyML trên MCU | 18 | 3 |
| CH1 §1.6 | Mục tiêu và đóng góp | 21 | 2 |
| CH2 §2.1 | Kiến trúc hệ thống RFAR | 26 | 3 |
| CH2 §2.2 | Cơ sở dữ liệu | 29 | 4 |
| CH2 §2.3 | Xử lý dữ liệu | 33 | 4 |
| CH2 §2.4 | Trích xuất đặc trưng | 37 | 3 |
| CH2 §2.5 | Tối ưu RF trên MCU | 40 | 5 |
| CH3 §3.1 | Phương pháp đánh giá | 51 | 2 |
| CH3 §3.2 | Kết quả dataset riêng | 53 | 2 |
| CH3 §3.3 | Thực nghiệm RT | 55 | 3 |
| CH3 §3.4 | Kết quả 3 dataset công khai | 58 | 3 |
| CH3 §3.5 | So sánh nghiên cứu | 61 | 3 |
| CH3 §3.6 | Phân tích tham số + đặc trưng | 64 | 2 |
| CH3 §3.7 | Hạn chế + hướng PT | 66 | 2 |
| KẾT LUẬN | A+B+C+D | 69 | 3–4 |
| TÀI LIỆU THAM KHẢO | IEEEtran, 45–55 entries | 73 | 5–7 |
| **TỔNG** | | | **~67–78 trang** |

---

*File này hoàn thành Giai đoạn 2 — Sẵn sàng chuyển sang Giai đoạn 3: Viết LaTeX chapter.*
