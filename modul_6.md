# Modul 6: Full-text Acquisition dan Screening untuk Scoping Review

---

## **LANGKAH 1: ACQUISITION STRATEGY + PRIORITY-BASED TRACKING**

> **🎯 Tujuan:** Dapatkan full-text (peer-reviewed) + full report (grey literature) berdasarkan prioritas dari Modul 5 L4. Jangan acquire "semua dulu baru screening" — proses sekuensial dari HIGH → MEDIUM → LOW menghemat waktu. Untuk ScR, grey lit butuh strategi acquisition berbeda dari peer-reviewed.

### **Prompt untuk Claude:**
```
Saya memiliki [N] sumber yang lolos title/abstract screening untuk full-text review
(Scoping Review — JBI + PRISMA-ScR).

Dari Modul 5 L4, sudah diprioritaskan:
- HIGH priority: [N] (peer: [N], grey: [N]) — clearly match PCC
- MEDIUM priority: [N] (peer: [N], grey: [N]) — match sebagian, butuh verify
- LOW priority (UNCERTAIN): [N] (peer: [N], grey: [N]) — deferred untuk disambiguate

Date of search (Modul 3 L4): [YYYY-MM-DD per sumber]

Tolong bantu develop acquisition strategy DUAL-TRACK:

=== 1. ACCESSIBILITY ASSESSMENT ===

TRACK A — Peer-Reviewed:
- Institutional access (library subscription)
- Open access (DOAJ, PMC, preprint servers)
- Author request (ResearchGate, email)
- Inaccessible

TRACK B — Grey Literature:
- Direct URL (dari hasil search Modul 3)
- Website lembaga (WHO, Bappenas, UNESCO, dsb)
- Repositori tesis (ProQuest login, institusional repo)
- Wayback Machine / Internet Archive (jika URL asli mati)
- Author/organization direct request
- Inaccessible

Use web search jika perlu cek open access status atau URL yang masih aktif.

=== 2. PROCUREMENT SEQUENCE ===

Urutan pengerjaan (dual-track):
1. HIGH priority peer-reviewed OA → dapatkan semua dulu (cepat)
2. HIGH priority peer-reviewed institutional → login library
3. HIGH priority grey lit via direct URL → akses website
4. MEDIUM priority (peer + grey) secara paralel
5. LOW priority (UNCERTAIN) → semua channel
6. Author/organization request untuk yang masih inaccessible

=== 3. INACCESSIBLE PROTOCOL ===

Tetapkan threshold eksplisit (untuk dokumentasi Methods & Limitations):
- Jika inaccessible rate <5% → dokumentasi standar di Limitations, low impact
- Jika inaccessible rate 5-15% → dokumentasi detail + analisis potensi bias
  (apakah inaccessible skewed ke grey lit / region / tahun tertentu?)
- Jika inaccessible rate >15% → REVISI strategi:
  * Tambah channel (inter-library loan, Wayback Machine untuk grey lit)
  * Konsultasi librarian untuk peer-reviewed
  * Untuk grey lit: coba kontak langsung organisasi penerbit
  * Konsultasi supervisor: lanjut dengan caveat, atau scope revision?

CATATAN ScR: grey lit cenderung lebih rentan inaccessible (URL mati, laporan
tidak lagi dipublikasikan). Jika inaccessible rate untuk grey lit >25%, ini
sering diterima sebagai keterbatasan standar ScR — dokumentasikan transparan.

=== 4. TRACKING INTEGRATION ===

Update kolom di spreadsheet Modul 4 L3:
- Full_Text_Retrieved: YES / NO / PENDING / INACCESSIBLE
- Full_Text_Location: filepath/URL (mis. "/fulltext/SCR042_Smith_2022.pdf")
- Acquisition_Date: YYYY-MM-DD
- Acquisition_Source: institutional / OA / author_request / ILL /
                     grey_direct / wayback / org_request

=== 5. FILE NAMING CONVENTION ===
Standardisasi: `SCR[ID]_[FirstAuthor/Org]_[Year].pdf`
Contoh peer: `SCR042_Hariri_2023.pdf`
Contoh grey: `SCR101_WHO_2024.pdf` atau `SCR115_Bappenas_2023.pdf`

Ini memudahkan batch upload ke Claude di Langkah 2.

Output: acquisition workplan dengan timeline realistis (dual-track).
```

> **💡 Tips Claude:** Untuk ScR, jangan shortcut grey lit acquisition — kalau 30% grey lit tidak ter-acquire, Methods & Limitations section akan menanggung beban argumentasi berat. Gunakan **Wayback Machine (archive.org)** sebagai safety net untuk URL grey lit yang sudah mati — sering berhasil untuk laporan lembaga yang di-de-publikasi.

**Target L1:** semua HIGH priority ter-acquire, ≥80% MEDIUM, jalur jelas untuk LOW priority, dan dokumentasi eksplisit untuk grey lit inaccessible.

---

## **LANGKAH 2: FULL-TEXT SCREENING (DUAL-REVIEW + AI-ASSISTED)**

> **🎯 Tujuan:** Konfirmasi INCLUDE/EXCLUDE berbasis full-text/full-report, bukan hanya abstract. Kappa pada full-text stage sering lebih tinggi dari abstract (info lebih lengkap) — tetap wajib dihitung. Untuk ScR, tidak ada eksklusi karena kualitas di tahap ini (QA opsional, non-exclusionary).

### **Workflow per Reviewer (mirror Modul 5 L3):**

Setiap reviewer menjalankan alur:
1. Baca full-text/full-report PDF dengan bantuan Claude (dual-perspective)
2. Bandingkan dengan operational definitions PCC dari Modul 2 L3
3. Decide INCLUDE/EXCLUDE + Reason_Code (BUKAN berdasarkan kualitas)
4. Catat di kolom Screener_[1/2]_Decision di spreadsheet

### **Reason Codes Full-Text Stage (ScR):**

Gunakan 9 reason codes ScR dari Modul 4 L3, **ditambah 3 codes khusus full-text**:

| Code | Keterangan |
|---|---|
| P-NOMATCH | Population tidak sesuai (jika applicable, konfirmasi dari full-text) |
| C-CONCEPT-NOMATCH | Concept tidak sesuai operational def (konfirmasi dari full-text) |
| C-CONTEXT-NOMATCH | Context tidak sesuai (konfirmasi dari full-text) |
| STUDY-DESIGN | Tipe sumber di luar kriteria |
| LANGUAGE | Bahasa full-text berbeda dari abstract filter |
| DUPLICATE | Duplikat (post-hoc detected — mis. same dataset, different venue) |
| NO-ABSTRACT | (jarang di full-text stage) |
| INACCESSIBLE | Full-text tidak dapat diakses |
| **METHODS-UNCLEAR** | Full-text tidak cukup deskripsi untuk kualifikasi PCC |
| **NO-SUBSTANTIVE-CONTENT** | Konseptual paper tanpa substansi yang bisa di-chart (mis. editorial pendek, commentary) |
| **DUPLICATE-POSTHOC** | Overlap dataset/konten dengan sumber lain yang sudah included |
| OTHER | (wajib catat di Notes) |

**CATATAN KRUSIAL ScR:** TIDAK ADA kode "POOR-QUALITY" untuk eksklusi (ini berbeda dari SLR). JBI eksplisit: kualitas tidak basis eksklusi untuk ScR. Jika QA dilakukan di Modul 7, itu deskriptif untuk peta bukti, bukan exclusionary.

### **AI-Assisted Full-Text Screening dengan Claude:**

> **🚀 Fitur Claude:** Upload PDF langsung — Claude membaca full-text utuh tanpa Anda perlu copy-paste.

```
[Upload PDF: SCR[ID]_[Author/Org]_[Year].pdf]

STUDY ID: [SCR042]
Source_Type: [PEER / GREY]
Document_Type: [Article / Conference / Thesis / Report / Policy Brief / Preprint]
Priority tier dari Modul 5: [HIGH/MEDIUM/LOW]
Decision abstract-level di Modul 5: [INCLUDE / UNCERTAIN]

Operational definitions PCC (dari Modul 2 L3):
- P WHAT COUNTS: [...] (atau N/A)
- C (Concept) WHAT COUNTS: [...]
- C (Context) WHAT COUNTS: [...]

Reason codes yang tersedia: [12 codes lengkap ScR]

Tolong baca full-text dan berikan DUAL PERSPECTIVE (bukan keputusan final):

=== 1. DOCUMENT TYPE CONFIRMATION ===
- Actual type (dari isi dokumen): [article/report/policy brief/thesis/preprint]
- Konsisten dengan metadata? [YES/NO + penjelasan]
- Substantive content (untuk bisa di-chart di Modul 7)? [YES/NO]

=== 2. POPULATION VERIFICATION (jika applicable) ===
- Detail partisipan (jika empiris) atau karakterisasi target (jika konseptual)
- Match WHAT COUNTS? Kutip kalimat pendukung
- Match WHAT DOESN'T? (jika iya, paper ini EXCLUDE)

=== 3. CONCEPT VERIFICATION (INTI ScR) ===
- Bagaimana Concept di-konseptualisasikan/operasionalisasikan di sumber ini?
- Match WHAT COUNTS operational def? Kutip
- Apakah sumber ini akan menambah "peta" Concept (bukan duplikasi)?

=== 4. CONTEXT VERIFICATION ===
- Konteks spesifik yang dilaporkan (geografis, setting, kultural, kebijakan)
- Match WHAT COUNTS Context? Kutip

=== 5. CHARTING READINESS ===
Preview untuk Modul 7 (Data Charting):
- Informasi yang bisa di-chart: [study design, population chars, concept
  operationalization, context details, key findings, gaps mentioned]
- Missing info yang akan sulit di-chart: [...]
- Untuk grey lit: apakah struktur dokumen memungkinkan charting sistematis?

=== 6. DUAL PERSPECTIVE (untuk reviewer decision) ===

INCLUSIVE-SCR (default INCLUDE saat ragu, prinsip mapping luas):
- Argumen INCLUDE: [...]
- Justifikasi via WHAT COUNTS PCC: [...]
- Kontribusi untuk mapping: [...]
- Kutipan mendukung: [...]

RESTRICTIVE (default EXCLUDE saat ragu):
- Argumen EXCLUDE: [...]
- Reason code yang tepat: [...]
- Kutipan mendukung: [...]

=== 7. RECOMMENDATION (bukan keputusan) ===
- INCLUDE / EXCLUDE dengan alasan utama
- Reason code yang tepat (dari 12 ScR codes)
- Confidence: HIGH / MEDIUM / LOW
- Missing info yang critical (jika UNCERTAIN tetap)
- CATATAN: Jangan EXCLUDE karena quality — ScR tidak exclude atas dasar kualitas

Output untuk reviewer decide.
```

### **Alur Human Decision (sama seperti Modul 5):**

1. Baca Claude's full-text analysis
2. **Spot-check kutipan** — buka PDF, verifikasi kutipan akurat (Claude bisa hallucinate)
3. Isi kolom Screener_[X]_Decision + Reason_Code + Notes
4. Untuk kasus UNCERTAIN dari Modul 5 yang sekarang sudah bisa di-decide → isi sebagai final decision

### **Batch Processing (untuk efisiensi):**

```
[Upload beberapa PDF sekaligus: SCR001.pdf, SCR002.pdf, ...]

Saya upload [N] PDF batch untuk full-text screening ScR.
Operational definitions PCC + reason codes ScR: [sama seperti sebelumnya]

Untuk SETIAP PDF, berikan analisis ringkas format tabel:

| ID | Source_Type | Doc_Type | Concept Match | Context Match | Charting Ready | Inclusive | Restrictive | Recommend | Reason | Confidence |

Di akhir, highlight 3-5 sumber yang paling butuh attention manual (UNCERTAIN,
LOW confidence, atau charting readiness issues).
```

### **Kedua Reviewer Bekerja Independently:**

- Reviewer 1 isi Screener_1_* untuk full-text stage
- Reviewer 2 isi Screener_2_* (TIDAK melihat Reviewer 1)
- Kappa full-text stage auto-calculated di Sheet Kappa_Calculation

---

## **LANGKAH 3: RESOLVE CONFLICTS + FINAL PCC AUDIT + CHARTING PREP**

### **3.1 Resolve Disagreements Full-Text:**

```
Hasil dual-review full-text:
- Total screened: [N]
- Agreement: [N] ([%])
- Disagreements: [N] ([%])
- Full-text kappa: [X]
- Sub-kappa peer vs grey: [X / Y]

[Paste tabel disagreement cases]

Analisis dan strategi resolusi:

1. PATTERN:
   - Apakah disagreement terkonsentrasi di tier tertentu (LOW priority)?
   - Apakah di komponen PCC tertentu (Concept vs Context)?
   - Apakah di Source_Type tertentu (grey lit lebih sering DISAGREE)?
   - Apakah ada confusion antar reason codes yang mirip (METHODS-UNCLEAR vs
     NO-SUBSTANTIVE-CONTENT)?

2. PER-CASE RESOLUTION:
   Untuk setiap DISAGREE:
   - Reviewer diskusi face-to-face atau via notes
   - Rujuk balik ke operational def PCC + full-text evidence
   - Consensus → update Conflict_Resolution column
   - Ingat: prinsip ScR "when in doubt, INCLUDE" — eksklusi harus well-grounded

3. JIKA PATTERN DISAGREEMENT KONSISTEN:
   - Update operational def di Modul 2 L3 untuk klarifikasi
   - Regenerate Screener Briefing
   - (Tidak perlu re-screen semua — hanya klarifikasi agar Modul 7 tetap konsisten)

Dokumentasikan jumlah disagreement + resolusinya untuk Methods PRISMA-ScR.
```

### **3.2 PCC-Consistency Final Audit:**

```
Ambil RANDOM 15% dari FINAL INCLUDED records (post-full-text).
Proporsional peer vs grey.
Untuk setiap record, cross-check dengan operational definitions PCC:

- Apakah keputusan INCLUDE benar-benar grounded di WHAT COUNTS Concept + Context?
- Reason code (jika EXCLUDE di tier sebelumnya) konsisten?
- Ada "slipped through" yang seharusnya EXCLUDE?
- Apakah ada INCLUDED yang sebenarnya NO-SUBSTANTIVE-CONTENT (tidak bisa di-chart)?

Jika audit menemukan issue pada X records:
- Jika X ≤ 5%: acceptable, dokumentasi di Limitations
- Jika X > 5%: RE-SCREEN seluruh batch oleh Reviewer 3 atau re-do pass 2

Output: audit report + daftar flagged records (jika ada).
```

### **3.3 Inaccessible Studies Impact Assessment (ScR-specific):**

```
Dari Langkah 1, saya memiliki [N] inaccessible sumber.
Inaccessible rate total: [%]
Breakdown:
- Peer-reviewed inaccessible: [%]
- Grey lit inaccessible: [%]

Analisis impact (ScR-specific):

1. Karakteristik inaccessible sumber:
   - Apakah skewed ke Source_Type tertentu? (grey lit biasanya lebih rentan)
   - Apakah skewed ke region tertentu?
   - Apakah skewed ke tahun tertentu? (URL lama mati)
   - Apakah skewed ke Document_Type tertentu?

2. Potensi bias untuk mapping:
   - Jika skewed → potential systematic bias di peta bukti
   - Jika random → less concern tapi tetap dokumentasi
   - ScR-specific: apakah inaccessible mengurangi coverage untuk gap identification?

3. Mitigation disclosure (untuk Methods & Limitations PRISMA-ScR):
   - Template kalimat: "[N] sources ([%]) were inaccessible despite [strategi
     yang dicoba — library, ILL, Wayback, author/org request]. These were
     [karakterisasi]. This may introduce [jenis bias] but we estimate the
     impact on the mapping is [low/moderate/high] because [alasan]."

Output: paragraf siap-Limitations tentang inaccessible sumber.
```

### **3.4 Charting Readiness Checklist:**

```
Sebelum commit ke Modul 7 (Data Charting), validasi:

CHECKLIST (ScR-specific):
[ ] Final INCLUDED list finalized (jumlah + daftar ID, breakdown peer vs grey)
[ ] Semua DISAGREE di-resolve (Conflict_Resolution column filled)
[ ] Semua UNCERTAIN dari Modul 5 sudah di-decide via full-text
[ ] Full-text kappa calculated dan didokumentasi (+ sub-kappa peer/grey)
[ ] Exclusion reasons table (full-text stage) compiled
[ ] PCC-consistency audit completed
[ ] Inaccessible sumber dokumentasi ready
[ ] Full-text PDFs tersimpan dengan naming convention konsisten (SCR[ID]_*)
[ ] Spreadsheet kolom Full_Text_Location filled dengan path akurat
[ ] PRISMA-ScR flow diagram tracker updated (Modul 4 L3 Sheet 4)
[ ] TIDAK ADA exclusion karena quality (prinsip ScR)

Jika semua ceklis → PROCEED to Modul 7.
Jika ada yang kosong → selesaikan dulu.
```

---

## **HASIL AKHIR**

### **Full-text Screening Summary ScR (v1):**
```
=== FULL-TEXT SCREENING RESULTS (ScR) ===

ACQUISITION:
- Target sources (dari Modul 5): [N]
- Breakdown by priority:
  · HIGH: [N] acquired / [N] target (peer: [N], grey: [N])
  · MEDIUM: [N] acquired / [N] target
  · LOW (UNCERTAIN): [N] acquired / [N] target
- Inaccessible total: [N] ([%])
  · Peer-reviewed inaccessible: [N]
  · Grey lit inaccessible: [N]
- Methods used: [institutional / OA / author request / ILL / grey_direct /
                 wayback / org_request]

FULL-TEXT SCREENING:
- Total screened: [N]
- Screener_1 + Screener_2 complete: ✓
- Full-text kappa: [X]
- Sub-kappa peer: [X] / Sub-kappa grey: [X]
- Disagreements: [N]
- Resolved via discussion: [N]

DECISIONS:
- FINAL INCLUDED: [N] sumber
  · Peer-reviewed: [N]
  · Grey lit: [N]
- EXCLUDED at full-text: [N]

EXCLUSION REASONS TABLE (full-text stage → Methods appendix PRISMA-ScR):
| Reason Code | Count | % |
| P-NOMATCH | X | Y% |
| C-CONCEPT-NOMATCH | X | Y% |
| C-CONTEXT-NOMATCH | X | Y% |
| STUDY-DESIGN | X | Y% |
| METHODS-UNCLEAR | X | Y% |
| NO-SUBSTANTIVE-CONTENT | X | Y% |
| DUPLICATE-POSTHOC | X | Y% |
| LANGUAGE | X | Y% |
| INACCESSIBLE | X | Y% |
| OTHER | X | Y% |

(Catatan: TIDAK ADA exclusion karena POOR-QUALITY — prinsip ScR)

RESOLVED UNCERTAIN (dari Modul 5):
- Total UNCERTAIN deferred from Modul 5: [N]
- Resolved as INCLUDE at full-text: [N]
- Resolved as EXCLUDE at full-text: [N]
- Remaining unresolved: [N] (tandai di Notes, dokumentasi di Limitations)

PCC-CONSISTENCY AUDIT:
- Sample size: 15% of INCLUDED (proporsional peer vs grey)
- Issues found: [N]
- Action: [none / flagged / re-screen]

INACCESSIBLE STUDIES IMPACT:
- Rate: [%]
- Breakdown peer/grey: [X% / Y%]
- Characterization: [random / skewed ke X]
- Potential bias: [low/moderate/high]
- Limitations paragraph: [drafted]

CHARTING READINESS:
- Checklist: [all ✓ / items pending]

PRISMA-ScR FLOW UPDATE:
- Identification: [total per source]
- Screening: [N screened, N excluded]
- Eligibility: [N assessed full-text, N excluded]
- Included: [N final, peer: [N], grey: [N]]

FORWARD ARTIFACTS (→ Modul 7):
- Final INCLUDED list dengan full-text file paths (peer + grey)
- Document type breakdown
- Charting readiness notes (sumber dengan substantive content terkonfirmasi)
- Canonical terminology (dari Modul 2 L3)
- Operational definitions PCC (dari Modul 2 L3)
- Kappa final: abstract + full-text (+ sub-kappa peer/grey)
```

---

## **TROUBLESHOOTING**

**Problem 1: Inaccessible rate >15% (terutama grey lit)**
- Reach out lewat institutional ILL (inter-library loan) — sering underutilized untuk peer-reviewed
- Untuk grey lit: coba **Wayback Machine (web.archive.org)** — laporan lembaga sering arsip
- Request via ResearchGate atau email langsung author/organization
- Konsultasi dengan librarian institusi
- Untuk ScR, grey lit inaccessible 20-30% masih dapat diterima jika didokumentasi transparan

**Problem 2: Full-text kappa lebih rendah dari abstract kappa**
- Biasanya terjadi karena full-text mengungkap nuansa yang abstract sembunyikan
- Check apakah reason codes baru (METHODS-UNCLEAR, NO-SUBSTANTIVE-CONTENT) jadi sumber disagreement
- Update Screener Briefing dengan decision tree untuk codes tsb
- Re-calibrate via 10 sample tambahan

**Problem 3: Banyak DUPLICATE-POSTHOC discoveries**
- Authors publikasi multiple paper dari dataset/konten yang sama (slicing)
- Untuk ScR, pilih versi yang paling **komprehensif untuk charting** (bukan paling top journal — berbeda dari SLR)
- Catat di Notes: "Excluded due to content overlap with SCR[X]"
- Dokumentasikan jumlah DUPLICATE-POSTHOC di Methods

**Problem 4: Godaan exclude karena quality — JANGAN**
- ScR **TIDAK** mengeksklusi atas dasar kualitas metodologis (JBI Manual explicit)
- Jika Anda tergoda exclude karena "papernya lemah", ingat: ScR memetakan lanskap bukti, termasuk bukti berkualitas rendah
- Jika QA dilakukan di Modul 7, itu deskriptif (mendokumentasikan kualitas dalam peta), bukan basis eksklusi
- Exception: jika paper PURE predatory journal tanpa substance sama sekali → gunakan NO-SUBSTANTIVE-CONTENT (bukan POOR-QUALITY)

**Problem 5: PDF tidak bisa dibaca Claude (scan quality buruk / gambar)**
- OCR dulu dengan tool eksternal (pdftoppm + tesseract, atau Adobe Acrobat OCR)
- Untuk dokumen sangat lama / scan buruk: pertimbangkan manual summary untuk feed ke Claude
- Jika tidak bisa di-decide: tandai sebagai INACCESSIBLE
- Untuk grey lit: banyak laporan lembaga dalam format image-based PDF — OCR wajib

**Problem 6: Disagreement persists meski diskusi**
- Konsultasi reviewer ke-3 (majority vote)
- Jika ke-3 juga split: flag sebagai AMBIGUOUS-CONSENSUS, dokumentasi di Limitations
- Update operational def untuk mencegah kasus serupa

**Problem 7: Grey lit tanpa struktur metodologi jelas**
- Grey lit (laporan, policy brief) sering tidak punya bagian "Methods" formal
- Untuk ScR, ini bukan alasan eksklusi (kualitas bukan basis eksklusi)
- Gunakan METHODS-UNCLEAR hanya jika substansi benar-benar tidak bisa dikategorisasi untuk PCC
- Di Modul 7, charting grey lit boleh lebih longgar — cantumkan "Methods: not reported" sebagai data

**Problem 8: Ragu apakah UNCERTAIN deferred dari Modul 5 benar-benar INCLUDE**
- Prinsip ScR: when in doubt, INCLUDE. Kalau info full-text cukup untuk mapping, INCLUDE.
- Jika full-text confirm bahwa Concept/Context tidak match → EXCLUDE dengan reason code
- Jika full-text masih ambigu tapi ada sinyal relevansi → INCLUDE, tag di Notes "marginal — monitor in charting"

---
