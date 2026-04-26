# Modul 7: Data Charting untuk Scoping Review (Claude Cowork)

> **🎯 Output Modul Ini:** `charting.xlsx` lengkap berisi data setiap sumber INCLUDED, di-chart sesuai framework PCC, siap untuk mapping di Modul 8.

> **🤝 Workflow Modul Ini:** Lanjutan dari Modul 6 — gunakan **folder kerja yang sama** (`ScR_Project/` atau nama yang Anda pilih). Claude cowork akses PDF di `pdfs/`, generate charting form, isi `charting.xlsx` langsung.

> **📌 Perbedaan dari SLR:** Ini **CHARTING** (bukan extraction). Form-nya **iteratif** (Levac et al.) — boleh direvisi setelah pilot. Quality Assessment **OPSIONAL** dan non-exclusionary.

---

## **LANGKAH 0: PERLUASAN FOLDER KERJA (LANJUTAN MODUL 6)**

> **📁 Catatan:** Jika di Modul 6 Anda pakai nama folder selain `ScR_Project/`, gunakan nama yang sama di Modul 7 — konsistensi lintas modul wajib.

### **Prompt Cowork (single prompt — setup file baru + brief context):**

```
Lanjut Modul 7 (Data Charting) di folder kerja saya [ScR_Project/ atau nama
folder Anda dari Modul 6]. Eksekusi dua hal sekaligus:

=== BAGIAN A: SETUP FILE TAMBAHAN ===

Target struktur akhir:

ScR_Project/                       ← folder yang sama dari Modul 6
├── pdfs/                          ← (dari M6)
├── screening.xlsx                  ← (dari M6)
├── pcc_definitions.md              ← (dari M6)
├── reason_codes.md                 ← (dari M6)
├── briefing.md                     ← (dari M6)
├── charting_form.md                ← BARU — definisi kolom charting
├── charting.xlsx                   ← BARU — data charted
└── pilot_log.md                    ← BARU — log iterasi form (jika revisi)

Steps:
1. CREATE charting_form.md (kosong, diisi di L1)

2. CREATE charting.xlsx dengan struktur:
   - Sheet "Charting": Row 1-5 header meta (Framework + canonical PCC + tanggal),
     kolom data mulai Row 6 (kolom ditentukan setelah L1)
   - Sheet "Pilot_Log": tracking iterasi revisi form
     (Iterasi | Tanggal | Perubahan | Alasan)
   - Sheet "Summary": auto-calculated (total sources, NR rate, peer/grey breakdown)

3. Pre-populate Sheet "Charting" dengan baris untuk setiap source dari
   screening.xlsx yang Final_Decision=INCLUDE. Isi kolom meta dasar
   (ID, Source_Type, Author/Org, Year, DOI/URL, Document_Type).

=== BAGIAN B: BRIEF AWAL CONTEXT ===

Setelah setup, simpan context untuk seluruh sesi Modul 7:

- Target charting: sources Final_Decision=INCLUDE di screening.xlsx
- PDFs di pdfs/
- Standar: JBI Manual Ch.11 — ini CHARTING (iteratif), bukan extraction
- Quality Assessment: opsional dan non-exclusionary
- TIDAK ADA meta-analysis di ScR
- Output format default: tabel/bullet ringkas, no preamble
- Bahasa: Indonesia

VERIFY: file baru tersimpan + total INCLUDED rows pre-populated + context siap
untuk eksekusi L1-L4.
No preamble.
```

---

## **LANGKAH 1: PILIH FRAMEWORK + DRAFT CHARTING FORM**

### **Prompt Cowork:**

```
Bantu pilih framework charting yang paling cocok untuk ScR saya.

Konteks dari modul sebelumnya:
- RQ primary: [paste dari Modul 2 L5]
- Tipe gap: [A/B/C/D dari Modul 2 L1]
- Total INCLUDED sources: [N]
- Source breakdown: peer-reviewed [X], grey [Y]
- Document types: [breakdown]

Pilihan framework:
- JBI standard (default — meta + study design + PCC + findings + gaps)
- PCC-driven (langsung turun dari PCC)
- Thematic (untuk Tipe Gap B — klarifikasi konsep)
- Policy-oriented (jika grey lit/policy dominan)
- Custom (justifikasi ekstensif)

Output:
1. REKOMENDASI framework + alasan singkat (3-4 kalimat)
2. DRAFT charting form: list kolom + deskripsi singkat per kolom
3. Tulis ke charting_form.md di folder kerja saya
4. Update Sheet "Charting" di charting.xlsx: tambah kolom-kolom sesuai draft

No preamble.
```

> **💡 Tips:** Default rekomendasi untuk ScR umum = **JBI standard**. Pilih custom hanya jika ada kebutuhan khusus.

---

## **LANGKAH 2: ITERATIVE CHARTING (PILOT → REFINE → FULL)**

### **Prompt Cowork (single prompt, 3 fase otomatis):**

```
Lakukan iterative charting end-to-end dalam satu sesi.

=== FASE 1: PILOT (5-10 SUMBER) ===
1. Pilih 5-10 sources dari charting.xlsx (mix peer + grey, mix document types)
2. Untuk setiap source: baca PDF dari pdfs/, chart sesuai charting_form.md
3. Aturan charting:
   - Evidence-backed: kutip section reference untuk tiap field
   - [NOT REPORTED] jika info tidak ada (jangan mengira)
   - Konsisten dengan canonical terminology di pcc_definitions.md
   - [AMBIGUOUS: alasan] untuk field borderline
4. Isi langsung Sheet "Charting" charting.xlsx
5. Generate PILOT OBSERVATIONS:
   - Kolom mana yang sulit diisi / sering NR?
   - Kolom mana yang redundant / overlap?
   - Ada info penting di sumber yang TIDAK ADA kolomnya?
   - Apakah grey lit butuh kolom berbeda dari peer?

=== FASE 2: REFINE FORM (CONDITIONAL) ===
Berdasarkan pilot observations:
- Jika perlu revisi: update charting_form.md + Sheet "Charting" charting.xlsx
  (tambah/hapus/rephrase kolom) + log ke Sheet "Pilot_Log"
  (Iterasi | Tanggal | Perubahan | Alasan)
- Jika pilot sudah OK: skip refine, catat di Pilot_Log "v1 final, no revisions"

=== FASE 3: FULL CHARTING SISA SOURCES ===
1. Chart sisa sources di charting.xlsx yang belum terisi (form versi final)
2. Batch 5-10 sumber sekaligus, baca PDF dari pdfs/
3. Aturan sama Fase 1
4. Isi langsung Sheet "Charting"

OUTPUT FINAL (di akhir, ringkas):
- Pilot: [N] sources, [list pilot observations 3-4 poin]
- Refinement: [list revisi atau "no revisions needed"]
- Full charting: [N total sources di-chart]
- NR rate per kolom (untuk monitoring)
- Daftar [AMBIGUOUS] yang butuh review manual

No preamble.
```

> **💡 Iterative refinement** adalah prinsip Levac et al. Single prompt untuk seluruh siklus pilot → refine → full charting — cowork eksekusi 3 fase berurutan tanpa break sesi.

### **Verifikasi Manual (Spot-Check 20%):**

Peserta (setelah cowork selesai L2):
1. Pilih random 20% sources yang sudah di-chart
2. Buka PDF + bandingkan dengan baris di charting.xlsx
3. Cek akurasi 3 kolom kritis: Concept Operationalization, Context, Key Findings
4. Jika disagreement >20%: re-run L2 (form revised, ulang fase 1-3)
5. Jika <20%: PROCEED ke L3

---

## **LANGKAH 3: OPTIONAL QUALITY APPRAISAL (DESKRIPTIF, NON-EXCLUSIONARY)**

### **3.1 Keputusan: Lakukan QA atau Tidak?**

```
Tolong rekomendasikan: apakah QA opsional perlu dilakukan untuk ScR saya?

Konteks: Tipe gap [A/B/C/D], purpose [mapping/gap-id/precursor].

KAPAN QA RELEVAN:
- Prekursor SLR (Tipe D) → QA awal
- Evidence gap map butuh dimensi quality
- Stakeholder/funder minta info quality
- RQ menanyakan karakterisasi metodologi (Tipe C)

KAPAN QA TIDAK PERLU:
- Fokus klarifikasi konsep (Tipe B)
- Fokus pemetaan awal (Tipe A)
- Resource terbatas
- Grey lit dominan (sulit di-QA standar)

Output: REKOMENDASI YES/NO + 2-3 kalimat justifikasi (siap-paste ke Methods).
```

### **3.2 Jika YES — Eksekusi QA via Cowork:**

```
Lakukan QA non-exclusionary untuk semua sources di charting.xlsx.

Tool:
- Peer-reviewed empirical: MMAT (Mixed Methods Appraisal Tool)
- Grey lit: AACODS (Authority, Accuracy, Coverage, Objectivity, Date,
  Significance)
- Conceptual paper: skip QA, tag sebagai "conceptual"

Untuk setiap source:
1. Baca PDF
2. Skor sesuai tool
3. Kategorisasi: HIGH (>75%), MODERATE (50-75%), LOW (<50%)
4. Tambah kolom di Sheet "Charting": QA_Tool, QA_Score, QA_Category

PENEGASAN: Skor ini DESKRIPTIF, BUKAN exclusionary. Semua sources tetap
included di mapping.

Output ringkas: distribusi quality (HIGH/MODERATE/LOW counts) + breakdown
peer vs grey.
```

### **3.3 Jika NO — Dokumentasikan Justifikasi:**

```
Generate paragraf 2-3 kalimat untuk Methods section, menjelaskan mengapa
QA tidak dilakukan. Rujuk JBI Manual + PRISMA-ScR item 12 (QA opsional
untuk ScR). Simpan sebagai qa_justification.md di folder kerja.
```

---

## **LANGKAH 4: MAPPING PREPARATION + FINAL SUMMARY (BRIDGE KE MODUL 8)**

### **Prompt Cowork (single prompt — generate dua output sekaligus):**

```
Generate dua file output dari charting.xlsx:

=== OUTPUT 1: mapping_prep.md (BRIDGE KE MODUL 8) ===

Tulis ke outputs/mapping_prep.md (jika folder outputs/ belum ada, buat dulu):

1. DESCRIPTIVE SUMMARY:
   - Total sources charted (peer/grey breakdown)
   - Year distribution
   - Geographic distribution
   - Document type breakdown
   - QA distribution (jika dilakukan)

2. CATEGORICAL ANALYSIS per kolom kunci:
   - Concept Operationalization: kategori + frekuensi
   - Context: kategori + frekuensi
   - Methodology: kategori + frekuensi
   (Jika kategori >15, suggest second-level clustering ke 5-7 meta-kategori)

3. CROSS-TABULATION preview:
   - Concept × Context matrix (cell = N sources)
   - Identifikasi dense cells + gap cells (n=0 atau <3)

4. PRELIMINARY GAP INVENTORY:
   - Gap kuantitatif (PCC kombinasi sparse)
   - Gap kualitatif/konseptual (definisi beragam)
   - Gap metodologis (desain underused)
   - Gap temporal (tahun sparse)

5. RECOMMENDED MAPPING APPROACH untuk Modul 8:
   - Descriptive only / Thematic / Evidence Gap Map / Hybrid
   - Justifikasi singkat

=== OUTPUT 2: modul7_summary.md (HASIL AKHIR MODUL 7) ===

Tulis ke outputs/modul7_summary.md format:

=== CHARTING + (OPTIONAL) QA SUMMARY (ScR) ===

CHARTING FRAMEWORK: [dari L1]
Justifikasi: [3-4 kalimat untuk Methods]

ITERATIVE CHARTING (L2):
- Pilot sample size: [N]
- Revisions made: [list dari Sheet Pilot_Log atau "no revisions"]
- Final form version: v[X]
- Total sources charted: [N] (peer: X, grey: Y)
- NR rate per kolom: [breakdown]
- Spot-check disagreement rate: [<20% / >20%]

OPTIONAL QA (L3): [YES / NO]
Jika YES:
- Tool: [MMAT / AACODS / multi-tool]
- Distribusi: HIGH [N], MODERATE [N], LOW [N]
- NON-EXCLUSIONARY: ✓
Jika NO:
- Justifikasi (2-3 kalimat) di qa_justification.md

MAPPING PREP HIGHLIGHTS (dari Output 1):
- Descriptive overview: [tabel ringkas 3-4 baris]
- Top categorical findings: [3-5 kategori dominan]
- Preliminary gaps: [4 jenis gap, 1 contoh per jenis]
- Recommended mapping approach: [verdict + 1 kalimat justifikasi]

FORWARD ARTIFACTS (→ Modul 8):
- charting.xlsx (lengkap dengan QA jika ada)
- charting_form.md (versi final)
- outputs/mapping_prep.md (input utama Modul 8)
- outputs/qa_justification.md (jika QA tidak dilakukan)

NEXT: Mapping + EGM (Modul 8) — gunakan folder kerja sama.

=== KONFIRMASI ===
Konfirmasi kedua file sudah tersimpan + path absolutnya.
No preamble.
```

> **💡 Manfaat penggabungan:** Single prompt menghasilkan 2 file output (mapping_prep.md untuk Modul 8 + modul7_summary.md sebagai checkpoint). Hemat token + 1 sesi cowork untuk semua wrap-up.

---

## **TROUBLESHOOTING**

**1. Charting form tidak fit untuk grey lit**
- Grey lit sering tanpa Methods formal — terima NR tinggi sebagai karakteristik
- Alternatif: Sheet terpisah untuk grey lit dengan kolom disesuaikan
- Jangan paksa struktur peer-reviewed ke grey lit

**2. NR rate tinggi (>50% di kolom tertentu)**
- Normal untuk ScR multi-source — laporkan sebagai temuan ("reporting standard inkonsisten")
- Flag source dengan >70% NR — cek apakah substansi cukup untuk mapping
- Jika tidak cukup → kembali ke Modul 6, mungkin seharusnya NO-SUBSTANTIVE-CONTENT

**3. Tergoda exclude berdasarkan QA score rendah — JANGAN**
- ScR tidak exclude atas dasar quality (prinsip JBI)
- LOW quality dilaporkan deskriptif di mapping
- Sensitivity analysis boleh tampilkan "mapping HIGH+MODERATE only" tapi mapping utama tetap inklusif

**4. Concept operationalization sangat beragam — sulit dikategorisasikan**
- Ini **temuan penting** (gap Tipe B: ambiguitas konseptual)
- Minta cowork: "group these N operationalizations into 5-7 thematic categories"
- Dokumentasikan heterogeneity sebagai contribution di Discussion

**5. Token cowork cepat habis saat full charting**
- Brief context **sekali** di Langkah 0, tidak ulang
- Batch 5-10 PDF sekaligus, bukan 1-1
- Output tabel saja, no narasi panjang
- Hindari "pikirkan secara mendalam" — langsung tugas
