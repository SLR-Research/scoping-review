# Modul 7: Data Charting untuk Scoping Review (Optional Quality Appraisal)

---

## **LANGKAH 1: CHARTING FRAMEWORK SELECTION + CHARTING FORM DRAFT**

> **🎯 Tujuan:** Pilih framework charting (bukan "extraction") SEBELUM mulai. Charting form ScR bersifat **iteratif** (Levac et al., 2010 enhancement): draft → pilot dengan 5-10 studi → refine → finalize. Ini berbeda dari SLR extraction yang final di awal. Framework charting menentukan struktur Results dan Discussion di Modul 9.

### **Perbedaan Penting: Charting vs Extraction**

| Aspek | Extraction (SLR) | Charting (ScR) |
|---|---|---|
| Tujuan | Ekstrak variabel untuk sintesis jawaban RQ | Petakan karakteristik untuk pemetaan |
| Struktur form | Ditetapkan a priori, rigid | **Iteratif, direvisi post-pilot** |
| Fokus | Effect size, variabel kausal | Deskripsi, konsep, konteks, gap |
| Perlakuan missing | Ditandai NOT REPORTED, QA concern | Ditandai NR, **tidak menjadi basis eksklusi** |
| Quality Assessment | Wajib, exclusionary | **Opsional, non-exclusionary** |

### **Prompt untuk Claude:**
```
Saya akan mulai data charting untuk [N] sumber yang lolos Modul 6.

Konteks dari modul sebelumnya:
- Research question ScR (Modul 2 L5): [primary + secondary, "what/how/which" style]
- PCC + operational definitions (Modul 2 L3): [ringkasan]
- Tipe gap yang ditarget (Modul 2 L1): [A/B/C/D]
- Source distribution (Modul 6): [peer-reviewed N, grey lit N]
- Document type breakdown: [articles, reports, theses, policy briefs, dll.]

=== TUGAS 1: CHARTING FRAMEWORK RECOMMENDATION ===

ScR charting framework lebih fleksibel daripada SLR extraction. Pilihan:

OPSI A — JBI RECOMMENDED CHARTING (default untuk ScR umum)
  Kolom standar:
  - Meta: Author(s)/Org, Year, Country, Source type (peer/grey)
  - Study design/Document type
  - Aims/Purpose
  - Population (jika applicable): characteristics
  - Concept: bagaimana dikonseptualisasikan/operasionalisasikan
  - Context: setting, sector, cultural, policy environment
  - Methodology (jika empiris): sampling, data collection, analysis
  - Key findings relevant to PCC
  - Gap/future research noted by authors

OPSI B — PCC-DRIVEN CHARTING (untuk ScR fokus konseptual)
  Turunkan langsung dari PCC + secondary RQs.
  Contoh untuk ScR tentang "generative AI dalam higher education Indonesia":
  - P: mahasiswa S1/S2/dosen, demografi
  - C (Concept): jenis AI tool, mode penggunaan, aktivitas pembelajaran
  - C (Context): institusi (PTN/PTS), disiplin, setting (kelas/online/hybrid),
    kebijakan institusi
  - Outcome/impact reported (bukan untuk effect size, tapi untuk mapping jenis)

OPSI C — THEMATIC FRAMEWORK (untuk ScR konseptual/teoretis)
  Cocok jika ScR bertujuan klarifikasi konsep (Tipe Gap B):
  - Definisi konsep yang digunakan
  - Dimensi konsep yang disebut
  - Related concepts
  - Theoretical lens
  - Examples/illustrations yang diberikan

OPSI D — POLICY/PRACTICE-ORIENTED CHARTING (untuk ScR kebijakan)
  Cocok jika grey lit dominan dan fokus implementasi:
  - Policy area/sector
  - Implementation level (nasional/regional/institusional)
  - Stakeholders identified
  - Recommendations made
  - Evidence base cited

OPSI E — HYBRID / CUSTOM
  Kombinasi atau domain-specific. Wajib dijustifikasi ekstensif.

Untuk ScR saya, opsi mana yang paling cocok? Berikan:
- Rekomendasi + alasan (3-4 kalimat, merujuk PCC + gap type)
- Jika rekomendasi CUSTOM: struktur yang diusulkan

=== TUGAS 2: DRAFT CHARTING FORM ===

Bangun draft charting form (belum final — akan dipilot di L2). Contoh untuk
OPSI A (JBI standard):

| Kolom | Kategori | Isi |
|-------|----------|-----|
| ID | Meta | SCR[ID] |
| Source_Type | Meta | PEER / GREY |
| Document_Type | Meta | Article/Conference/Thesis/Report/Policy Brief/Preprint |
| Author(s)/Organization | Meta | Citation |
| Year | Meta | |
| Country/Region | Meta | |
| Journal/Publisher | Meta | |
| DOI/URL | Meta | |
| **Aims/Purpose** | Core | Tujuan sumber (1-2 kalimat) |
| **Study Design** | Core | Desain (jika empiris) atau "Conceptual"/"Policy" |
| **Population (if applicable)** | PCC-P | Karakteristik partisipan/target |
| **Concept Operationalization** | PCC-C | Bagaimana Concept dikonseptualisasikan di sumber ini |
| **Context Details** | PCC-C | Setting, kultural, kebijakan, temporal |
| **Methodology** | Core | Jika empiris: sampling, data collection, analysis |
| **Key Findings (PCC-relevant)** | Core | Temuan utama yang terkait PCC |
| **Gaps/Future Research** | Core | Gap atau future research yang DISEBUT penulis |
| **Notes** | Manual | Catatan charter, termasuk ambiguitas |

Variasi per opsi framework (B/C/D) akan berbeda. Berikan form sesuai opsi terpilih.

=== TUGAS 3: PILOT PLAN ===

Charting form ScR WAJIB dipilot sebelum finalisasi (prinsip Levac et al.):

1. Pilot dengan 5-10 sumber yang beragam (mix peer + grey, mix document types)
2. Kedua charter isi form independen
3. Bandingkan hasil: kolom mana yang sering NR? Kolom mana yang ambigu?
4. Refine form: tambah/hapus/rephrase kolom sesuai temuan pilot
5. Dokumentasi revisi sebagai "iterative refinement" di Methods

Output: draft charting form + pilot plan + rencana iterasi.
```

> **💡 Tips Claude:** Pemilihan framework charting adalah keputusan strategis yang memengaruhi seluruh struktur Results. Konsultasi supervisor atau cross-check dengan prior scoping reviews (Modul 2 L2) — framework charting apa yang mereka pakai? Mengikuti konvensi bidang memudahkan publikasi dan perbandingan lintas-ScR.

**Dokumentasikan** framework charting pilihan + justifikasi — akan dikutip di Methods (Modul 9).

---

## **LANGKAH 2: ITERATIVE CHARTING (PILOT → REFINE → FINAL)**

### **Setup Charting Spreadsheet:**

1. Buat file Excel baru: `charting_scr_[topik]_[YYYYMMDD].xlsx`
2. Struktur kolom sesuai DRAFT template dari L1
3. Header meta (Row 1-6): framework charting + operational definitions PCC + date
4. Satu baris per sumber, diurutkan by ID (SCR001, SCR002, ...)
5. Tambah Sheet "Pilot_Iterations" untuk melacak revisi form

### **2.1 Pilot Phase (WAJIB untuk ScR):**

```
[Upload 5-10 PDF sampel beragam: peer + grey, berbagai document types]

Saya akan pilot charting form untuk Scoping Review.
Framework charting: [dari L1]
Draft form columns: [list kolom]
Operational definitions PCC (dari Modul 2 L3):
- P WHAT COUNTS: [...]
- C (Concept) WHAT COUNTS: [...]
- C (Context) WHAT COUNTS: [...]

Untuk setiap PDF, lakukan CHARTING sesuai draft form.

ATURAN PILOT:
1. EVIDENCE-BACKED: untuk setiap field, kutip kalimat pendukung dengan section
   reference (mis. "Methods p.5: 'The study involved 234 students...'")

2. TANDAI [NOT REPORTED] jika informasi tidak tersedia.
   JANGAN mengira-ngira. Untuk grey lit tanpa Methods formal, ini WAJAR — 
   tandai NR, bukan dianggap cacat.

3. KONSISTENSI TERMINOLOGI: pakai istilah kanonikal dari Modul 2 L3 saat menulis
   field. Jika sumber pakai istilah berbeda, catat di Notes.

4. FLAG AMBIGUITY: jika field borderline, tandai [AMBIGUOUS: reason].

5. PILOT OBSERVATIONS (khusus pilot, bukan charting final):
   - Kolom mana yang sulit diisi untuk jenis sumber tertentu?
   - Kolom mana yang redundant atau overlap?
   - Ada informasi penting yang DISEBUT di sumber tapi TIDAK ADA kolomnya?
   - Apakah charting untuk grey lit membutuhkan kolom berbeda dari peer?

Output:
1. Charted data untuk 5-10 sampel (format tabel)
2. Pilot observations (sebagai rekomendasi untuk refine form)
3. Draft revisi form v2
```

### **2.2 Refinement Meeting (Human):**

Dua charter + supervisor (jika ada) bertemu untuk:
1. Review pilot observations
2. Diskusi kolom yang diusulkan untuk direvisi (tambah/hapus/rephrase)
3. Keputusan: freeze form v2 untuk charting penuh
4. **Dokumentasikan perubahan form** dengan alasan — masuk ke Methods sebagai "iterative refinement"

### **2.3 Full Charting dengan Form Final:**

> **🚀 Fitur Claude:** Upload PDF langsung — Claude membaca full-text dan chart data ke template. Bisa batch 5-10 PDF sekaligus.

```
[Upload batch PDF: SCR001.pdf, SCR002.pdf, ...]

Framework charting: [dari L1, sudah direvisi post-pilot]
Final charting form columns: [list kolom final]
Operational definitions PCC (dari Modul 2 L3): [...]

Chart data dari semua [N] PDF sesuai form final.

ATURAN CHARTING:

1. EVIDENCE-BACKED untuk setiap field (kutipan + section reference)

2. [NOT REPORTED] untuk field tidak ada di sumber — tanpa mengira

3. Konsistensi terminologi dengan canonical terms Modul 2 L3

4. FLAG AMBIGUITY dengan [AMBIGUOUS: reason]

5. Untuk grey lit: struktur sumber sering non-standar — cantumkan [NR:
   not applicable] jika kolom tidak relevan (mis. "Sample size" untuk policy
   brief)

Format output tabel terkonsolidasi (siap-paste ke Excel):

| ID | Source_Type | Author/Org | Year | [kolom framework lengkap] | Notes |

Di akhir, sajikan:
1. Coverage summary: berapa field COMPLETE vs NR per sumber
2. Daftar sumber dengan >50% NR (normal untuk grey lit, flag untuk analisis)
3. Daftar AMBIGUOUS fields yang butuh verifikasi manual
```

### **2.4 Human Verification Protocol (ScR Adaptation):**

**Spot-verification pattern** (bukan full dual-chart — cost-benefit):

1. **Charter 1 (lead):** full charting semua sumber dengan bantuan Claude
2. **Charter 2 (verifier):** ambil random 20% sampel + semua AMBIGUOUS fields, verifikasi ke sumber asli
3. **Disagreement di sampel:**
   - Jika disagreement rate <10%: acceptable (tolerance ScR lebih longgar dari SLR), catat di Limitations
   - Jika 10-20%: diskusi pattern, refine charting protocol, re-do flagged subset
   - Jika >20%: full dual-charting untuk seluruh studi

**Charting kappa** (jika full dual-chart): hitung untuk kolom kategorik (document type, country, concept category).

> **💡 Tips Claude:** Tolerance disagreement ScR lebih longgar (<10% vs <5% SLR) karena charting mencakup lebih banyak kolom deskriptif yang bersifat interpretif. Fokuskan verifikasi pada kolom KRITIS untuk peta (Concept Operationalization, Context Details, Key Findings) — bukan Meta.

---

## **LANGKAH 3: OPTIONAL QUALITY APPRAISAL (NON-EXCLUSIONARY)**

> **🎯 Tujuan:** JBI eksplisit: Quality Assessment (QA) untuk ScR bersifat **OPSIONAL** dan **TIDAK BOLEH** digunakan untuk eksklusi. Jika dilakukan, QA berfungsi mendeskripsikan kualitas bukti dalam peta (untuk evidence gap map) atau sebagai informasi untuk peneliti yang akan melakukan SLR lanjutan.

### **3.1 Keputusan: QA atau Tidak?**

```
Saya memiliki data charted untuk [N] sumber.
Tipe gap ScR (Modul 2 L1): [A/B/C/D]

Tolong bantu keputusan: apakah QA opsional ini perlu dilakukan untuk ScR saya?

KAPAN QA RELEVAN UNTUK ScR:
[ ] ScR sebagai prekursor untuk SLR (Tipe D) → QA awal memberi gambaran
    kualitas yang akan diharapkan di SLR lanjutan
[ ] Evidence gap map perlu menampilkan dimensi "kualitas" selain "kuantitas"
[ ] Stakeholder/funder secara eksplisit meminta informasi kualitas
[ ] RQ menanyakan karakterisasi metodologi (Tipe C)

KAPAN QA TIDAK PERLU:
[ ] ScR fokus klarifikasi konsep (Tipe B) — kualitas bukan fokus
[ ] ScR fokus pemetaan awal (Tipe A) — inklusivitas prioritas
[ ] Waktu/resource terbatas dan QA akan delay publikasi
[ ] Grey lit dominan — standard QA tools sulit diterapkan

REKOMENDASI untuk ScR saya: [YES with tool / YES dengan AACODS untuk grey lit /
                             NO, dokumentasikan alasan di Methods]

Jika NO, dokumentasikan di Methods:
"Following JBI guidelines for scoping reviews (Peters et al., 2020), we did
not conduct formal quality appraisal, as it is not required for the purpose
of mapping the evidence."
```

### **3.2 Jika QA Dilakukan — Tool Selection:**

```
Study designs + document types dari charting:
- Peer-reviewed empirical: [N] — breakdown design
- Peer-reviewed conceptual/review: [N]
- Grey lit (reports, policy briefs, theses, preprints): [N]

Pilih tool QA yang appropriate untuk ScR:

OPSI 1 — MMAT (Mixed Methods Appraisal Tool)
  - Cocok untuk ScR lintas-desain peer-reviewed
  - Satu rubrik: quantitative, qualitative, mixed
  - Dapat digunakan non-exclusionary (reporting only)

OPSI 2 — JBI Critical Appraisal Tools
  - Set terpisah per design
  - Aligned dengan JBI scoping review methodology
  - Score dinormalisasi untuk komparabilitas

OPSI 3 — AACODS Checklist (KHUSUS GREY LITERATURE)
  - Authority, Accuracy, Coverage, Objectivity, Date, Significance
  - Dikembangkan khusus untuk grey lit
  - Direkomendasikan jika grey lit dominan dan QA dilakukan

OPSI 4 — MULTI-TOOL (pragmatis)
  - MMAT untuk peer-reviewed
  - AACODS untuk grey lit
  - Score dinormalisasi 0-100% untuk komparabilitas

Untuk breakdown saya, tool mana yang paling cocok?

Output: tool pilihan + justifikasi 100-150 kata untuk Methods.
PENEGASAN: QA ini NON-EXCLUSIONARY — skor dilaporkan deskriptif, tidak
digunakan untuk menyaring sumber.
```

### **3.3 Dual-Reviewer QA (Jika Dilakukan):**

```
Prosedur:
1. Kedua reviewer menilai QA secara independen
2. Gunakan tool yang dipilih di 3.2
3. Isi kolom QA_Score di charting spreadsheet per reviewer
4. Hitung kappa untuk agreement pada kategori QA
5. Jika disagreement: diskusi → consensus

Target kappa QA: ≥ 0.60 (substantial) — sama dengan SLR, namun kappa lebih
rendah dapat diterima untuk grey lit yang sulit dinilai dengan rubric standar.

Dokumentasikan kappa QA di Methods + penegasan bahwa skor TIDAK exclusionary.
```

### **3.4 Pelaporan QA dalam Peta Bukti:**

```
Jika QA dilakukan, integrasikan ke peta bukti:

OPSI A — Dimensi ke Evidence Gap Map
  Heatmap dengan 2 sumbu: Concept × Context, dengan color intensity = jumlah sumber
  + pattern/border = quality level (HIGH solid, MODERATE dashed, LOW dotted)

OPSI B — Tabel Kolom Quality
  Charting spreadsheet + kolom QA_Category (HIGH/MODERATE/LOW)
  Results section: narasi "Of the 45 sources, 12 (27%) were rated HIGH quality,
  22 (49%) MODERATE, and 11 (24%) LOW. Quality was NOT used for exclusion."

OPSI C — Sensitivity Analysis Narrative
  "Pemetaan utama mencakup semua 45 sumber. Sebagai analisis sensitivitas,
  kami juga memetakan hanya sumber HIGH+MODERATE (n=34). Pattern peta
  [tidak berubah / berubah signifikan] ketika sumber LOW quality dikeluarkan,
  menunjukkan [robustness / sensitivity]."

PENEGASAN ScR: QA reporting harus transparan sebagai informasi deskriptif,
bukan untuk menyaring. Kerangka JBI + PRISMA-ScR mengharapkan ini.
```

---

## **LANGKAH 4: MAPPING PREPARATION + NARRATIVE SYNTHESIS PLAN**

> **🎯 Tujuan:** Sebelum masuk Modul 8, persiapkan groupings dan strategi pemetaan. Untuk ScR, tidak ada "meta-analysis feasibility flag" — **selalu narrative/thematic/descriptive**. Yang perlu diputuskan: pendekatan mapping mana yang paling informatif.

### **Prompt untuk Claude:**
```
[Upload charting spreadsheet final dari L2 + QA results dari L3 (jika ada)]

Framework charting: [dari L1]
Total final INCLUDED sources: [N]
Breakdown: peer-reviewed [N], grey lit [N]

Tolong bantu mapping preparation:

=== 1. DESCRIPTIVE OVERVIEW ===
- Distribusi study designs / document types
- Distribusi geografis (Country/Region)
- Distribusi tahun publikasi (time trend)
- Distribusi per komponen PCC:
  · P: karakteristik populasi (jika applicable)
  · C (Concept): jenis/variasi Concept yang ditemukan
  · C (Context): jenis/variasi Context
- Breakdown peer vs grey per kategori

=== 2. CATEGORICAL ANALYSIS (Core ScR) ===

Untuk setiap kolom kunci dalam charting form:
- Identifikasi kategori-kategori yang muncul
- Hitung frekuensi per kategori
- Deteksi pola: dominance, clusters, outliers

Contoh untuk kolom "Concept Operationalization":
- Kategori 1: [nama] — n=[X] sumber
- Kategori 2: [nama] — n=[X]
- [dst]

Kategori ini akan jadi basis thematic mapping di Modul 8.

=== 3. GAP IDENTIFICATION (INTI ScR) ===

Berdasarkan charting data, identifikasi gap dalam bukti:

GAP KUANTITATIF (apa yang jarang di-cover):
- Populasi yang underrepresented
- Context yang jarang dipetakan
- Kombinasi PCC yang tidak ada sumbernya
- Periode/era yang sparse

GAP KUALITATIF (apa yang tidak terkonsep dengan baik):
- Konsep yang ambigu di literatur
- Terminologi yang inkonsisten
- Theoretical framework yang absen

GAP METODOLOGIS:
- Desain studi yang belum pernah dipakai untuk Concept ini
- Pendekatan analisis yang underused

Output: "Evidence Gap Inventory" siap untuk Modul 8 visualisasi.

=== 4. MAPPING APPROACH RECOMMENDATION ===

Untuk ScR saya, pendekatan mapping mana yang paling informatif?

OPSI A — DESCRIPTIVE NUMERICAL SUMMARY
  Tabel + chart frekuensi (count, percentage)
  Cocok untuk: semua ScR sebagai dasar

OPSI B — THEMATIC/CATEGORICAL MAPPING
  Pengelompokan tematik berdasarkan Concept operationalization
  Cocok untuk: ScR konseptual (Tipe B)

OPSI C — EVIDENCE GAP MAP (matrix/heatmap)
  2D heatmap: biasanya Concept × Context atau Intervention × Outcome
  Cocok untuk: ScR gap identification (Tipe A, D)

OPSI D — HYBRID (rekomendasi default untuk ScR berkualitas)
  Kombinasi A + B + C:
  - A untuk deskripsi dasar
  - B untuk konsep mapping
  - C untuk gap visualization

Rekomendasi: [pilih + justifikasi]

=== 5. FRAMEWORK-DRIVEN GROUPINGS ===

Siapkan groupings untuk Results section (Modul 9):

Berdasarkan framework charting L1:
- Group 1: [dimensi framework] — [N] sumber
- Group 2: [...]
- ...

Setiap group akan jadi sub-section di Results.

Output:
- Descriptive overview tabel
- Categorical analysis per kolom kunci
- Evidence Gap Inventory
- Mapping approach verdict
- Framework-driven groupings untuk narrative mapping
```

**Hasil L4** adalah input kritis untuk Modul 8. Simpan sebagai `mapping_prep_[topik].md` atau dokumentasikan di charting spreadsheet.

---

## **HASIL AKHIR**

### **Data Charting + Optional QA Package ScR (v1):**
```
=== CHARTING + (OPTIONAL) QA RESULTS (ScR) ===

CHARTING FRAMEWORK SELECTION (→ Methods):
- Framework: [JBI standard / PCC-driven / Thematic / Policy-oriented / Custom]
- Justifikasi: [100-150 kata]
- Charting form columns: [list kolom final]

PILOT ITERATION (→ Methods, sebagai "iterative refinement"):
- Pilot sample: [N sumber, mix peer + grey]
- Pilot observations: [ringkasan]
- Revisions made: [list perubahan kolom dengan alasan]
- Final form version: v[X]

CHARTING EXECUTION:
- Total sources charted: [N]
- Charting period: [dates]
- Method: single-charter dengan Claude assistance + 20% spot-verification
- Spot-verification disagreement rate: [%]
- NOT REPORTED fields prevalence: [breakdown peer vs grey]
- AMBIGUOUS fields resolved: [N]

OPTIONAL QA (→ Methods, jika dilakukan):
- QA performed: [YES / NO]
- Justifikasi keputusan: [paragraph]
- If YES:
  · Tool: [MMAT / JBI / AACODS / multi-tool]
  · Justifikasi tool: [100-150 kata]
  · Dual-reviewer kappa QA: [X]
  · Categorization: HIGH [N], MODERATE [N], LOW [N]
  · NON-EXCLUSIONARY: ✓ (penegasan eksplisit)
  · Reporting approach: [dimension di gap map / kolom deskriptif / sensitivity]

DESCRIPTIVE OVERVIEW (→ Results):
- Study designs / Document types: [breakdown]
- Geographic: [breakdown]
- Temporal: [breakdown]
- Framework-component breakdown: [per Concept, Context, Population]
- Peer vs Grey distribution per kategori

CATEGORICAL ANALYSIS:
- Concept Operationalization categories: [list + frekuensi]
- Context categories: [list + frekuensi]
- Methodology categories: [list + frekuensi]

EVIDENCE GAP INVENTORY:
- Quantitative gaps: [...]
- Qualitative/conceptual gaps: [...]
- Methodological gaps: [...]

MAPPING APPROACH VERDICT:
- Recommended: [Descriptive / Thematic / Gap Map / Hybrid]
- Rationale: [...]

FRAMEWORK-DRIVEN GROUPINGS (→ Modul 9 Results structure):
- Group 1: [...] (n=[N])
- Group 2: [...] (n=[N])
- ...

FORWARD ARTIFACTS (→ Modul 8):
- charting_scr_[topik].xlsx dengan semua data charted
- QA scores (jika dilakukan) + categorization
- Evidence Gap Inventory
- Mapping groupings per framework
- Canonical terminology (dari Modul 2 L3)
```

---

## **TROUBLESHOOTING**

**Problem 1: Charting form tidak fit untuk grey lit**
- Grey lit sering tidak punya struktur standar peer-reviewed
- Solusi: tambah Sheet terpisah untuk grey lit dengan kolom yang disesuaikan (mis. drop "Sample size", tambah "Report type", "Implementation level")
- Atau: gunakan kolom sama tapi terima NR tinggi — dokumentasikan sebagai karakteristik ScR multi-source
- Jangan paksa struktur peer-reviewed ke grey lit

**Problem 2: Banyak field [NOT REPORTED] — apakah normal?**
- Untuk ScR, NR rate tinggi adalah **normal**, terutama untuk grey lit
- Jangan panik — catat sebagai data (bisa jadi temuan: "reporting standard inkonsisten di literatur ini")
- Flag sumber dengan >70% NR untuk assessment apakah substansi cukup untuk mapping
- Jika flagged sumber tidak punya substansi yang bisa di-chart → kembali ke Modul 6, mungkin seharusnya NO-SUBSTANTIVE-CONTENT

**Problem 3: Charting disagreement tinggi (>20%)**
- Pattern check: disagreement di kolom tertentu?
- Refine operational definition kolom + contoh
- Re-calibrate dengan 5-10 sampel baru
- Jika tetap tinggi: full dual-charting untuk seluruh studi

**Problem 4: Godaan exclude berdasarkan QA rendah — JANGAN**
- ScR **TIDAK** mengeksklusi atas dasar QA (prinsip JBI)
- Skor LOW dilaporkan deskriptif dalam peta bukti
- Sensitivity analysis boleh menampilkan "mapping hanya HIGH+MODERATE" — tapi mapping utama harus inklusif

**Problem 5: Pilot menunjukkan perlu banyak revisi form**
- Ini BUKAN kegagalan — ini prinsip iteratif ScR berjalan
- Dokumentasikan semua revisi + alasan sebagai bukti rigor metodologis
- Jika revisi terlalu radikal (>5 kolom ditambah/dihapus), pertimbangkan pilot tahap 2

**Problem 6: Concept operationalization sangat beragam — sulit dikategorikan**
- Ini justru **temuan penting** (gap Tipe B: ambiguitas konseptual)
- Gunakan thematic analysis untuk mengelompokkan variasi
- Dokumentasikan sebagai "heterogeneity in conceptualization" — masuk ke Discussion sebagai contribution
- Claude bisa bantu clustering: minta "group these 45 operationalizations into 4-6 thematic categories"

**Problem 7: Grey lit sulit di-QA (AACODS juga terbatas)**
- Banyak grey lit memang tidak memenuhi kriteria QA standar
- Untuk ScR: laporkan AACODS score sebagai informasi, tidak untuk eksklusi
- Dokumentasikan di Limitations: "Grey literature quality varied widely, limiting formal appraisal"
- Alternative: focus pada Authority + Date + Objectivity saja (subset AACODS)

**Problem 8: Supervisor/reviewer minta meta-analysis**
- Tegaskan: ini scoping review, bukan SLR — meta-analysis tidak sesuai
- Tunjukkan Modul 2 L1 Tipe Gap + justifikasi pilih ScR
- Jika ada subset homogen yang bisa meta-analyzed: pertimbangkan ScR + mini-SLR sebagai dua output terpisah (bukan satu)
- JBI Manual Ch.11 eksplisit: ScR **bukan** meta-analysis

---
