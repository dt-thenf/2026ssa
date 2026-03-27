# REPORT 01 — KIỂM KÊ SÂU NỘI DUNG NGUỒN CHÍNH (jsen.tex / RFAR PDF)

**Ngày:** 27/03/2026  
**Vòng:** 1 — Chỉ đọc, không sửa file .tex  
**Nguồn quét:**
- `jsen.tex` (1058 dòng, 107 KB) — nguồn LaTeX bài báo IEEE Sensors
- `RFAR_A_Real-Time_Firefighter...pdf` — bản PDF bài báo (không đọc trực tiếp được, nội dung tương đương jsen.tex)

---

## A. MỤC TIÊU CỦA VÒNG

Kiểm kê sâu toàn bộ nội dung có thể tái sử dụng từ bài báo RFAR (jsen.tex) cho báo cáo tiến độ, gồm:
- Bản đồ chi tiết từng nhóm nội dung
- So sánh với draft hiện tại để xác định phần còn thiếu/mỏng
- Danh sách figure/table/algorithm tái sử dụng
- Số liệu quan trọng phải giữ nhất quán
- Phát hiện vấn đề bibliography

---

## B. FILE ĐÃ ĐỌC / VÙNG NỘI DUNG ĐÃ KHAI THÁC

| File | Dòng đã đọc | Ghi chú |
|---|---|---|
| `jsen.tex` | 1–1058 (toàn bộ) | Đọc 2 lần: L1–800, L800–1058 |
| `references.bib` (draft) | 1–623 | 56 entries |
| `references_sensors.bib` | Kiểm tra key | 74 entries gốc |
| `sn-bibliography.bib` (jsen source) | Kiểm tra key | File bib gốc của bài báo |
| Tất cả `Chapters/*.tex` | Đã quét citation keys | 69 citation keys sử dụng |

---

## C. NỘI DUNG RÚT TRÍCH ĐƯỢC

### C.1 BẢN ĐỒ NỘI DUNG TOÀN DIỆN — jsen.tex

---

#### NHÓM 1: BỐI CẢNH VÀ TÍNH CẤP THIẾT (jsen.tex §I, L76–99)

| Nội dung | Dòng jsen.tex | Có trong draft? | Mức khai thác |
|---|---|---|---|
| Đô thị hóa → gia tăng cháy nổ | L79–80 | ✅ CH1 §1.1 | ĐỦ |
| Hạ tầng lỗi thời, thiếu kiểm soát xây dựng | L80 | ✅ nhưng SƠ | CẦN MỞ RỘNG |
| Vai trò lính cứu hỏa, các hiểm nguy | L82–83 | ✅ CH1 §1.1 | ĐỦ |
| **Thống kê USFA 2018–2020:** 23,075 thương vong, 87% structural fires | L83 | ⚠️ THIẾU | CẦN BỔ SUNG |
| **Thống kê NFPA 2023:** 63,175 thương, 89 tử vong, 18,875 suppression | L83 | ✅ CH1 §1.1 | ĐỦ |
| Footnote URLs: USFA, NFPA | L85–86 | ❌ | Có thể thêm |
| 3 hướng ứng dụng KHCN: trang phục, sức khỏe tâm lý, hệ thống giám sát | L88 | ✅ CH1 §1.1 | ĐỦ |
| **Hệ thống liên lạc giữa chỉ huy và tuyến đầu** (Rosing, Takacs) | L89 | ❌ THIẾU | CẦN BỔ SUNG — refs thiếu |
| Hạn chế bộ đàm truyền thống | L92 | ✅ CH1 §1.2 | ĐỦ |
| **Hậu quả phản hồi chậm** (carmona, Waring, Tamrakar) | L92 | ❌ THIẾU | CẦN BỔ SUNG — refs thiếu |
| Khoảng trống: thiếu thông tin vị trí/trạng thái (RF_ForestFires2024) | L94 | ⚠️ MỜ | CẦN BỔ SUNG — ref thiếu |
| HAR = hướng giải pháp tiềm năng | L94 | ✅ CH1 §1.2 | ĐỦ |
| So sánh CV vs wearable sensor | L94 | ✅ CH1 §1.3.1 | ĐỦ |
| Liệt kê ưu điểm wearable: nhỏ gọn, giá rẻ, phát hiện nhanh | L94 | ✅ | ĐỦ |
| **Tổng quan vị trí đặt cảm biến:** thắt lưng, cổ tay, đùi | L96 | ✅ nhưng SƠ | CẦN MỞ RỘNG |
| **Tích hợp cảm biến khác:** gyro, CO, 9-axis, EMG | L96 | ⚠️ SƠ | CẦN MỞ RỘNG |
| HAR cho người cao tuổi vs lính cứu hỏa | L98 | ✅ CH1 §1.3 | ĐỦ |
| **Thách thức: crawling/slithering, môi trường khắc nghiệt** (Shah2024) | L98 | ⚠️ MỜ | CẦN BỔ SUNG — ref thiếu |
| **DL vs ML tradeoff cho MCU** | L98 | ✅ CH1 §1.3.3 | ĐỦ |

**→ Đánh giá:** CH1 §1.1–1.2 cần bổ sung ~3 trang từ các nội dung THIẾU ở trên.

---

#### NHÓM 2: RELATED WORKS (jsen.tex §II, L158–183)

##### §II.A — HAR cho người cao tuổi và wearable (L159–168)

| Nội dung | Dòng | Có trong draft? | Mức khai thác |
|---|---|---|---|
| Nhu cầu chăm sóc người cao tuổi → HAR | L160 | ✅ CH1 §1.3 | SƠ |
| ML truyền thống: DT, RF, GBDT, KNN, SVM | L162 | ✅ CH1 §1.3.2 | ĐỦ |
| **Thu et al. (DT, ESP8266, 99%)** | L162 | ✅ | ĐỦ |
| **Hong et al. (RF, 99.2%, 4 trạng thái)** | L162 | ✅ | ĐỦ |
| **Lu et al. (single accel, 93%)** | L162 | ✅ | ĐỦ |
| **Wang et al. (hierarchical, RF+SVM, 90.4%)** | L162 | ❌ THIẾU | CẦN BỔ SUNG |
| **Preece et al. (14 feature types, time/freq/wavelet, 94%)** | L164 | ✅ CH1 §1.3.2 | ĐỦ |
| **DL: Tang (Triple Cross-Domain, CNN+ResNet, UniMiB)** | L166 | ❌ THIẾU | CẦN BỔ SUNG — hay, so sánh |
| **DL: Xu (DCT channel attention, ResNet, 79.51%)** | L166 | ✅ | ĐỦ |
| **DL: Qin (CLS-CNN-ResNest, 99.12% WISDM)** | L166 | ✅ | ĐỦ |
| **DL: Li (WCNN, smart home, CASAS 86.68–97.08%)** | L166 | ❌ THIẾU | CẦN BỔ SUNG — đa dạng hóa |
| **Kết luận: ML thực tế hơn DL cho MCU** | L168 | ✅ CH1 §1.3.3 | ĐỦ |

##### §II.B — HAR cho lính cứu hỏa (L170–183)

| Nội dung | Dòng | Có trong draft? | Mức khai thác |
|---|---|---|---|
| FAR: yêu cầu đặc thù | L171 | ✅ CH1 §1.4 | ĐỦ |
| **Geng et al. (RF signal, SVM, 88.7%, 7 HĐ, 10s window)** | L173 | ✅ | ĐỦ |
| **Pham/Thanh (sensor fusion, fall, CO, 100%/97.9%)** | L175 | ✅ | ĐỦ |
| **Dang et al. (accel+CO, fall 93%, sen 96.5%)** | L177 | ✅ | ĐỦ |
| **Chai 2021 (LSTM 3 lớp, 5 vị trí, 94.1%)** | L179 | ✅ | ĐỦ |
| **Chai 2024 (sensor fusion, EMG+IMU, 8 HĐ, training fatigue)** | L181 | ✅ nhưng SƠ | CẦN MỞ RỘNG |
| **Phân tích khoảng trống nghiên cứu** | L183 | ✅ CH1 §1.4 cuối | CẦN MỞ RỘNG |
| **Mục tiêu: 11 HĐ, RF trên MCU, AIx** | L183 | ✅ | ĐỦ |

**→ Đánh giá:** CH1 §1.3–1.4 cần bổ sung ~5 trang: thêm Wang, Tang, Li; mở rộng analysis Chai 2024; phân tích sâu khoảng trống.

---

#### NHÓM 3: 4 ĐÓNG GÓP CHÍNH (jsen.tex L146–156)

| # | Đóng góp | Dòng | Trong draft? |
|---|---|---|---|
| 1 | Dataset riêng 11 HĐ bổ sung khoảng trống | L148 | ✅ CH1 §1.6 |
| 2 | Pipeline xử lý tín hiệu mới: sliding window + AIx | L150 | ✅ CH1 §1.6 |
| 3 | Hệ thống RFAR: RF tối ưu <1MB trên MCU, 11 HĐ | L152 | ✅ CH1 §1.6 |
| 4 | Thiết bị đeo <200g, 24h, F1>96%, SFDLA/MobiFall/UniMiB | L154 | ✅ CH1 §1.6 |

**→ Đánh giá:** ĐỦ — đã ánh xạ chính xác.

---

#### NHÓM 4: KIẾN TRÚC HỆ THỐNG (jsen.tex §III.A, L189–244)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| Tổng quan: thiết bị đeo + trung tâm chỉ huy | L198 | ✅ CH2 §2.1.1 | ĐỦ |
| **Figure: FirefighterSystemfull.png** (Fig.1) | L190–196 | ✅ | ĐỦ |
| **Table: table_hardware** | L200–240 | ✅ CH2 §2.1.2 | ĐỦ |
| 11 hoạt động liệt kê | L242 | ✅ | ĐỦ |
| 3 giai đoạn hoạt động | L244 | ✅ | ĐỦ |
| **Radio frequency module, latency** | L242 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **Ứng dụng: tòa nhà xuống cấp, mất điện** | L244 | ❌ THIẾU | CẦN BỔ SUNG — tính ứng dụng thực tế |

**→ Đánh giá:** CH2 §2.1 cần bổ sung ~1 trang: chi tiết module RF, quy trình hoạt động 3 giai đoạn, ứng dụng thực tế.

---

#### NHÓM 5: DATASET (jsen.tex §III.B, L246–295)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| Private dataset: 20 TV nam, 22–35 tuổi, 1.6–1.8m, 60–80kg | L252 | ✅ CH2 §2.2.1 | ĐỦ |
| Phenikaa + ĐH PCCC | L252 | ✅ | ĐỦ |
| Fs=100Hz, 3 trục, đơn vị g | L252 | ✅ | ĐỦ |
| **Complex activities sampled more frequently** | L252 | ❌ THIẾU | CẦN BỔ SUNG |
| **Table: table_activity_description** (11 HĐ) | L254–289 | ✅ CH2 §2.2.1 | ĐỦ |
| 371 phút, >100MB, 60/40 split | L252 | ✅ | ĐỦ |
| **6 model (RF, DT, GBDT, SVM, LBM, XGB) dùng cùng dataset** | L252 | ✅ | ĐỦ |
| **MobiFall:** 4 ngã + 9 ADL, smartphone pocket | L291–295 | ✅ CH2 §2.2.2 | ĐỦ |
| **SFDLA:** waist-mounted | L291–295 | ✅ | ĐỦ |
| **UniMiB-SHAR:** 17 HĐ, smartphone pocket | L291–295 | ✅ | ĐỦ |
| **Cách tiếp cận mới: ngã = behavior, không phải event** | L292 | ✅ | nhưng SƠ — CẦN MỞ RỘNG |
| Footnote URLs cho 3 dataset | L293–295 | ❌ THIẾU | Nên thêm |

**→ Đánh giá:** CH2 §2.2 cần bổ sung ~1.5 trang: lý do chọn đối tượng, complex sampling, phân tích chi tiết hơn 3 dataset công khai.

---

#### NHÓM 6: DOWNSAMPLING + SLIDING WINDOW (jsen.tex §III.C, L297–311)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| Lý do giảm 100→50Hz, moving average filter | L302 | ✅ CH2 §2.3.1 | ĐỦ |
| **Eq: a_k[n] resample** | L303–306 | ✅ | ĐỦ |
| **Phân tích vai trò Fs cho wearable (1Hz/50Hz/100Hz)** | L302 | ⚠️ SƠ | CẦN MỞ RỘNG — thêm refs |
| Sliding window Δt=3s, 150 mẫu, N_Δt windows | L309–311 | ✅ CH2 §2.3.2 | ĐỦ |
| **Phân tích ảnh hưởng window: 10s/8s/6s/3s** | L309 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **References: 10s (Hong), 8s (Vi), 6s (Thu), 3s (Thanh, Dang)** | L309 | ⚠️ SƠ | CẦN MỞ RỘNG |
| 60/40 train/test split | L311 | ✅ | ĐỦ |

---

#### NHÓM 7: LABELLING (jsen.tex §III.C labelling, L313–324)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| 3 bước gán nhãn: xác định → phân đoạn → gán | L315–324 | ✅ CH2 §2.3.4 | nhưng RẤT SƠ |
| **Chi tiết Step 1:** 11 labels, 0–10 | L317 | ✅ | ĐỦ |
| **Chi tiết Step 2:** Sequential segmentation, N_Δt windows | L319–321 | ❌ THIẾU | CẦN BỔ SUNG |
| **Chi tiết Step 3:** L_j = k, labeled pairs notation | L323–324 | ❌ THIẾU | CẦN BỔ SUNG |
| **2 supervisors giám sát** | L315 | ✅ | ĐỦ |

**→ Đánh giá:** CH2 cần bổ sung ~0.5 trang chi tiết quá trình gán nhãn.

---

#### NHÓM 8: AIx PIPELINE (jsen.tex §III.C new pipeline, L326–363)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Figure: pipeline.png** (Fig.3) — 4 panel (a,b,c,d) | L328–333 | ✅ CH2 §2.3.3 | ĐỦ |
| Giải thích dark blue vs green arrows | L335 | ✅ | ĐỦ |
| **Step 1: AIx detection** — Δs[n] formula | L337–354 | ✅ | ĐỦ |
| **ΔW=0.5s** — lý do: flight time ~0.34s (Thanh) | L337 | ✅ | ĐỦ |
| **Threshold = 1.8g** (Thanh et al.) | L350–354 | ✅ | ĐỦ |
| **Step 2: Data collection** [n0-3Fs, n0+3Fs] | L356–358 | ✅ | ĐỦ |
| **Step 3: Processing + classification** | L361–362 | ✅ | nhưng SƠ |
| **Step size logic: 3s bình thường, 0.5s khi AIx>threshold** | L799 | ✅ CH3 §3.3 | ĐỦ |

**→ Đánh giá:** ĐỦ — pipeline đã được khai thác tốt.

---

#### NHÓM 9: FEATURE EXTRACTION (jsen.tex §III.D, L365–437)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| Tầm quan trọng feature extraction | L367 | ✅ CH2 §2.4 | ĐỦ |
| **Chai: 654 features (25 time + 6 freq), 90%+** | L367 | ❌ THIẾU | CẦN BỔ SUNG — phân tích chi tiết |
| **Autoregressive coefficients → không phù hợp MCU** | L367 | ❌ THIẾU | CẦN BỔ SUNG |
| **16 loại đặc trưng ban đầu xem xét** (liệt kê đầy đủ) | L367 | ⚠️ SƠ | CẦN MỞ RỘNG — liệt kê 4 loại bị loại |
| **Phương pháp loại trừ: importance < 0.01 = 0.5×σ** | L369 | ✅ | ĐỦ |
| **Figure: pipeline-d** (feature importance) | L369 | ✅ | ĐỦ |
| **σ importance ≈ 0.02** | L369 | ❌ THIẾU | CẦN BỔ SUNG — chi tiết quan trọng |
| **Table: table_feature** (30 features, 12 loại + HC) | L371–437 | ✅ CH2 §2.4.2 | ĐỦ |
| **4 loại bị loại:** skewness, kurtosis, autocorrelation, hjorth mobility (riêng) | L367 | ❌ THIẾU | CẦN BỔ SUNG |

**→ Đánh giá:** CH2 §2.4 cần bổ sung ~1.5 trang: phân tích 654 features của Chai, 16→13 loại, lý do loại 4 loại.

---

#### NHÓM 10: OPTIMIZATION OF RF ON MICROCONTROLLERS (jsen.tex §III.E, L440–519)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| Bài toán tối ưu: D = {(feat_j, L_j)} | L442–458 | ✅ CH2 §2.5.1 | ĐỦ |
| **RF structure: n_estimators trees, max_depth** | L446 | ✅ | ĐỦ |
| **Bootstrap sampling technique** | L446 | ❌ THIẾU | CẦN BỔ SUNG |
| **Prediction: majority voting** | L454–457 | ✅ | ĐỦ |
| **RAM constraints: concurrent real-time + system ops** | L461 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **Flash: firmware + sensor buffers + config** | L461 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **~1MB deployment limit** (recent studies) | L461 | ✅ | ĐỦ |
| **Algorithm: OptimizationRandomForest** | L466–493 | ✅ CH2 §2.5.1 | ĐỦ |
| **Deployment steps: micromlgen, port(), random_forest.h** | L497–519 | ✅ CH2 §2.5.3 | ĐỦ |
| **Eloquent::ml::port::RF rf;** | L511 | ✅ | ĐỦ |
| **rf.predict(feat_j)** | L517 | ✅ | ĐỦ |

**→ Đánh giá:** CH2 §2.5 cần bổ sung ~1 trang: bootstrap sampling, RAM/flash constraints chi tiết.

---

#### NHÓM 11: EVALUATION METRICS (jsen.tex §IV.A, L522–582)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **5 metrics: acc, sen, spe, pre, F1** | L526–549 | ✅ CH3 §3.1 | ĐỦ |
| **Eq: acc, sen, spe, pre** (Eq. 5–8) | L528–548 | ✅ | nhưng gộp 2 eq/dòng |
| **Eq: F1, F1_mi, F1_ma** (Eq. 9–11) | L554–567 | ✅ | ĐỦ |
| **TP/FP/TN/FN definitions** | L571 | ✅ | ĐỦ |
| **K-fold CV: k=5, Score_CV formula** | L573–581 | ⚠️ SƠ | CẦN MỞ RỘNG — chi tiết fold |

**→ Đánh giá:** CH3 §3.1 cần bổ sung ~0.5 trang: chi tiết K-fold, lý do chọn k=5.

---

#### NHÓM 12: RESULTS ON PRIVATE DATASET (jsen.tex §IV.B, L585–718)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Table: table_model_config** (6 model comparison) | L590–638 | ✅ CH2 §2.5.2 | ĐỦ |
| **Figure: find_parameter.png** (Fig.5) | L640–645 | ✅ CH2 §2.5.2 | ĐỦ |
| **Phân tích chi tiết XGB, GBDT, RF, LBM parameter ranges** | L657 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **RF: 0.921709MB, train 0.093589s, test 0.010951s, ~3.95μs/prediction** | L660 | ✅ | ĐỦ |
| **Phân tích chi tiết XGB vs LBM vs DT** | L660 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **Figure: RFmatrix.png** — 5 panel confusion matrices | L647–655 | ✅ CH3 §3.2.2 | ĐỦ |
| **Chi tiết confusion: DS↔US, WA↔US, WS↔WA** | L662 | ✅ | ĐỦ nhưng có thể MỞ RỘNG |
| **Table: table_RF_private_realtime** (per-activity metrics) | L665–712 | ✅ CH3 §3.2 | ĐỦ |
| **Phân tích chi tiết: ST=100%, SI=100%, FA=100%** | L714 | ✅ | ĐỦ |
| **Phân tích overfitting: consistent across eval schemes** | L718 | ❌ THIẾU | CẦN BỔ SUNG — quan trọng |

---

#### NHÓM 13: RESULTS ON PUBLIC DATASETS (jsen.tex §IV.B, L720–781)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **SFDLA:** loại female, loại head/wrist/thigh/chest, giữ waist | L721 | ✅ CH3 §3.4.1 | nhưng SƠ |
| **SFDLA confusion details:** RI, LY, FA=0 error; WA↔LI | L723–726 | ❌ THIẾU | CẦN BỔ SUNG — chi tiết confusion |
| **Table: evaluation_public** | L731–760 | ✅ CH3 §3.4 | ĐỦ |
| **MobiFall:** loại BSC, CSI, CSO; loại female | L764 | ✅ CH3 §3.4.2 | ĐỦ |
| **MobiFall confusion: US(32/45), DS(35/47)** | L768 | ⚠️ SƠ | CẦN MỞ RỘNG |
| **UniMiB AF17:** 17 HĐ liệt kê, preprocessing orientation | L775 | ✅ CH3 §3.4.3 | ĐỦ |
| **UniMiB chi tiết: WA 233/242(96.3%), STL 22/38(57.9%)** | L777 | ❌ THIẾU | CẦN BỔ SUNG |
| **UniMiB fall group: 879 windows, 431 correct** | L779 | ❌ THIẾU | CẦN BỔ SUNG |
| **UniMiB: FAF 61/72(84.7%), FART 32/79(40.5%), SC 19/85(22.4%)** | L779 | ❌ THIẾU | CẦN BỔ SUNG — chi tiết rất hay |
| **UniMiB: no FA misclassified as ADL** | L781 | ❌ THIẾU | CẦN BỔ SUNG |

**→ Đánh giá:** CH3 §3.4 cần bổ sung ~2 trang: chi tiết confusion SFDLA, MobiFall, UniMiB.

---

#### NHÓM 14: ON-DEVICE DEPLOYMENT + PRACTICAL EVALUATION (jsen.tex §IV.C, L783–817)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Figure: demo_realtime.png** (Fig.7) | L786–792 | ✅ CH3 §3.3 | ĐỦ |
| **Demo video link:** https://youtu.be/S4hAzgEo-NA | L1019 | ❌ | Có thể thêm vào phụ lục |
| **Source code:** https://github.com/HieuSSALAB/FireFighter | L1021 | ❌ | Có thể thêm vào phụ lục |
| **Step size logic:** 3s normal, 0.5s khi AIx>threshold | L799 | ✅ CH3 §3.3 | ĐỦ |
| **Figure: Suyluan.png** (Fig.6) — inference timing | L801–807 | ✅ CH2 §2.5.3 | ĐỦ |
| **450 samples / 3s window** | L809 | ⚠️ | Sai? jsen nói 450 samples (3s×150Hz=450??), draft nói 150 mẫu (3s×50Hz) → **CẦN XÁC NHẬN** |
| **Feature extraction: 84,507 lines, ~8,858 μs** | L809 | ✅ | ĐỦ |
| **RF inference: 140,838 lines, 733–738 μs** | L809 | ✅ | ĐỦ |
| **SPI: 10MHz, ~1.6 μs** | L809 | ❌ THIẾU | CẦN BỔ SUNG |
| **Total latency: 9.561–9.596 ms** | L811 | ✅ | ĐỦ |
| **RT results: acc=99.4%, F1=96.2%** | L814 | ✅ CH3 §3.3 | ĐỦ |
| **FA: 162/162 = 100%** | L814 | ✅ | ĐỦ |
| **RT vs private: <1% difference all metrics** | L816 | ✅ | nhưng SƠ |
| **Lý giải: AIx giúp handle transitions** | L816 | ✅ | ĐỦ |
| **Ethics approval:** Phenikaa ERB #024.22/DHP-HDDD | L1023 | ❌ | Có thể thêm vào CH2 |

---

#### NHÓM 15: COMPARISON WITH PRIOR WORKS (jsen.tex §V.A, L819–921)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Table: Comparison_UniMiB** — AF17 + AF2 | L823–849 | ✅ CH3 §3.5.1 | ĐỦ |
| **Phân tích: CNN-DCT freq-domain, CNN-TSFDU-LW** | L851 | ✅ | nhưng SƠ |
| **Preprocessing: signal alignment to common orientation** | L851 | ❌ THIẾU | CẦN BỔ SUNG |
| **Phân tích tổng quan: private tốt, MobiFall/SFDLA tốt, UniMiB thấp** | L853 | ✅ | ĐỦ |
| **Table: fall_detection_model** — so sánh ngã cho firefighter | L856–877 | ✅ CH3 §3.5.2 | ĐỦ |
| **Phân tích chi tiết: Thanh (fixed threshold), Dang (fixed threshold)** | L879 | ✅ | nhưng SƠ |
| **Chai: chest sensor → FA↔WS confusion** | L879 | ❌ THIẾU | CẦN BỔ SUNG |
| **Table: Comparison_Fall_SFDLA_MobiFall** | L883–914 | ✅ CH3 §3.5.2 | ĐỦ |
| **Phân tích Yi model: 36 features + complex LSTM** | L917 | ❌ THIẾU | CẦN BỔ SUNG |
| **SFDLA: device placement explanation (pocket vs fixed waist)** | L919 | ❌ THIẾU | CẦN BỔ SUNG |
| **AF2: CNN-PCNN, 1D-CNN, HMMs analysis** | L921 | ⚠️ SƠ | CẦN MỞ RỘNG |

**→ Đánh giá:** CH3 §3.5 cần bổ sung ~1.5 trang: phân tích sâu so sánh, ưu điểm AIx vs fixed threshold, Yi LSTM.

---

#### NHÓM 16: WINDOW SIZE + SAMPLING FREQUENCY (jsen.tex §V.B, L923–935)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Figure: accurracyonwindow.png** (Fig.8) | L925–930 | ✅ CH3 §3.6.1 | ĐỦ |
| **6s window + 50% overlap → stable trên 20–100Hz** | L933 | ❌ THIẾU | CẦN BỔ SUNG |
| **50–100Hz + 3–6s → F1>95%** | L933 | ✅ | ĐỦ |
| **100Hz vs 50Hz: chỉ +0.2–0.3%** | L933 | ✅ | ĐỦ |
| **6s: F1>99% (GBDT, LBM) nhưng overlapping actions** | L933–935 | ✅ | ĐỦ |
| **3s: F1 thấp hơn 2–3%, nhưng thực tế hơn** | L935 | ✅ | ĐỦ |
| **1s: giảm ~15%** | L933 | ✅ | ĐỦ |
| **50Hz: tiết kiệm năng lượng vs 100Hz** | L935 | ✅ | ĐỦ |

---

#### NHÓM 17: FEATURE EFFECTIVENESS / ABLATION (jsen.tex §V.C, L938–1001)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Table: table_changefeature** — ablation 13 loại | L942–996 | ✅ CH3 §3.6.2 | ĐỦ |
| **Phân tích: loại mean → -3.5%, loại AAC → -3.1%** | L999 | ✅ | ĐỦ |
| **Chai 26 types: 95.6%, Wang 16 types: 92.9%** | L999 | ✅ | ĐỦ |
| **Vi 5 types: 85.7%, Hong 5 types: 83.1%** | L999 | ✅ | ĐỦ |
| **Kết luận: 13 types = balance tốt nhất** | L999–1001 | ✅ | ĐỦ |
| **Phân tích: thêm features → tăng computation → giảm RT perf** | L1001 | ❌ THIẾU | CẦN BỔ SUNG |

---

#### NHÓM 18: LIMITATIONS (jsen.tex §V.D, L1003–1010)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Thiết bị lắp ráp thủ công, kích thước lớn** | L1006 | ✅ CH3 §3.7.1 | ĐỦ |
| **Chỉ có male volunteers** | L1006 | ✅ | ĐỦ |
| **Chưa tích hợp location tracking + emergency alerts** | L1008 | ✅ | ĐỦ |
| **Cần phối hợp SW/HW/protocol** | L1008 | ❌ THIẾU | CẦN BỔ SUNG |
| **Tối ưu size, weight, HW upgrades = key objective** | L1008 | ⚠️ SƠ | CẦN MỞ RỘNG |

---

#### NHÓM 19: FUTURE WORK (jsen.tex §V.D, L1010)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Emergency support system toàn diện** | L1010 | ✅ CH3 §3.7.2 | ĐỦ |
| **Monitor work status + emergency alerts + multi-firefighter network** | L1010 | ✅ | ĐỦ |

---

#### NHÓM 20: CONCLUSION (jsen.tex §VI, L1011–1013)

| Nội dung | Dòng | Trong draft? | Mức khai thác |
|---|---|---|---|
| **Dataset bổ sung khoảng trống** | L1013 | ✅ Conclusion §A | ĐỦ |
| **Pipeline: sliding window + AIx → adjust position + starting time** | L1013 | ✅ | ĐỦ |
| **RFAR: RF tối ưu trên MCU, F1>96% private, >78% public** | L1013 | ✅ | ĐỦ |
| **Real-time: all metrics >96%** | L1013 | ✅ | ĐỦ |
| **Indoor emergency positioning support system** | L1013 | ✅ Conclusion §C | ĐỦ |
| **Acknowledgment: MHN2024-01.02 Hanoi Open University** | L1016 | ❌ | Có thể thêm |
| **Ethics: Phenikaa ERB #024.22/DHP-HDDD** | L1023 | ❌ | Có thể thêm CH2 |
| **Data availability: DOI 10.21227/9w3p-v638** | L1026 | ❌ | Có thể thêm |

---

### C.2 DANH SÁCH FIGURE/TABLE/ALGORITHM TÁI SỬ DỤNG

| # | Loại | Label trong jsen.tex | Tên file | Trong draft? | Ghi chú |
|---|---|---|---|---|---|
| 1 | Figure | Firefighter_System (Fig.1) | FirefighterSystemfull.png | ✅ | |
| 2 | Figure | pipeline (Fig.3) | pipeline.png | ✅ | |
| 3 | Figure | findparameter (Fig.5) | find_parameter.png | ✅ | |
| 4 | Figure | RF_matrix (Fig.4) | RFmatrix.png | ✅ | |
| 5 | Figure | Demorealtime (Fig.7) | demo_realtime.png | ✅ | CẦN NÉN 20→<3MB |
| 6 | Figure | suyluan (Fig.6) | Suyluan.png | ✅ | |
| 7 | Figure | accurracyonwindow (Fig.8) | accurracyonwindow.png | ✅ | |
| 8 | Figure | — (commented, L1052–1055) | graph_linh_cuu_hoa.png | ❌ | CHƯA DÙNG — thêm vào CH1 |
| 9 | Figure | — | nhan_dang_hanh_dong.png | ❌ | CHƯA DÙNG |
| 10 | Figure | — | ml_on_mcu.PNG | ❌ | CHƯA DÙNG — thêm vào CH2 TinyML |
| 11 | Figure | — | loai_hinh_xay_ra_chay.pdf | ❌ | CHƯA DÙNG — thêm vào CH1 |
| 12 | Table | Table_firemanActivityRecognition (Tab.I) | — | ✅ | |
| 13 | Table | table_hardware (Tab.II) | — | ✅ | |
| 14 | Table | table_activity_description (Tab.III) | — | ✅ | |
| 15 | Table | table_feature (Tab.IV) | — | ✅ | |
| 16 | Table | table_model_config (Tab.V) | — | ✅ | |
| 17 | Table | table_RF_private_realtime (Tab.VI) | — | ✅ | |
| 18 | Table | evaluation_public (Tab.VII) | — | ✅ | |
| 19 | Table | Comparison_UniMiB (Tab.VIII) | — | ✅ | |
| 20 | Table | fall_detection_model (Tab.IX) | — | ✅ | |
| 21 | Table | Comparison_Fall_SFDLA_MobiFall (Tab.X) | — | ✅ | |
| 22 | Table | table_changefeature (Tab.XI) | — | ✅ | |
| 23 | Algorithm | OptimizationRandomForest (Alg.1) | — | ✅ | |

---

### C.3 SỐ LIỆU QUAN TRỌNG PHẢI GIỮ NGUYÊN

| Chỉ số | Giá trị chính xác | Nguồn (jsen.tex) | Trong draft? |
|---|---|---|---|
| **RF model size** | 0.921709 MB | L615, L660 | ✅ (dùng 0.92 MB / 0.9217 MB) |
| **RF n_estimators** | 17 | L615 | ✅ |
| **RF max_depth** | 14 | L615 | ✅ |
| **RF train time** | 0.093589 s | L615, L660 | ✅ |
| **RF test time** | 0.010951 s | L615, L660 | ✅ |
| **RF per-prediction time** | ~3.95 μs | L660 | ✅ |
| **Private: acc=99.3%, F1_mi=96.1%, F1_ma=97.0%** | Tab.V, L615 | ✅ |
| **Private: sen=97.0%, spe=99.6%, pre=97.1%** | Tab.V, L615 | ⚠️ KHÁC — Tab.VI: sen=95.9%, pre=96.4% |
| **RT: acc=99.4%, F1_mi=96.2%** | Tab.VI, L814 | ✅ |
| **RT: sen=96.4%, pre=96.6%** | Tab.VI, L814 | ✅ |
| **SFDLA: F1_mi=96.6%, acc=99.4%** | Tab.VII, L728 | ✅ |
| **SFDLA model size** | 0.750984 MB | Tab.VII, L754 | ❌ THIẾU |
| **MobiFall: F1_mi=96.6%, acc=99.2%** | Tab.VII, L770 | ✅ |
| **MobiFall model size** | 0.429473 MB | Tab.VII, L755 | ❌ THIẾU |
| **UniMiB AF17: F1_mi=78.2%, acc=97.4%** | Tab.VII, L756 | ✅ |
| **UniMiB AF2: 100% all metrics** | Tab.VIII, L842 | ✅ |
| **UniMiB model size** | 0.975449 MB | Tab.VII, L756 | ❌ THIẾU |
| **Feature extraction: 84,507 lines, ~8,858 μs** | L809 | ✅ |
| **RF inference: 140,838 lines, 733–738 μs** | L809 | ✅ |
| **Total latency: 9.561–9.596 ms** | L811 | ✅ |
| **Data: 20 TV, 22–35 tuổi, 1.6–1.8m, 60–80kg** | L252 | ✅ |
| **Data: 371 phút, >100MB** | L252 | ✅ |
| **60/40 train/test split** | L311 | ✅ |
| **ΔW=0.5s, threshold=1.8g** | L337, L350 | ✅ |
| **FA RT: 162/162 = 100%** | L814 | ✅ |
| **NFPA 2023: 63,175 injuries, 89 fatalities, 18,875 suppression** | L83 | ✅ |
| **USFA 2018–2020: 23,075 injured, 87% structural** | L83 | ⚠️ SƠ |
| **SPI transmission: 10MHz, ~1.6 μs** | L809 | ❌ |

⚠️ **CẢNH BÁO SỐ LIỆU:** Có sự khác biệt giữa `table_model_config` (Tab.V: tổng thể) và `table_RF_private_realtime` (Tab.VI: per-activity) trong jsen.tex. Tab.V là kết quả xác thực chéo tổng thể; Tab.VI chi tiết hơn. Draft hiện tại trộn số liệu từ cả hai bảng — cần kiểm tra nhất quán.

---

### C.4 VẤN ĐỀ BIBLIOGRAPHY — CẢNH BÁO NGHIÊM TRỌNG

#### 12 citation keys từ jsen.tex THIẾU trong references.bib (có trong references_sensors.bib):

| Key | Sử dụng trong jsen.tex | Cần cho chương nào |
|---|---|---|
| `accelerometer_error2024` | §I | CH1 |
| `AccelerometerHAR2023` | §I | CH1 |
| `DL_Abdi2024` | §III.C | CH2 |
| `Firefighter_limited2019` | §I | CH1 |
| `Firefigter_toxis_2016` | §I | CH1 |
| `RealtimeOnESP32_2015` | §III.C | CH2 |
| `RF_ForestFires2024` | §I, §II | CH1 |
| `Rosing04032022` | §I | CH1 |
| `Shah2024` | §I | CH1 |
| `Takacs2022` | §I | CH1 |
| `Tamrakar2020` | §I | CH1 |
| `Waring2024` | §I | CH1 |

#### 22 citation keys DÙNG trong draft nhưng KHÔNG TỒN TẠI ở bất kỳ file .bib nào:

| Key | Ghi chú |
|---|---|
| `al2021towards` | Không rõ nguồn |
| `bui2024smart` | Có thể bài nhóm nghiên cứu |
| `bui2025development` | Có thể bài nhóm nghiên cứu |
| `chen2019detection` | Không rõ |
| `cinaz2008headslam` | Không rõ |
| `dao2022human` | Trùng DaoHieu2022? |
| `dao2023developing` | Bài Dao khác |
| `dao2025rfar` | Chính bài RFAR này |
| `de2017hybrid` | Không rõ |
| `ek2025comparing` | Không rõ |
| `ho2016step` | Bài step length |
| `hong2023low` | Trùng HongNhung2023? |
| `lowe2022towards` | Không rõ |
| `pham2018highly` | Bài Pham |
| `soni2024cabmnet` | Không rõ |
| `thu2022real` | Trùng Thu2022? |
| `van2019development` | Bài Van |
| `vi2024efficient` | Trùng ViManhTuyen2024? |
| `vu2024sports` | Không rõ |
| `yi2024fall` | Trùng MobiFall_Yi_2024? |
| `yuan2016research` | Không rõ |
| `zhang2024effective` | Trùng MobiFall2024? |

**→ HÀNH ĐỘNG CẦN THIẾT:** Phải bổ sung 12 keys từ sensors bib vào references.bib VÀ xử lý 22 keys "ma" (thêm entries hoặc xóa citations).

---

## D. ĐỀ XUẤT THAY ĐỔI VÀO BÁO CÁO

**KHÔNG thay đổi file .tex trong vòng này.** Dưới đây là tổng hợp đề xuất cho các vòng tiếp theo:

### D.1 Ưu tiên mở rộng nội dung (theo thứ tự trang bổ sung)

| TT | Chương | Mục | Nội dung cần bổ sung từ jsen.tex | Trang ước tính |
|---|---|---|---|---|
| 1 | CH1 | §1.1 | USFA 2018–2020 stats; hệ thống liên lạc chỉ huy; hậu quả phản hồi chậm | +1.5 |
| 2 | CH1 | §1.3 | Wang hierarchical; Tang Triple Cross-Domain; Li WCNN smart home | +2 |
| 3 | CH1 | §1.4 | Phân tích sâu Chai 2024; khoảng trống chi tiết hơn | +1.5 |
| 4 | CH1 | §1.5 | RAM/Flash constraints chi tiết; bootstrap sampling | +1 |
| 5 | CH2 | §2.2 | Complex sampling; cách tiếp cận ngã=behavior chi tiết | +1 |
| 6 | CH2 | §2.4 | 654 features Chai; 16→13 loại; autoregressive; σ≈0.02 | +1.5 |
| 7 | CH2 | §2.5 | Parameter range analysis; overfitting analysis | +1 |
| 8 | CH3 | §3.4 | Chi tiết confusion SFDLA/MobiFall/UniMiB (FAF, FART, SC) | +2 |
| 9 | CH3 | §3.5 | Yi LSTM comparison; device placement; AIx vs fixed threshold | +1.5 |
| 10 | CH3 | §3.1 | K-fold CV chi tiết | +0.5 |
| | | | **TỔNG BỔ SUNG ƯỚC TÍNH** | **+13.5 trang** |

### D.2 Hình ảnh chưa sử dụng — đề xuất thêm vào

| Hình | Đề xuất chương | Lý do |
|---|---|---|
| `graph_linh_cuu_hoa.png` | CH1 §1.1 hoặc §1.4 | Biểu đồ thống kê hoạt động lính cứu hỏa |
| `loai_hinh_xay_ra_chay.pdf` | CH1 §1.1 | Phân loại loại hình cháy — đã nêu trong đề cương |
| `ml_on_mcu.PNG` | CH1 §1.5 hoặc CH2 §2.5 | Sơ đồ TinyML trên MCU |
| `nhan_dang_hanh_dong.png` | CH2 §2.1 hoặc CH3 §3.3 | Minh họa nhận dạng hoạt động |

### D.3 Sửa bibliography (CRITICAL — cần làm trước khi biên dịch)

1. **Merge 12 keys** từ `references_sensors.bib` vào `references.bib`
2. **Xử lý 22 keys "ma"** — xác định: trùng lặp? cần thêm entry? hoặc xóa citation?

---

## E. RỦI RO / ĐIỂM CẦN NGƯỜI DÙNG REVIEW

1. **⚠️ 22 citation keys trong draft KHÔNG CÓ trong bất kỳ file .bib nào.** Đây là lỗi biên dịch nghiêm trọng — LaTeX sẽ hiển thị `[?]` cho tất cả citations này. Cần xác nhận: những keys nào là bài viết của nhóm nghiên cứu (cần tạo entry), và những keys nào trùng lặp (cần thống nhất tên).

2. **Sự khác biệt số liệu giữa Tab.V và Tab.VI trong jsen.tex:** Tab.V (model_config) cho sen=97.0%, pre=97.1% nhưng Tab.VI (RF_private_realtime) cho Overall sen=95.9%, pre=96.4%. Draft hiện tại dùng cả hai — cần xác nhận nguồn nào dùng ở đâu.

3. **jsen.tex L809 nói "450 samples within 3-second window"** nhưng nếu Fs=50Hz thì 3s chỉ có 150 samples. Có thể jsen.tex nói 450 = 150 samples × 3 trục. Cần xác nhận.

4. **Model size cho public datasets** (SFDLA: 0.75MB, MobiFall: 0.43MB, UniMiB: 0.98MB) — draft hiện tại KHÔNG đề cập, chỉ nói model chung 0.92MB. Cần quyết định có bổ sung không.

5. **12 citation keys thiếu** sẽ gây `[?]` nếu mở rộng nội dung CH1 dùng tới chúng. Cần merge trước khi viết nội dung mở rộng.

6. **Hình `graph_linh_cuu_hoa.png`** (3MB) — trong jsen.tex bị comment out (L1052–1055). Có dùng trong báo cáo tiến độ không?

---

*Vòng 1 hoàn thành — Không thay đổi file .tex nào.*
