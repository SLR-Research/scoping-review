# Modul 7: Data Charting untuk Scoping Review (Claude Cowork)

> **🎯 Output Modul Ini:** `charting.xlsx` lengkap berisi data setiap sumber INCLUDED, di-chart sesuai framework PCC, siap untuk mapping di Modul 8.

> **🤝 Workflow Modul Ini:** Lanjutan dari Modul 6 — gunakan **folder kerja yang sama** (`ScR_Project/` atau nama yang Anda pilih). Claude cowork akses PDF di `pdfs/`, generate charting form, isi `charting.xlsx` langsung.

> **📌 Perbedaan dari SLR:** Ini **CHARTING** (bukan extraction). Form-nya **iteratif** (Levac et al.) — boleh direvisi setelah pilot. Quality Assessment **OPSIONAL** dan non-exclusionary.

---

## **LANGKAH 0: PERLUASAN FOLDER KERJA (LANJUTAN MODUL 6)**

### **0.1 Tambahan Struktur Folder:**

```
ScR_Project/                       ← folder yang sama dari Modul 6
├── pdfs/                          ← PDF dari Modul 6 (sudah ada)
├── screening.xlsx                  ← dari Modul 6
├── pcc_definitions.md              ← dari Modul 6
├── reason_codes.md                 ← dari Modul 6
├── briefing.md                     ← dari Modul 6
├── charting_form.md                ← BARU — definisi kolom charting
├── charting.xlsx                   ← BARU — data charted
└── pilot_log.md                    ← BARU — log iterasi form (jika revisi)
```

> **📁 Catatan:** Jika di Modul 6 Anda pakai nama folder selain `ScR_Project/`, gunakan nama yang sama di Modul 7 — konsistensi lintas modul wajib.

### **0.2 Setup Tambahan via Cowork:**

```
Lanjutan dari Modul 6. Buat 2 file baru di folder kerja saya
[ScR_Project/ atau nama folder Anda]:

1. CREATE charting_form.md (kosong, akan diisi di L1)

2. CREATE charting.xlsx dengan struktur:

   Sheet "Charting":
   - Header meta (Row 1-5): Framework charting + canonical PCC + tanggal
   - Kolom data mulai Row 6 — kolom akan ditentukan setelah L1

   Sheet "Pilot_Log":
   - Tracking iterasi revisi form (kolom: Iterasi, Tanggal, Perubahan, Alasan)

   Sheet "Summary":
   - Auto-calculated: total sources charted, NR rate per kolom, peer/grey breakdown

3. Pre-populate Sheet "Charting" dengan baris untuk setiap source dari
   screening.xlsx yang Final_Decision=INCLUDE. Isi kolom meta dasar (ID,
   Source_Type, Author/Org, Year, DOI/URL, Document_Type) dari screening.xlsx.

VERIFY hasil + konfirmasi total INCLUDED rows yang sudah pre-populated.
No preamble.
```

### **0.3 Brief Awal Modul 7:**

```
Lanjut Modul 7 (Data Charting) di folder [nama folder Anda].

Konteks:
- Target charting: sources dengan Final_Decision=INCLUDE di screening.xlsx
- PDFs di pdfs/
- Standar: JBI Manual Ch.11 — ini CHARTING (iteratif), bukan extraction
- Quality Assessment: opsional dan non-exclusionary
- TIDAK ADA meta-analysis di ScR

Output kamu: tabel/bullet ringkas, no preamble, no narasi panjang.
Bahasa Indonesia.
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

## **LANGKAH 2: PILOT CHARTING (5-10 SUMBER) + REFINE FORM**

### **2.1 Eksekusi Pilot via Cowork:**

```
Pilot charting dengan 5-10 sumber sample.

1. Pilih 5-10 sources dari charting.xlsx (mix peer + grey, mix document types)
2. Untuk setiap source, baca PDF dari pdfs/, chart sesuai charting_form.md
3. Aturan charting:
   - Evidence-backed: kutip section reference untuk tiap field
   - [NOT REPORTED] jika info tidak ada (jangan mengira)
   - Konsisten dengan canonical terminology di pcc_definitions.md
   - [AMBIGUOUS: alasan] untuk field borderline
4. Isi langsung di Sheet "Charting" charting.xlsx
5. Output PILOT OBSERVATIONS:
   - Kolom mana yang sulit diisi / sering NR?
   - Kolom mana yang redundant atau overlap?
   - Ada info penting yang DISEBUT di sumber tapi TIDAK ADA kolomnya?
   - Apakah grey lit butuh kolom berbeda dari peer?

No preamble.
```

### **2.2 Refine Form (Berdasarkan Pilot):**

```
Berdasarkan pilot observations:
1. SARAN REVISI charting form (tambah/hapus/rephrase kolom)
2. Update charting_form.md dengan revisi
3. Update Sheet "Charting" charting.xlsx (tambah/hapus kolom sesuai)
4. Log perubahan ke Sheet "Pilot_Log":
   Iterasi | Tanggal | Perubahan | Alasan

No preamble.
```

> **💡 Iterative refinement** adalah prinsip Levac et al. Dokumentasi revisi = bukti rigor metodologis untuk Methods.

---

## **LANGKAH 3: FULL CHARTING (BATCH)**

### **Prompt Cowork:**

```
Chart sisa sources di charting.xlsx (yang belum terisi).

Batch 5-10 sumber sekaligus. Untuk setiap:
1. Baca PDF dari pdfs/
2. Chart sesuai charting_form.md (versi final pasca-pilot)
3. Aturan sama L2: evidence-backed, [NOT REPORTED] jujur, canonical terms,
   [AMBIGUOUS] untuk borderline
4. Isi langsung Sheet "Charting"

Output ringkas per batch:
- Jumlah sources di-chart
- NR rate per kolom (untuk monitoring)
- Daftar [AMBIGUOUS] yang butuh review manual

No preamble.
```

### **Verifikasi Manual (Spot-Check 20%):**

Peserta:
1. Pilih random 20% sources yang sudah di-chart
2. Buka PDF + bandingkan dengan baris di charting.xlsx
3. Cek akurasi 3 kolom kritis: Concept Operationalization, Context, Key Findings
4. Jika disagreement >20%: kembali ke L2, refine form lagi
5. Jika <20%: PROCEED

---

## **LANGKAH 4: OPTIONAL QUALITY APPRAISAL (DESKRIPTIF, NON-EXCLUSIONARY)**

### **4.1 Keputusan: Lakukan QA atau Tidak?**

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

### **4.2 Jika YES — Eksekusi QA via Cowork:**

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

### **4.3 Jika NO — Dokumentasikan Justifikasi:**

```
Generate paragraf 2-3 kalimat untuk Methods section, menjelaskan mengapa
QA tidak dilakukan. Rujuk JBI Manual + PRISMA-ScR item 12 (QA opsional
untuk ScR). Simpan sebagai qa_justification.md di folder kerja.
```

---

## **LANGKAH 5: MAPPING PREPARATION (BRIDGE KE MODUL 8)**

### **Prompt Cowork:**

```
Generate mapping preparation summary dari charting.xlsx.

Output ringkas (tabel + bullet, no narasi panjang):

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

Simpan output sebagai mapping_prep.md di folder kerja.
No preamble.
```

---

## **HASIL AKHIR**

```
=== CHARTING + (OPTIONAL) QA SUMMARY (ScR) ===

CHARTING FRAMEWORK: [JBI standard / PCC-driven / Thematic / Policy / Custom]
Justifikasi: [3-4 kalimat untuk Methods]

PILOT ITERATION:
- Sample size: [N]
- Revisions made: [list dari Sheet Pilot_Log]
- Final form version: v[X]

CHARTING EXECUTION:
- Total sources charted: [N] (peer: X, grey: Y)
- NR rate per kolom: [breakdown]
- Spot-check disagreement rate: [<20% / >20%]

OPTIONAL QA: [YES / NO]
Jika YES:
- Tool: [MMAT / AACODS / multi-tool]
- Distribusi: HIGH [N], MODERATE [N], LOW [N]
- NON-EXCLUSIONARY: ✓
Jika NO:
- Justifikasi (2-3 kalimat) di qa_justification.md

DESCRIPTIVE OVERVIEW: [tabel ringkas]
CATEGORICAL ANALYSIS: [kategori + frekuensi per kolom kunci]
PRELIMINARY GAP INVENTORY: [4 jenis gap]
RECOMMENDED MAPPING APPROACH: [verdict + justifikasi]

FORWARD ARTIFACTS (→ Modul 8):
- charting.xlsx (lengkap dengan QA jika ada)
- charting_form.md (versi final)
- mapping_prep.md (input untuk Modul 8)
- qa_justification.md (jika QA tidak dilakukan)

NEXT: Mapping + EGM (Modul 8) — gunakan folder kerja sama.
```

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
