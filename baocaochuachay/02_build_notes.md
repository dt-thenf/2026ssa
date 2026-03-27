# 02_BUILD_NOTES — Ghi chú quá trình xây dựng Giai đoạn 3

**Ngày build:** 27/03/2026  
**Trạng thái biên dịch:** THANH CONG — 0 loi, 0 undefined citations  
**Ket qua:** 41 trang, 33.4 MB PDF

---

## File da tao moi (Giai doan 3)

| File | Vi tri | Trang thai | Ghi chu |
|---|---|---|---|
| `main.tex` | `baocaochuachay/` | Tao moi | Dua template, doi tieu de RFAR + thong tin sinh vien |
| `references.bib` | `baocaochuachay/` | Tao moi (ghi de) | Hop nhat 60+ entries tu jsen.bbl + loc bot entries phu hop tu references.bib goc |
| `Chapters/abstract.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | TOM TAT: 5 phan, van phong hoc thuat, tieng Viet |
| `Chapters/abbreviations.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | 51 tu viet tat RFAR-specific, dung longtable |
| `Chapters/literature_review.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | CHUONG 1: 6 tieu muc, 2 hinh, 1 bang |
| `Chapters/materials_and_methods.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | CHUONG 2: 5 tieu muc, 7 hinh/bang, algorithm |
| `Chapters/results_and_discussion.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | CHUONG 3: 7 tieu muc, 7 hinh/bang |
| `Chapters/conclusion.tex` | `baocaochuachay/Chapters/` | Viet moi hoan toan | KET LUAN: 4 phan A-D |

---

## File ke thua tu template (khong doi)

| File | Vi tri | Ghi chu |
|---|---|---|
| `main.tex` preamble | Template goc | Giu nguyen class, packages, pagestyle, fonts, captions |
| Cac file .tex phu tu template | `Chapters/` | Giu de tham khao: proposed_system.tex, method_har.tex, result_har.tex, etc. — KHONG \input trong main.tex moi |

---

## Figure da su dung

| File hinh | Tu nguon nao | Chapter | Ghi chu |
|---|---|---|---|
| `Figure/tinh_hinh_chay_no.pdf` | Template goc | CH1 | OK |
| `Figure/nguyen_nhan_chan_thuong.pdf` | Template goc | CH1 | WARNING: PDF incompatibility (hien thi duoc, khong gay loi) |
| `Figure/FirefighterSystemfull.png` | jsen.tex Fig.1 | CH2 | OK — 2.7 MB |
| `Figure/pipeline.png` | jsen.tex Fig.3 | CH2 | OK — 442 KB |
| `Figure/find_parameter.png` | jsen.tex Fig.5 (da doi ten) | CH2/CH3 | OK — 571 KB |
| `Figure/Suyluan.png` | jsen.tex Fig.6 | CH2 | OK — 670 KB |
| `Figure/RFmatrix.png` | jsen.tex Fig.4 | CH3 | OK — 313 KB |
| `Figure/demo_realtime.png` | jsen.tex Fig.7 (da doi ten) | CH3 | FILE LON: 20 MB — nen xem xet nen |
| `Figure/accurracyonwindow.png` | jsen.tex Fig.8 | CH3 | OK — 146 KB |

---

## Figure CHUA dung (co san trong Figure/)

| File hinh | Li do chua dung | De xuat |
|---|---|---|
| `Figure/loai_hinh_xay_ra_chay.pdf` | Bo qua de giam dai CH1 | Them vao CH1 §1.1 neu can tang trang |
| `Figure/nhan_dang_hanh_dong.png` | Tien do chua them | Them vao CH3 §3.3 de minh hoa |
| `Figure/ml_on_mcu.PNG` | Tien do chua them | Them vao CH2 §2.5 de minh hoa TinyML |
| `Figure/graph_linh_cuu_hoa.png` | Kho xoay, 3 MB | Them vao CH1 §1.2 neu can tang trang |

---

## Trang thai bien dich

### Lan bien dich thu 1 (pdflatex lan 1):
- PDF tao thanh cong
- Warnings: font size 13pt (khong gay loi - "ignored")
- Warnings: citation undefined (binh thuong khi chua chay bibtex)

### Lan 2 (bibtex + pdflatex x3):
- **0 loi (!)**
- **0 undefined citations**
- **Output: 41 trang, 33.4 MB**
- Warnings: `PDF incompatibility` voi `nguyen_nhan_chan_thuong.pdf` (hien thi duoc)
- Warnings: font size (ignored, khong anh huong)

---

## Do dai hien tai: 41 trang

**Can mo rong them 20+ trang de dat muc tieu 60-80.** Cac muc co the mo rong:

| Chuong | Mo rong co the | Tang trang |
|---|---|---|
| CH1 §1.3 | Bo sung 2-3 bang so sanh HAR methods, phan tich sau hon | +4 |
| CH1 §1.4 | Mo rong tong quan FAR research (them bieu do so sanh) | +3 |
| CH2 §2.3 | Them chi tiet cong thuc, vidu tinh toan sliding window | +3 |
| CH2 §2.4 | Them phep tinh day du cho 30 dac trung (bang mo ta chi tiet) | +4 |
| CH3 §3.2 | Phan tich sau per-class results, them discussion | +3 |
| CH3 §3.4/3.5 | Them bang so sanh toan dien voi literature | +3 |
| Them figure | `nhan_dang_hanh_dong.png`, `ml_on_mcu.PNG`, `graph_linh_cuu_hoa.png`, `loai_hinh_xay_ra_chay.pdf` | +3 |
| Tai lieu tham khao | Hien tai ~45 entries, them 10-15 entries tu Ref Docs | +2 |

**Tong co the tang them:** ~25 trang → 65-66 trang

---

## Loi ton tai (sau bien dich cuoi)

| Ma loi | Mo ta | Muc do | Bien phap |
|---|---|---|---|
| PDF incompat | `nguyen_nhan_chan_thuong.pdf` khong tuong thich PDF version | Thap (warning, hien thi duoc) | Chuyen sang PNG hoac re-export PDF |
| File lon | `demo_realtime.png` 20 MB | Cao (giam toc do bien dich) | Nen xuong <3 MB |
| Font size 13 | OT1/cmr khong support size 13 chinh xac | Rat thap (ignored) | Khong can xu ly, LaTeX tu xu ly |

---

## Cay file hien tai

```
baocaochuachay/
├── main.tex           (tao moi - khung chinh RFAR)
├── main.pdf           (41 trang - 33.4 MB)  <-- KET QUA
├── main.log
├── main.aux
├── main.bbl
├── references.bib     (hop nhat 60+ entries)
├── references_sensors.bib  (giu de tham khao)
├── 00_status_scan.md
├── 01_outline_mapping.md
├── 02_build_notes.md  (file nay)
├── Chapters/
│   ├── abstract.tex          (VIET MOI - TOM TAT)
│   ├── abbreviations.tex     (VIET MOI - 51 tu viet tat)
│   ├── literature_review.tex (VIET MOI - CHUONG 1)
│   ├── materials_and_methods.tex (VIET MOI - CHUONG 2)
│   ├── results_and_discussion.tex (VIET MOI - CHUONG 3)
│   ├── conclusion.tex        (VIET MOI - KET LUAN)
│   └── [cac file cu tu template - KHONG DUNG]
└── Figure/
    └── [10+ hinh PNG/PDF da copy va doi ten]
```
