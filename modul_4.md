# Modul 4: Data Mining dan Export untuk Scoping Review

---

## **LANGKAH 1: EKSEKUSI FINAL SEARCH + KONFIRMASI KONSISTENSI**

### **Praktik di Database Peer-Reviewed (Scopus, WoS, dll.):**
1. **Login ke database** dan masuk ke Advanced Search
2. **Input final search string** dari Modul 3 L3 (format PCC)
3. **Apply filters** yang sudah dijustifikasi di Modul 3 L3
4. **Catat total results** + screenshot untuk dokumentasi PRISMA-ScR flow
5. **WAJIB catat tanggal pencarian** (YYYY-MM-DD) per sumber — sesuai Modul 3 L4

### **Praktik di Grey Literature Sources:**
1. **Google Scholar**: jalankan query, screen top-200 hits by title, catat relevan
2. **ProQuest Dissertations**: query, apply filter tahun, export metadata
3. **Website lembaga** (WHO, UNESCO, Bappenas, Kemendikbud): search terms, catat query + tanggal + top-N hits yang diperiksa
4. **Preprint platform** (OSF, arXiv, SSRN): query platform, filter tahun
5. **Dokumentasikan setiap sumber** dalam **Grey Literature Search Log** (jika grey lit digunakan) — diperlukan untuk PRISMA-ScR transparency

### **Sanity Check dengan Claude:**
```
Final search results (semua sumber):

=== PEER-REVIEWED ===
- Scopus: search string [dari Modul 3 L3], total [N], filter [N], tanggal [YYYY-MM-DD]
- WoS: [...]
- [DB lain]: [...]

=== GREY LITERATURE ===
- Google Scholar: query [...], screened top-200, relevan [N], tanggal [...]
- ProQuest: [...]
- WHO/Bappenas/UNESCO: [...]
- OSF/arXiv: [...]

SANITY CHECK — verifikasi kebenaran search sebelum export:

=== 1. PAPER-KUNCI + LAPORAN-KUNCI CHECK ===
Saya akan sebutkan 5-10 sumber yang saya TAHU ada di bidang saya
(paper kunci + laporan lembaga kunci — dari supervisor, prior reading, atau
literature review terdahulu).

Sumber kunci:
1. [Author, Year, Title, DOI/URL jika tahu]
2. [Author, Year, Title, DOI/URL jika tahu]
3. [Laporan WHO / Bappenas / dsb, Year, Title, URL]
4. [...]

Cek apakah sumber-sumber ini muncul di hasil search saya. Saya akan kirim
20-50 judul pertama dari hasil search per sumber untuk Anda verifikasi.

Jika BANYAK sumber kunci TIDAK muncul → search string/filter masih bermasalah.
Tunjukkan pola kegagalan dan sarankan revisi balik ke Modul 3 (langkah
spesifik mana).

=== 2. KONFIRMASI VOLUME (ScR-specific) ===
Berdasarkan scope (Modul 2 L4), apakah jumlah hits reasonable?
Benchmark ScR: 50-500 post-dedup ideal; <30 thin mapping; >1000 pertimbangkan
penyempitan Context.

- Jika >> expected: "trap keyword" terlewat di AVOID list? identifikasi
- Jika << expected: filter terlalu ketat? Concept synonym kurang kaya?
  Jika grey lit DIGUNAKAN, apakah sudah di-explore cukup?
- Distribusi sumber: apakah sehat (tidak didominasi 1 DB)? Jika grey lit
  termasuk scope tetapi peer-reviewed dominan 95%+ → grey lit mungkin
  belum cukup di-search.

=== 3. GO/NO-GO DECISION ===
Berikan konfirmasi eksplisit:
- PROCEED: lanjut ke export
- REVISE: balik ke Modul 3 L[X], ini alasannya
```

> **💡 Tips Claude:** Untuk ScR, sanity check sebaiknya mencakup **paper kunci** dan — jika grey lit Anda gunakan — **laporan/grey lit kunci**. Jika grey lit termasuk dalam scope tetapi tidak dicross-check, Anda berisiko missing mapping di sisi kebijakan/praktik. Jika grey lit tidak digunakan, sanity check fokus ke paper peer-reviewed kunci saja sudah cukup.

**Konfirmasi** sebelum lanjut ke export.

---

## **LANGKAH 2: EXPORT DATA + MULTI-SOURCE DEDUP + PCC-CONSISTENCY PREVIEW**

### **Export Process — Peer-Reviewed Databases:**
1. **Select All** hasil pencarian
2. **Export** dengan format **CSV**
3. **Pilih fields**: Authors, Title, Year, Abstract, Author Keywords, Index Keywords, DOI, Source title, Document Type
4. **Naming convention**: `scopus_[topik-singkat]_[YYYYMMDD].csv`

### **Export Process — Grey Literature:**
Grey lit sering tidak support export CSV. Strategi manual:
1. **Google Scholar**: gunakan Zotero/Publish or Perish untuk harvest metadata top-200 hits, export CSV
2. **ProQuest Dissertations**: built-in export CSV/RIS
3. **Website lembaga**: manual entry ke spreadsheet (kolom: Title, Author/Organization, Year, URL, Type [policy brief/report/white paper], Retrieved date)
4. **OSF/arXiv/SSRN**: export metadata dari platform
5. **Naming convention**: `greylit_[source]_[topik]_[YYYYMMDD].csv`

### **Jika Multi-Sumber (standar untuk ScR):**
Ulangi export untuk setiap sumber — minimal:
- `scopus_[topik]_[YYYYMMDD].csv`
- `wos_[topik]_[YYYYMMDD].csv`
- `greylit_gscholar_[topik]_[YYYYMMDD].csv`
- `greylit_proquest_[topik]_[YYYYMMDD].csv`
- `greylit_institutions_[topik]_[YYYYMMDD].csv` (gabungan laporan WHO/Bappenas/dll)

### **Verifikasi + Multi-Source Dedup + Preview Check dengan Claude:**

> **🚀 Fitur Claude:** Upload file CSV langsung — Claude dapat membaca dan memproses tanpa copy-paste.

```
[Upload file CSV hasil export — peer-reviewed + grey lit]

Saya telah mengupload [N] file CSV dari [list sumber].
Date of search: [YYYY-MM-DD per sumber]
Review type: Scoping Review (JBI + PRISMA-ScR)

Lakukan tiga tugas berurutan:

=== TUGAS 1: BASIC QUALITY AUDIT ===

Untuk setiap file CSV:
1. Verifikasi jumlah total records
2. Identify essential fields yang ada (Authors/Organization, Title, Year,
   Abstract/Summary, DOI/URL, Keywords)
3. Data quality issues (per sumber):
   - Berapa records missing abstract/summary?
   - Berapa records missing keywords?
   - Berapa records missing DOI/URL?
   - Untuk grey lit: apakah Type/Format terdokumentasi (report, policy brief,
     thesis, preprint)?
4. Ringkasan statistik per sumber:
   - Distribusi tahun publikasi
   - Top 5 journal/organization
   - Breakdown document type
   - Peer-reviewed vs grey lit ratio

=== TUGAS 2: MULTI-SOURCE DEDUPLICATION ===

Strategi dedup bertingkat (sama seperti SLR tapi dengan tambahan grey lit):
1. PRIMARY MATCH: DOI (jika tersedia di ≥2 sumber)
2. SECONDARY MATCH: normalized title (lowercase, strip punctuation) + year
3. TERTIARY MATCH: fuzzy title match (>90% similarity) + first author/org
4. GREY LIT SPECIAL: URL match (satu laporan bisa ada di Google Scholar +
   website lembaga)

Output:
- Total records across all sources: [N]
- Unique records after dedup: [N]
- Duplicates detected: [N] dengan breakdown per strategi match
- Records eksklusif per sumber: [breakdown]
- PEER vs GREY breakdown post-dedup: [X peer-reviewed, Y grey lit]
- FLAG records dengan matching ambigu (untuk review manual)

Catatan: untuk ScR, cross-source duplication (peer-reviewed paper yang juga
ada di OSF preprint, misalnya) WAJAR dan perlu dedup, tetapi catat
versi mana yang dipertahankan (prefer peer-reviewed final version, tapi
catat preprint version jika relevan untuk tanggal).

=== TUGAS 3: PCC-CONSISTENCY PREVIEW CHECK ===

Dari output Modul 2 L3:
- Canonical term Concept: [...]
- WHAT COUNTS (Concept): [...]
- WHAT DOESN'T COUNT (Concept): [...]
- Canonical term Context: [...]
- WHAT COUNTS (Context): [...]
- WHAT DOESN'T COUNT (Context): [...]

Ambil SAMPEL ACAK 30 records dari data post-dedup (lebih besar dari SLR
karena ScR lebih heterogen; pastikan sample mencakup peer-reviewed + grey
lit proporsional). Untuk setiap record, baca title + abstract/summary +
keywords, lalu klasifikasi:

- MATCH "WHAT COUNTS" (Concept + Context): jelas memenuhi operational definition
- PARTIAL MATCH: memenuhi Concept tapi tidak Context (atau sebaliknya)
- MATCH "WHAT DOESN'T": jelas termasuk yang harus dieksklusi
- AMBIGU: tidak cukup info untuk memutuskan
- OFF-TOPIC: tidak match sama sekali (noise)

Hitung persentase, sajikan tabel.

INTERPRETASI & REKOMENDASI (ScR tolerance lebih luas):
- MATCH "WHAT COUNTS" + PARTIAL MATCH >70% → search bagus, PROCEED ke L3
- MATCH "WHAT COUNTS" + PARTIAL MATCH 40-70% → acceptable, tapi screening
  workload akan tinggi
- MATCH "WHAT COUNTS" + PARTIAL MATCH <40% → TERLALU BANYAK NOISE, BACK TO
  MODUL 3 L2/L3 (fokus perbaikan: AVOID list, operational definitions PCC)
- MATCH "WHAT DOESN'T" tinggi → AVOID list belum lengkap, tambah trap keywords

CATATAN SCR: tolerance "partial match" lebih longgar daripada SLR karena ScR
bertujuan mapping luas. Jika record cocok Concept tapi Context marginal,
umumnya INCLUDE dengan tag untuk analisis sub-grup di Modul 7-8.

Verdict akhir: PROCEED atau BACK TO MODUL 3.
```

> **💡 Tips Claude:** PCC-consistency preview adalah *early warning system*. Investasi 30-45 menit di sini menghemat 20+ jam screening yang ternyata 70% noise. Jika Claude merekomendasikan BACK TO MODUL 3, ikuti — jangan paksa proceed. Untuk ScR, preview sample harus 30 (bukan 20 seperti SLR) karena heterogenitas sumber lebih tinggi (peer-reviewed + grey lit).

**Lanjutkan** ke Langkah 3 hanya jika preview check lolos.

---

## **LANGKAH 3: SETUP SCREENING DATABASE + INCLUSION CRITERIA EMBEDDED**

### **Prompt untuk Claude:**
```
[Upload file CSV final post-dedup dari Langkah 2 — peer-reviewed + grey lit
terpisah atau gabungan dengan kolom Source_Type]

Dari Modul 2 L3, operational definitions saya:

P (Population): [operational def atau "N/A — conceptual scoping"]
C (Concept):
   Canonical term: [...]
   WHAT COUNTS: [...]
   WHAT DOESN'T COUNT: [...]
   EDGE CASES: [...]
C (Context):
   Canonical term: [...]
   WHAT COUNTS: [...]
   WHAT DOESN'T COUNT: [...]

Tolong buat SCREENING DATABASE (Excel .xlsx) dengan struktur ScR:

=== SHEET 1: "Screening" ===

HEADER META (Row 1-7) — BUKAN kolom kosong, tapi embedded criteria:
Row 1: "Scoping Review — JBI + PRISMA-ScR"
Row 2: "Tanggal pencarian: [YYYY-MM-DD per sumber]"
Row 3: "P Canonical: [term atau N/A]"
Row 4: "C (Concept) Canonical: [term]"
Row 5: "C (Concept) WHAT COUNTS: [...] | WHAT DOESN'T: [...]"
Row 6: "C (Context) WHAT COUNTS: [...] | WHAT DOESN'T: [...]"
Row 7: (kosong — separator)

Embedded criteria ini tampil PERMANEN sebagai referensi saat screener bekerja.

KOLOM DATA (mulai Row 8):

| Kolom | Isi | Keterangan |
|-------|-----|------------|
| ID | SCR001, SCR002, ... | Unique identifier |
| Source | Scopus / WoS / GScholar / ProQuest / WHO / dll | Multi-source tracking |
| Source_Type | PEER / GREY | Untuk PRISMA-ScR flow + sub-analisis |
| Authors/Organization | [auto-fill dari CSV] | Grey lit: organisasi jika tidak ada author |
| Year | [auto-fill] | |
| Title | [auto-fill] | |
| Abstract/Summary | [auto-fill] | Grey lit: executive summary |
| Keywords | [auto-fill] | Boleh kosong untuk grey lit |
| DOI/URL | [auto-fill] | Grey lit: URL sumber |
| Journal/Publisher | [auto-fill] | |
| Document_Type | Article/Review/Conference/Thesis/Report/Policy Brief/Preprint | PRISMA-ScR requires |
| Screener_1_Decision | INCLUDE / EXCLUDE / UNCERTAIN | Kosong untuk diisi |
| Screener_1_Reason_Code | [kode standar — lihat di bawah] | |
| Screener_1_Notes | Catatan bebas | |
| Screener_2_Decision | [sama] | |
| Screener_2_Reason_Code | [sama] | |
| Screener_2_Notes | [sama] | |
| Agreement | Formula: =IF(Screener_1_Decision=Screener_2_Decision,"AGREE","DISAGREE") | Auto |
| Conflict_Resolution | INCLUDE/EXCLUDE setelah diskusi | Hanya jika DISAGREE |
| Final_Decision | INCLUDE / EXCLUDE | Komputasi akhir |
| Full_Text_Retrieved | YES/NO/PENDING | Untuk Modul 6 |
| Full_Text_Location | Filename atau URL | Traceability |

REASON CODES ScR (STANDAR):
- P-NOMATCH: Population tidak sesuai (jika Population applicable)
- C-CONCEPT-NOMATCH: Concept tidak sesuai operational definition
- C-CONTEXT-NOMATCH: Context tidak sesuai (geografis/setting/temporal)
- STUDY-DESIGN: Tipe sumber tidak masuk kriteria (mis. opini, editorial tanpa
  substansi — ingat, ScR boleh inklusif untuk berbagai desain)
- LANGUAGE: Bahasa tidak sesuai filter
- DUPLICATE: Duplikat (lintas-sumber atau internal)
- NO-ABSTRACT: Abstract/summary tidak tersedia, tidak bisa screen
- INACCESSIBLE: Full-text/report tidak dapat diakses (untuk grey lit)
- OTHER: (wajib isi notes)

Reason codes yang distandardisasi jadi fondasi tabel "alasan eksklusi" di
Methods (Modul 9) dan PRISMA-ScR flow diagram.

=== SHEET 2: "Kappa_Calculation" ===

Tabel 2x2 dengan formula Cohen's kappa:

                  Screener_2_INCLUDE    Screener_2_EXCLUDE    Total
Screener_1_INCLUDE        a                  b                a+b
Screener_1_EXCLUDE        c                  d                c+d
Total                    a+c                b+d              N=a+b+c+d

Formula:
- po = (a + d) / N           (observed agreement)
- pa1 = (a+b) / N            (marginal Screener_1 INCLUDE)
- pa2 = (a+c) / N            (marginal Screener_2 INCLUDE)
- pe = pa1*pa2 + (1-pa1)*(1-pa2)   (expected agreement by chance)
- kappa = (po - pe) / (1 - pe)

Interpretasi (Landis & Koch):
- kappa < 0.20: Poor
- 0.21-0.40: Fair
- 0.41-0.60: Moderate
- 0.61-0.80: Substantial (TARGET untuk proceed ScR)
- 0.81-1.00: Almost perfect

Target: kappa ≥ 0.60 setelah kalibrasi di Modul 5 sebelum batch massal.
Catatan: untuk ScR, kappa bisa lebih rendah dari SLR karena kriteria
lebih inklusif dan lebih banyak UNCERTAIN — acceptable asalkan ada prosedur
resolve disagreements yang jelas.

=== SHEET 3: "Summary" ===

Auto-calculated:
- Total records: [N]
- Source breakdown: peer-reviewed [X], grey lit [Y]
- Year distribution
- Document type breakdown
- Screening progress (Screener_1 done / total; Screener_2 done / total)
- Agreement rate
- Current kappa
- Final INCLUDE count (dengan breakdown peer vs grey)

=== SHEET 4: "PRISMA-ScR Flow Tracker" ===

Tabel untuk tracking flow diagram PRISMA-ScR 2018:

IDENTIFICATION:
- Records identified from databases: [N total + breakdown per DB]
- Records identified from other sources (grey lit): [N breakdown per source]
- Records removed before screening (duplicates, ineligible): [N]

SCREENING:
- Records screened (title/abstract): [N]
- Records excluded at title/abstract: [N + breakdown reasons]

ELIGIBILITY:
- Reports sought for retrieval: [N]
- Reports not retrieved: [N + reasons]
- Reports assessed for eligibility (full-text): [N]
- Reports excluded (full-text): [N + breakdown reasons]

INCLUDED:
- Sources included in review: [N + breakdown peer vs grey]

=== AUTO-FILL ===
Dari CSV post-dedup yang di-upload, populasi kolom Authors/Organization,
Year, Title, Abstract, Keywords, DOI/URL, Journal/Publisher, Document_Type,
Source_Type untuk semua records.

Simpan sebagai: `screening_scr_[topik]_[YYYYMMDD].xlsx`
```

> **💡 Tips Claude:** Reason codes ScR (C-CONCEPT-NOMATCH, C-CONTEXT-NOMATCH) terpisah dari SLR karena PCC punya dua "C". Screener perlu jelas apakah eksklusi karena Concept-nya tidak cocok (mis. AI klasik vs generative AI yang dicari) atau Context-nya (mis. pendidikan menengah padahal cari perguruan tinggi). Breakdown ini wajib untuk PRISMA-ScR flow diagram.

**Review** file Excel — pastikan embedded criteria Row 1-6 benar, PRISMA-ScR flow tracker sheet ada, dan reason codes lengkap.

---

## **HASIL AKHIR**

### **Complete Data Mining Package ScR (v1):**
```
=== DATA MINING RESULTS (SCR) ===

SEARCH EXECUTION (per sumber):
- Scopus: string [dari Modul 3], date [YYYY-MM-DD], pre-filter [N], post-filter [N]
- WoS: [...]
- Google Scholar: query [...], top-200 screened, relevan [N], date [...]
- ProQuest: [...]
- Situs lembaga (WHO/Bappenas/dll): [...]
- OSF/arXiv: [...]

SANITY CHECK:
- Sumber-kunci check: [X/Y paper + laporan kunci found]
- Volume assessment: [reasonable / too-many / too-few]
- Distribusi peer vs grey: [X% / Y%]
- Go/no-go decision: [PROCEED]

EXPORT DETAILS:
- Files: [list dengan path dan naming]
- Records per sumber: [breakdown]
- Fields preserved: Authors/Org, Title, Year, Abstract/Summary, DOI/URL,
  Keywords, Journal/Publisher, Document_Type, Source_Type

DEDUPLICATION (multi-sumber):
- Total across sources: [N]
- Unique after dedup: [N]
- Duplicates: [N] (DOI-matched: X, title-matched: Y, URL-matched: Z)
- Peer vs Grey post-dedup: [X peer, Y grey]
- Manual review flags: [N]

PCC-CONSISTENCY PREVIEW (sample 30):
- MATCH "WHAT COUNTS": X%
- PARTIAL MATCH: X%
- MATCH "WHAT DOESN'T": X%
- AMBIGU: X%
- OFF-TOPIC: X%
- Verdict: [PROCEED]

SCREENING DATABASE:
- File: screening_scr_[topik]_[YYYYMMDD].xlsx
- Total records: [N]
- Embedded PCC criteria: ✓ (Row 1-6)
- Reason codes ScR: ✓ (P-NOMATCH, C-CONCEPT-NOMATCH, C-CONTEXT-NOMATCH,
  STUDY-DESIGN, LANGUAGE, DUPLICATE, NO-ABSTRACT, INACCESSIBLE, OTHER)
- Kappa sheet: ✓ (ready untuk Modul 5)
- PRISMA-ScR Flow Tracker sheet: ✓
- Dual-reviewer columns: ✓

FORWARD ARTIFACTS:
- Date stamp: [YYYY-MM-DD per sumber] → Modul 5-9
- Update search policy (Modul 3 L4): → Modul 9 Methods
- Operational definitions PCC (Modul 2 L3): embedded in screening file
- Canonical terminology: embedded

NEXT STEP: Title/abstract screening + kappa calibration (Modul 5)
```

---

## **TROUBLESHOOTING**

**Problem 1: Sanity check gagal — sumber kunci tidak muncul**
- Cek apakah sumber kunci lolos filter (year, language, document type)
- Jika lolos filter tapi absen → search string tidak menangkap terminologi
- Balik ke Modul 3 L2: apakah keyword sumber kunci ada di Main synonyms (Concept/Context)?
- Jika terminologi sumber kunci justru ada di AVOID list → konflik definisi operasional, balik ke Modul 2 L3
- Untuk grey lit: cek apakah sumber lembaga kunci (mis. WHO, Bappenas) benar-benar di-hand-search, bukan hanya diandalkan Google Scholar

**Problem 2: PCC preview check <40% match**
- Identifikasi pola noise dominan:
  - Banyak MATCH "WHAT DOESN'T" (Concept) → AVOID list Concept kurang lengkap, balik ke Modul 3 L2
  - Banyak MATCH "WHAT DOESN'T" (Context) → keywords Context terlalu umum, tambah geographic/setting specifier
  - Banyak AMBIGU → operational definitions (Modul 2 L3) terlalu samar, perlu dipertajam
  - Banyak OFF-TOPIC → kemungkinan keyword trap (homonim, istilah ambigu antar-disiplin)

**Problem 3: Multi-sumber dedup terlalu sedikit duplikat (mencurigakan)**
- Cek normalisasi DOI (format beda antar DB)
- Cek title matching — karakter khusus, Unicode quote, dash vs hyphen
- Untuk grey lit: cek URL normalization (http vs https, trailing slash)
- Manual sample: ambil 5 paper populer + 2 laporan populer yang pasti ada di ≥2 sumber, cek apakah match detected
- Jika benar overlap rendah → kemungkinan sumber punya niche berbeda (wajar untuk ScR multi-sumber)

**Problem 4: Export CSV tidak lengkap / abstract terpotong**
- Scopus kadang memotong abstract sangat panjang di CSV
- Solusi: export RIS atau BibTeX (lebih lengkap), lalu konversi ke CSV
- Records dengan abstract terpotong: tandai [ABSTRACT-TRUNCATED], prioritaskan full-text retrieval
- Untuk grey lit tanpa abstract formal: gunakan executive summary / first paragraph sebagai proxy, tandai di notes

**Problem 5: Grey literature sulit di-dedup / metadata tidak konsisten**
- Standardisasi manual: buat kolom "normalized_title" (lowercase, strip punctuation) dan "normalized_year"
- Grey lit dari situs lembaga sering tidak punya DOI → andalkan URL + title match
- Satu laporan dengan versi update (2021, 2023): treat as separate records kecuali substansi identik, catat di notes "superseded by [year]"

**Problem 6: File CSV terlalu besar untuk upload ke Claude**
- Split CSV by source atau by year
- Upload per batch, minta Claude merge output di akhir
- Alternatif: pre-filter di Excel (mis. hanya Document Type yang relevan, hapus missing abstract)

**Problem 7: Ragu apakah distribusi peer vs grey sudah sehat**
- Benchmark ScR umum: peer-reviewed 60-80%, grey lit 20-40% (tergantung topik)
- Jika grey lit <10% → grey lit search kurang intensif, pertimbangkan re-run Modul 3 grey lit strategy
- Jika grey lit >50% dan topik seharusnya kaya peer-reviewed → cek peer-reviewed DB coverage, mungkin missed

---
