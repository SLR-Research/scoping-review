# Modul 6: Full-text Screening untuk Scoping Review (Claude Cowork)

> **🎯 Output Modul Ini:** Final list sumber yang INCLUDE setelah konfirmasi via full-text, siap untuk charting di Modul 7.

> **🤝 Workflow Modul Ini:** Dieksekusi peserta menggunakan **Claude cowork** (Claude desktop dengan akses langsung ke folder PDF + spreadsheet di komputer peserta). Claude membaca file langsung dari folder, mengupdate spreadsheet, dan mengelola batch tanpa peserta perlu copy-paste.

---

## **LANGKAH 0: SETUP CLAUDE COWORK (SEKALI DI AWAL)**

### **0.1 Struktur Folder Target:**

```
ScR_Project/
├── pdfs/                    ← semua full-text PDF (kosong dulu, diisi di L1)
├── screening.xlsx            ← spreadsheet dari Modul 4 L3
├── pcc_definitions.md        ← PCC + WHAT COUNTS/DOESN'T (Modul 2 L3)
├── reason_codes.md           ← 10 reason codes ScR (Modul 4 L3)
└── briefing.md               ← screener briefing (Modul 5 L1)
```

> **📁 Catatan Nama Folder:** `ScR_Project/` hanya **contoh**. Peserta bebas menggunakan nama folder lain yang sesuai dengan project — mis. `MyScR_GenAI_Education/`, `Tinjauan_Lingkup_2026/`, `[NamaTopik]_ScR/`. Penting: konsisten gunakan nama yang sama di semua prompt cowork sepanjang modul. Jika peserta sudah punya folder kerja existing (mis. di OneDrive/Google Drive), bisa pakai folder tsb — cukup ganti `ScR_Project/` di prompt-prompt berikutnya dengan nama folder peserta.

### **0.2 Setup Folder + Brief Awal (Single Prompt Cowork):**

```
Setup folder kerja Scoping Review + brief context untuk Modul 6 (full-text
screening). Eksekusi dua hal sekaligus:

=== BAGIAN A: SETUP STRUKTUR FOLDER ===

1. CREATE folder utama: ScR_Project/ di [path target, mis. ~/Documents/]
   - Gunakan mkdir/filesystem create. Jika folder sudah ada, konfirmasi
     dulu sebelum overwrite.

2. CREATE sub-folder kosong: ScR_Project/pdfs/

3. MOVE file: pindahkan screening.xlsx dari [path asal] ke
   ScR_Project/screening.xlsx

4. CREATE 3 file rujukan di ScR_Project/ dengan isi yang saya paste:

   File 1: pcc_definitions.md
   ---
   [Paste PCC + WHAT COUNTS/DOESN'T/EDGE CASES dari Modul 2 L3]
   ---

   File 2: reason_codes.md
   ---
   [Paste 10 reason codes ScR + deskripsi dari Modul 4 L3]
   ---

   File 3: briefing.md
   ---
   [Paste screener briefing dari Modul 5 L1, decision tree, prinsip
   "when in doubt, INCLUDE"]
   ---

5. VERIFY struktur akhir (ls/dir ScR_Project/), konfirmasi sesuai 0.1.

=== BAGIAN B: BRIEF AWAL CONTEXT ===

Setelah folder siap, simpan context berikut untuk seluruh sesi Modul 6:

- Folder kerja: ScR_Project/
- Tugas: full-text screening untuk Scoping Review (JBI + PRISMA-ScR)
- File rujukan: pcc_definitions.md, reason_codes.md, briefing.md
- Spreadsheet: screening.xlsx
- PDF source: folder pdfs/
- Prinsip ScR: when in doubt, INCLUDE/UNCERTAIN
- TIDAK ADA exclusion karena quality
- Output format default: tabel ringkas, no preamble, no narasi panjang
- Bahasa: Indonesia

Konfirmasi: setup folder selesai + context siap untuk eksekusi L1-L3.
No preamble.
```

> **💡 Alternatif:** Jika file-file sudah ada terpisah, cukup minta cowork **konsolidasi** ke `ScR_Project/` dengan menyebut path masing-masing file di Bagian A.

> **💡 Manfaat single prompt:** Cowork buat folder + simpan context dalam 1 sesi. Tidak perlu 2 round-trip prompt — peserta langsung bisa lanjut ke L1 setelah konfirmasi.

---

## **LANGKAH 1: AKUISISI FULL-TEXT**

### **1.1 Cek Status PDF yang Sudah Dimiliki:**

Sebelum mulai, peserta cek folder `pdfs/`:
- Jika sebagian/seluruh PDF sudah ada → lompat ke 1.3 (file naming + tracking)
- Jika belum ada PDF sama sekali → lanjut ke 1.2 (auto-download via cowork)

### **1.2 Auto-Download PDF via Claude Cowork (jika peserta belum punya):**

Claude cowork dengan web access dapat membantu download batch PDF dari hasil title/abstract screening.

**Prompt cowork:**

```
Saya belum punya full-text PDF dari hasil Modul 5.
Daftar INCLUDE + UNCERTAIN ada di screening.xlsx (kolom Final_Decision +
DOI/URL).

Tolong:
1. Baca screening.xlsx, ambil records dengan Final_Decision IN (INCLUDE,
   UNCERTAIN) dan Full_Text_Retrieved=PENDING
2. Buat folder pdfs/ jika belum ada
3. Untuk setiap record, coba download PDF berurutan:
   a. PEER-REVIEWED:
      - Cek Open Access via Unpaywall API (https://api.unpaywall.org/v2/[DOI])
      - Jika OA: download dari URL yang dikembalikan
      - Jika tidak OA: cek arXiv/SSRN/OSF preprint via DOI
      - Jika tidak ditemukan: tandai NEED_INSTITUTIONAL
   b. GREY LITERATURE:
      - Akses URL dari kolom DOI/URL langsung
      - Jika URL aktif: download
      - Jika URL mati: coba Wayback Machine
        (https://web.archive.org/web/[URL])
      - Jika tetap gagal: tandai NEED_MANUAL
4. Simpan PDF dengan naming: SCR[ID]_[FirstAuthor/Org]_[Year].pdf
   di folder pdfs/
5. Update screening.xlsx:
   - Full_Text_Retrieved: YES / NEED_INSTITUTIONAL / NEED_MANUAL /
     INACCESSIBLE
   - Full_Text_Location: path file (untuk YES)
   - Acquisition_Source: OA / preprint / grey_direct / wayback
   - Acquisition_Date: hari ini

Output ringkas: jumlah berhasil download per kategori + daftar
NEED_INSTITUTIONAL dan NEED_MANUAL untuk peserta tindak lanjut.

No preamble.
```

> **⚠️ ETIKA & LEGAL:** Hanya download dari sumber legal — Open Access (Unpaywall, DOAJ, PMC), preprint platform, situs lembaga publik, repositori institusional. **JANGAN** akses Sci-Hub atau sumber pirated. Jika peserta punya akses institusional (login VPN/proxy), Claude tidak boleh otomatisasi login — peserta harus download manual via library portal.

### **1.3 Tindak Lanjut untuk PDF yang Belum Berhasil:**

Untuk records dengan status:
- **NEED_INSTITUTIONAL** → peserta login library institusi, download manual, letakkan di `pdfs/`, update spreadsheet
- **NEED_MANUAL** → peserta coba ResearchGate, email author/organization, ILL
- **INACCESSIBLE** → setelah ≥3 channel dicoba, tandai final INACCESSIBLE

Setelah peserta tambah PDF manual, prompt cowork lagi:

```
Update screening.xlsx untuk PDF baru yang sudah saya tambahkan ke folder
pdfs/. Set Full_Text_Retrieved=YES + Full_Text_Location + Acquisition_Source
sesuai sumber.
```

### **1.4 Prioritas Acquisition (jika resource terbatas):**

Urutan dari Modul 5 priority list:
1. **HIGH priority** dulu — auto-download OA + manual untuk yang tidak OA
2. **MEDIUM priority** — proses paralel
3. **LOW (UNCERTAIN)** — semua channel
4. **Inaccessible** — dokumentasikan untuk Limitations

### **File Naming Convention:**

`SCR[ID]_[FirstAuthor/Org]_[Year].pdf` — mis. `SCR042_WHO_2023.pdf`

> **💡 Tips:** Inaccessible rate target <15%. Untuk grey lit, 20-30% inaccessible masih wajar — dokumentasikan di Limitations. Auto-download via cowork biasanya berhasil untuk 40-60% records (mostly OA peer + grey lit URL aktif), sisanya butuh tindak lanjut manual.

---

## **LANGKAH 2: FULL-TEXT SCREENING (DUAL-REVIEWER + COWORK)**

### **Workflow Dual-Reviewer:**

Cowork = sesi Claude masing-masing peserta di komputer sendiri.
- **Reviewer 1** jalankan cowork di komputernya → isi kolom `Screener_1_*` di spreadsheet shared (Google Sheets / OneDrive)
- **Reviewer 2** jalankan cowork di komputernya → isi kolom `Screener_2_*`
- Keduanya kerja independen, tidak saling melihat
- Spreadsheet di-sync via cloud, kappa auto-calculate

### **Reason Codes (10 total — sudah ada di `reason_codes.md`):**

Standar Modul 4 + tambahan full-text stage:
- **METHODS-UNCLEAR** — substansi tidak cukup untuk klasifikasi PCC
- **DUPLICATE-POSTHOC** — overlap konten dengan sumber lain yang sudah included

> **⚠️ PENTING:** TIDAK ADA exclusion karena quality (prinsip JBI ScR).

### **Prompt Cowork (Singkat — context sudah di-brief di Langkah 0):**

```
Screen 10 PDF berikutnya dari folder pdfs/ yang Full_Text_Retrieved=YES dan
Screener_1_Decision masih kosong. Cross-check ke pcc_definitions.md.

Output tabel saja, no preamble:

| ID | Doc_Type | Concept Match | Context Match | Recommend | Reason Code | Confidence |
```

> **💡 Token-efficient:** Prompt 2-3 baris cukup. Claude akses file langsung, tidak perlu Anda paste konten PDF.

### **Alur Decision per Reviewer:**

1. Baca tabel rekomendasi Claude
2. **Spot-check** kutipan ke PDF asli (Claude bisa hallucinate — buka PDF di viewer terpisah)
3. Minta Claude update spreadsheet:
```
Update screening.xlsx untuk 10 record tadi: isi Screener_1_Decision +
Screener_1_Reason_Code + Screener_1_Notes sesuai keputusan saya:
[ID 1: INCLUDE, ID 2: EXCLUDE C-CONTEXT-NOMATCH, ...]
```
4. Lanjut batch berikutnya

### **Resolve Disagreements (Sesi Bersama):**

Setelah keduanya selesai, peserta meeting + Claude cowork bersama:

```
Tampilkan DISAGREE cases dari screening.xlsx (Screener_1 != Screener_2).
Untuk setiap, berikan analisis singkat (1-2 kalimat) + saran resolusi.
Prinsip ScR: when in doubt, INCLUDE.
```

Reviewer diskusi → consensus → Claude update `Conflict_Resolution`.

---

## **LANGKAH 3: FINALISASI + CHARTING PREP**

### **Prompt Cowork (Aggregate):**

```
Aggregate hasil screening dari screening.xlsx.

Output ringkas:

1. PRISMA-ScR FLOW NUMBERS:
   - Sought / Inaccessible / Assessed / Excluded / INCLUDED FINAL
   - Breakdown reason codes

2. KAPPA REPORT: full-text kappa + N disagreements resolved

3. INACCESSIBLE IMPACT (1 paragraf untuk Limitations)

4. CHARTING READINESS CHECKLIST

Update juga Sheet PRISMA-ScR Flow Tracker. No preamble.
```

---

## **HASIL AKHIR**

```
=== FULL-TEXT SCREENING SUMMARY (ScR) ===

ACQUISITION:
- HIGH/MEDIUM/LOW retrieved: [breakdown]
- Inaccessible: [N] ([%]) — peer: X, grey: Y

SCREENING:
- Total assessed: [N]
- Full-text kappa: [X]
- INCLUDED FINAL: [N] (peer: X, grey: Y)
- EXCLUDED: [N] + reason code breakdown

PRISMA-ScR FLOW UPDATE:
- Identification → Screening → Eligibility → Included [angka]

INACCESSIBLE IMPACT: [paragraf 2-3 kalimat untuk Limitations]

FORWARD ARTIFACTS (→ Modul 7):
- Final INCLUDED list di screening.xlsx (kolom Final_Decision=INCLUDE)
- PDF paths di folder pdfs/
- pcc_definitions.md re-use untuk Modul 7 charting

NEXT: Data Charting (Modul 7) — lanjut di sesi cowork sama,
tambah file charting_form.md di folder ScR_Project/.
```

---

## **TROUBLESHOOTING**

**1. Inaccessible rate >15%**
- Coba ILL, ResearchGate, email author/organization
- Untuk grey lit URL mati: cek **Wayback Machine** (web.archive.org)
- Dokumentasikan di Limitations dengan karakterisasi (skewed/random)

**2. Tergoda exclude karena quality**
- **JANGAN.** ScR tidak exclude atas dasar kualitas (JBI Manual)
- Exception: paper benar-benar tanpa substansi → METHODS-UNCLEAR
- Quality assessment opsional di Modul 7, deskriptif

**3. PDF tidak terbaca Claude (scan buruk)**
- OCR dulu: `pdftoppm + tesseract` atau Adobe Acrobat OCR
- Untuk grey lit image-based: OCR wajib sebelum letakkan di pdfs/
- Jika tetap gagal: tandai INACCESSIBLE

**4. Auto-download via cowork berhasil sedikit (<30%)**
- Wajar jika topik dominan paywall / non-OA — tindak lanjut manual via library
- Cek apakah DOI/URL di screening.xlsx valid (kadang error format)
- Untuk grey lit: cek apakah situs lembaga sudah pindah URL (Wayback dulu)
- Pertimbangkan registrasi Unpaywall API key untuk akses lebih cepat

**5. Token cowork cepat habis**
- Brief context **sekali** di Langkah 0, jangan ulang setiap prompt
- Prompt singkat 2-3 baris (Claude sudah punya akses file)
- Batch 5-10 PDF sekaligus, bukan 1-1
- Hindari instruksi "pikirkan secara mendalam" — langsung minta tugas

**6. Spreadsheet sync conflict (Reviewer 1 + 2 edit bersamaan)**
- Pakai Google Sheets (auto-merge) bukan Excel desktop
- Atau: bagi range row per reviewer (R1: SCR001-100, R2: SCR101-200) sementara
- Final merge: copy kolom Screener_2_* dari spreadsheet R2 ke spreadsheet R1
