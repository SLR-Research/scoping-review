# Modul 5: Title/Abstract Screening Scoping Review dengan GenAI

---

## **LANGKAH 1: FINALISASI INTERPRETASI KRITERIA + SCREENER BRIEFING**

> **🎯 Tujuan:** Bukan men-develop kriteria dari nol — kriteria PCC sudah ditetapkan di Modul 2 L3 dan di-embed di spreadsheet Modul 4 L3. Langkah ini memastikan **dua human reviewer berinterpretasi sama** sebelum mulai screening. Catatan khas ScR: interpretasi cenderung **lebih inklusif** daripada SLR karena tujuan mapping, tetapi harus tetap konsisten.

### **Prompt untuk Claude:**
```
Saya akan memulai title/abstract screening untuk Scoping Review dengan
2 human reviewer. Claude dipakai sebagai AI-assistant untuk membantu analisis,
TAPI keputusan final dan reporting semuanya HUMAN.

Paket kriteria yang sudah saya miliki:

=== DARI MODUL 2 L3 (PCC — bukan PICO) ===
Canonical terminology: [...]
P (Population): [operational def atau N/A — conceptual]
C (Concept):
  WHAT COUNTS: [...]
  WHAT DOESN'T: [...]
  EDGE CASES: [...]
C (Context):
  WHAT COUNTS: [...]
  WHAT DOESN'T: [...]
  EDGE CASES: [...]

=== DARI MODUL 4 L3 ===
Reason codes standar ScR: P-NOMATCH / C-CONCEPT-NOMATCH / C-CONTEXT-NOMATCH /
STUDY-DESIGN / LANGUAGE / DUPLICATE / NO-ABSTRACT / INACCESSIBLE / OTHER

Tolong bantu saya dua tugas:

=== TUGAS 1: VALIDASI KELENGKAPAN KRITERIA ===
Periksa apakah operational definitions sudah cukup kuat untuk screening ScR:
- Apakah WHAT COUNTS untuk Concept sudah eksplisit dan testable?
- Apakah WHAT COUNTS untuk Context sudah cukup spesifik tapi tidak terlalu restriktif?
- Apakah EDGE CASES cukup menangkap skenario borderline yang mungkin muncul?
- Apakah reason codes cukup komprehensif untuk semua alasan eksklusi plausible,
  termasuk untuk grey literature (INACCESSIBLE code)?

Jika ada gap → rekomendasikan tambahan/revisi yang akan di-update kembali
ke Modul 2 L3 (bukan di-patch ad-hoc di sini).

=== TUGAS 2: SCREENER BRIEFING DOCUMENT (ScR VERSION) ===
Buat briefing document 1-2 halaman yang akan jadi SATU sumber kebenaran
bagi dua human reviewer. Format:

---
SCREENER BRIEFING — [Judul proyek] — SCOPING REVIEW
Date: [YYYY-MM-DD]
Source of truth untuk: [Reviewer 1 name] & [Reviewer 2 name]
Standar: JBI Manual Ch.11 + PRISMA-ScR

1. CANONICAL TERMINOLOGY
   [Term kanonikal + definisi baku 1 kalimat dari Modul 2 L3]

2. OPERATIONAL DEFINITIONS (quick-reference cards)
   P: [WHAT COUNTS | WHAT DOESN'T | EDGE CASES] atau "N/A — conceptual"
   C (Concept): [...]
   C (Context): [...]

3. DECISION TREE UNTUK KASUS AMBIGU (ScR-biased)
   If Concept match AND Context match → INCLUDE
   If Concept match BUT Context marginal → INCLUDE (tag untuk sub-analisis)
   If Concept partial match AND Context match → INCLUDE, flag UNCERTAIN
   If Concept clear mismatch → EXCLUDE dengan C-CONCEPT-NOMATCH
   If Context clear mismatch → EXCLUDE dengan C-CONTEXT-NOMATCH
   If Abstract tidak cukup info → UNCERTAIN, defer ke full-text
   [dst — turunkan dari EDGE CASES]

   PRINSIP ScR: "When in doubt, INCLUDE for full-text review" — karena
   tujuan ScR memetakan LUAS, default ambiguity adalah UNCERTAIN/INCLUDE
   bukan EXCLUDE. Ini berbeda dari SLR.

4. REASON CODES (wajib dipakai, tidak boleh freeform)
   [list 9 reason codes ScR dari Modul 4 L3]

5. UNCERTAIN PROTOCOL
   - Jika cukup info di abstract tapi sulit decide → flag UNCERTAIN, catat notes
   - Jika abstract tidak cukup info → tandai "pending full-text" di Notes
   - TIDAK BOLEH decide INCLUDE/EXCLUDE tanpa alasan grounded di operational def
   - Untuk grey lit tanpa abstract formal, gunakan executive summary / first
     paragraph sebagai proxy

6. AI-ASSISTANT WORKFLOW (Claude sebagai tool, keputusan tetap human)
   Setiap reviewer boleh pakai Claude untuk record yang sulit:
   → Minta Claude berikan DUAL PERSPECTIVE (Inclusive-ScR + Restrictive)
   → Reviewer membaca analisis, lalu decide secara independen
   → Decision, Reason_Code, Notes = ditulis HUMAN reviewer
   → Claude tidak "menggantikan" judgment, hanya memperkaya pertimbangan

7. REPORTING STANDARD (untuk Methods manuskrip PRISMA-ScR)
   - Cohen's kappa dilaporkan antara Reviewer 1 (human) dan Reviewer 2 (human)
   - Claude usage dideklarasikan sebagai AI-assistance tool di Methods
     (sesuai standar integritas akademik — lihat Modul 1 Section C)
   - Screening flow mengikuti PRISMA-ScR flow diagram (Modul 4 L3 Sheet 4)

8. KHAS SCR: PERLAKUAN GREY LITERATURE
   - Grey lit di-screen dengan kriteria PCC sama, tetapi evaluasi "kualitas"
     TIDAK digunakan untuk eksklusi (JBI: QA opsional, non-exclusionary)
   - Grey lit yang tidak punya abstract formal boleh memakai executive
     summary / first paragraph sebagai basis screening
   - Jika grey lit tidak dapat diakses full-text → EXCLUDE dengan INACCESSIBLE
     code, catat URL + tanggal akses di Notes
---

Print briefing ini dan jadikan pegangan sebelum & selama screening.
```

> **💡 Tips Claude:** Screener Briefing Document adalah "contract" antara dua reviewer. Untuk ScR, briefing EKSPLISIT menyatakan prinsip "when in doubt, INCLUDE" — ini berbeda dari SLR dan sering menjadi sumber divergensi awal antar reviewer yang punya pengalaman SLR sebelumnya. Tanpa penegasan ini, reviewer SLR-trained cenderung over-exclude.

**Print briefing** dan pastikan kedua reviewer membacanya sebelum mulai kalibrasi.

---

## **LANGKAH 2: KALIBRASI DUAL-REVIEW (HUMAN) + COHEN'S KAPPA**

> **🎯 Tujuan:** Pastikan 2 human reviewer berinterpretasi sama SEBELUM commit ke batch massal. Kappa awal rendah → diperbaiki di kalibrasi jauh lebih murah daripada menemukan kappa akhir rendah saat sudah screening 500 records. Untuk ScR, kappa target bisa sedikit lebih longgar (≥0.60) karena inklusivitas cenderung meningkatkan UNCERTAIN.

### **Prosedur Kalibrasi:**

1. **Ambil 25 sample acak** dari screening database (Modul 4 L3). Rekomendasi komposisi: 15 peer-reviewed + 10 grey lit; dari total: 15 yang tampak clear + 10 yang tampak ambigu.
2. **Kedua reviewer screen 25 sample secara INDEPENDEN** (tidak saling melihat keputusan).
3. **Isi kolom Screener_1 / Screener_2** (Decision + Reason_Code + Notes) di spreadsheet.
4. **Formula Excel di Sheet "Kappa_Calculation"** akan auto-calculate kappa.

### **AI-Assistance per Reviewer (Optional tapi Direkomendasikan):**

Setiap reviewer dapat pakai Claude sebagai *dual-perspective tool* untuk record yang sulit. **Keputusan akhir tetap reviewer.**

```
Saya sedang screening untuk Scoping Review (JBI + PRISMA-ScR) dengan
operational definitions berikut (dari Screener Briefing):
[P WHAT COUNTS / WHAT DOESN'T / EDGE CASES]
[C (Concept) sama]
[C (Context) sama]
[Reason codes]

Prinsip ScR: default ambiguity = INCLUDE/UNCERTAIN, bukan EXCLUDE.

Record yang sedang saya evaluasi:
Source_Type: [PEER / GREY]
Title: [title]
Abstract/Summary: [abstract atau executive summary untuk grey lit]
Keywords: [keywords — boleh kosong]
Document_Type: [Article / Conference / Thesis / Report / Policy Brief / Preprint]

Berikan DUA perspektif (saya yang memutuskan akhir):

PERSPEKTIF INCLUSIVE-SCR (default ScR, INCLUDE saat ambigu):
- Argumen untuk INCLUDE: [...]
- Justifikasi berdasarkan WHAT COUNTS Concept + Context: [...]
- Apakah fit tujuan mapping ScR: [...]
- Kutipan abstract yang mendukung: [...]

PERSPEKTIF RESTRICTIVE (conservative, EXCLUDE saat ambigu):
- Argumen untuk EXCLUDE: [...]
- Reason code yang tepat jika EXCLUDE: [C-CONCEPT-NOMATCH / C-CONTEXT-NOMATCH / dll]
- Kutipan abstract yang mendukung eksklusi: [...]

VERDICT-AID (bukan keputusan saya):
- Apakah abstract punya info CUKUP untuk decide? [YES/NO]
- Key ambiguity (jika ada): [...]
- Komponen mana yang ambigu: [Concept / Context / keduanya]
- Jika dipaksa memilih (ScR-biased): INCLUDE / EXCLUDE / UNCERTAIN
```

Reviewer membaca kedua perspektif → membuat keputusan → mencatat sebagai Screener_[1/2]_Decision.

### **Evaluasi Kappa dengan Claude:**

Setelah kedua reviewer selesai 25 sample:

```
Hasil kalibrasi 25 sample:
[Upload spreadsheet atau paste tabel hasil]

Nilai kappa dari Sheet Kappa_Calculation: [X]

Analisis:

=== JIKA KAPPA ≥ 0.60 (substantial agreement) ===
- Konfirmasi: safe to proceed ke batch screening massal (Langkah 3)
- Dokumentasikan kappa awal + jumlah iterasi kalibrasi untuk Methods section

=== JIKA KAPPA < 0.60 ===
Lakukan root-cause analysis:

1. PATTERN DISAGREEMENT:
   - Records mana yang kedua reviewer berbeda?
   - Apakah disagreement dominan di komponen tertentu (P/C-Concept/C-Context)?
   - Apakah disagreement lebih banyak di PEER atau GREY records?
   - Apakah reason code berbeda meski keputusan sama (precision issue)?

2. AKAR MASALAH:
   - Operational def ambigu? Komponen mana yang perlu dipertajam?
   - Edge case yang belum tercover di briefing?
   - Personality bias (satu reviewer konsisten restrictive, satu konsisten inclusive)?
   - Grey lit interpretation bias (reviewer tidak nyaman dengan non-peer-reviewed)?

3. REKOMENDASI PERBAIKAN:
   - Revisi Screener Briefing (tambah/klarifikasi edge cases)
   - Diskusi 2 reviewer untuk disagreement cases → consensus → update interpretasi
   - Rerun kalibrasi dengan 25 sample BARU (bukan 25 yang sama)
   - Untuk grey lit bias: penegasan di briefing bahwa grey lit screened dengan
     kriteria PCC sama, kualitas bukan basis eksklusi

Iterasi sampai kappa ≥ 0.60.
```

> **💡 Tips Claude:** Jangan shortcut kalibrasi. Kalau kappa pertama 0.45, godaannya "ya lanjut aja" — tapi ini akan menghasilkan kappa akhir rendah, reviewer jurnal akan minta re-screening. Lebih hemat 2-3 iterasi kalibrasi di awal. Khusus ScR: jika sub-analisis menunjukkan kappa grey lit jauh lebih rendah dari peer, ini sinyal reviewer butuh briefing tambahan tentang perlakuan grey lit.

**Proceed ke Langkah 3 HANYA jika kappa kalibrasi ≥ 0.60.** Dokumentasikan kappa + jumlah iterasi untuk Methods.

---

## **LANGKAH 3: BATCH SCREENING MASSAL (AI-ASSISTED, HUMAN-DECIDED)**

### **Workflow per Reviewer:**

> **🚀 Fitur Claude:** Upload screening database langsung — Claude dapat batch-process 50-100 records sekaligus dengan dual-perspective analysis. Keputusan final tetap human.

```
[Upload spreadsheet Modul 4 L3 — Screening database]

Saya adalah Reviewer [1 atau 2] untuk Scoping Review ini.
Saya sudah membaca Screener Briefing dan kalibrasi kappa sudah lolos (κ=[X]).
Standar: JBI + PRISMA-ScR. Prinsip: when in doubt, INCLUDE/UNCERTAIN.

Screener Briefing (ringkas):
[Canonical terminology]
[P WHAT COUNTS / WHAT DOESN'T / EDGE CASES]
[C Concept / C Context operational defs]
[Reason codes: list 9 ScR codes]

Tolong proses records dari ID [start] sampai [end].

Untuk SETIAP record, berikan:

1. DUAL-PERSPECTIVE ANALYSIS:
   - Inclusive-ScR argument (untuk INCLUDE)
   - Restrictive argument (untuk EXCLUDE)
   - Key ambiguity jika ada (Concept / Context / keduanya)

2. RECOMMENDATION (rekomendasi, bukan keputusan final):
   - INCLUDE / EXCLUDE / UNCERTAIN
   - Reason code yang paling tepat (dari 9 ScR codes)
   - Key evidence: kutipan singkat dari abstract/summary
   - Confidence level: HIGH / MEDIUM / LOW
   - Source_Type note: apakah grey lit perlu perlakuan khusus?

Format output tabel:
| ID | Source_Type | Title (singkat) | Inclusive | Restrictive | Recommend | Reason Code | Evidence | Confidence |

CATATAN PENTING:
- Keputusan FINAL adalah saya (human) — saya akan review output Anda
- Lalu saya isi kolom Screener_[X]_Decision / Reason_Code / Notes di spreadsheet
- Record dengan Confidence = LOW → saya kemungkinan besar akan re-read abstract
- Record dengan Recommend = UNCERTAIN → saya pertimbangkan defer ke full-text
- Untuk grey lit dengan info terbatas, default ke UNCERTAIN jika ada sinyal relevansi
```

### **Alur Keputusan Human per Record:**

1. Baca Claude's dual-perspective + recommendation + confidence
2. **Baca abstract/summary original** (minimal untuk confirm Claude's paraphrase akurat — Claude bisa hallucinate)
3. Put keputusan di Screener_[X]_Decision — **ini Anda, bukan Claude**
4. Isi Reason_Code dari 9 standard ScR codes + Notes
5. Jika UNCERTAIN: flag untuk diskusi atau defer ke full-text

### **Kedua Reviewer Bekerja Independently:**

- Reviewer 1 isi Screener_1_* (bisa dibantu Claude)
- Reviewer 2 isi Screener_2_* (independen — TIDAK melihat Reviewer 1 sampai selesai)
- Setelah kedua selesai → Agreement column auto-calculate

### **Resolve Disagreements + UNCERTAIN:**

```
Hasil dual-review batch massal:
- DISAGREE cases: [N] records
- UNCERTAIN cases (either reviewer): [N] records

[Paste atau upload tabel kasus-kasus tsb]

Analisis:

1. PATTERN DISAGREEMENT:
   - Apakah ada pola? (selalu di komponen sama? edge case jenis tertentu?
     peer vs grey?)
   - Apakah ini sinyal drift interpretasi?

2. UNCERTAIN CASES:
   - Apakah info di abstract cukup, atau butuh full-text?
   - Mana yang bisa diputuskan via dual-perspective analysis lagi?
   - Untuk ScR, mayoritas UNCERTAIN seharusnya deferred ke full-text
     (prinsip inklusivitas)

3. STRATEGI RESOLUSI per kasus:
   - DISCUSS: kedua reviewer diskusi → consensus → update Conflict_Resolution
   - DEFER-TO-FULLTEXT: tandai untuk keputusan di Modul 6 (default ScR untuk
     UNCERTAIN dengan sinyal relevansi)
   - UPDATE-BRIEFING: jika pattern disagreement menunjukkan gap operational def,
     update Modul 2 L3 + regenerasi briefing
```

Isi `Conflict_Resolution` untuk DISAGREE cases. UNCERTAIN → sebagian besar deferred ke Modul 6 (ScR-style).

### **Monitor Kappa Real-Time:**

Sheet Kappa_Calculation update otomatis setiap record terisi. Target: kappa tetap ≥ 0.60 sampai akhir. Jika drop signifikan → **pause**, investigasi drift interpretasi, re-briefing dan lanjut.

---

## **LANGKAH 4: REVIEW HASIL + EXCLUSION TABLE + FULL-TEXT PREP**

### **Aggregate Exclusion Reasons dengan Claude:**

```
[Upload spreadsheet final screening]

Tolong agregasi hasil screening untuk siap-Methods PRISMA-ScR:

=== 1. FLOW NUMBERS (untuk PRISMA-ScR diagram di Modul 9) ===
- Records identified from databases (peer-reviewed): [N] breakdown per DB
- Records identified from other sources (grey lit): [N] breakdown per source
- Duplicates removed: [N]
- Records screened (title/abstract): [N]
- Records excluded at screening: [N]
- Records sought for retrieval (INCLUDE + UNCERTAIN deferred): [N]

=== 2. EXCLUSION REASONS TABLE ===

Agregasi Reason_Code untuk semua EXCLUDE. Format siap-appendix:

| Reason Code | Count | % | Deskripsi |
|-------------|-------|---|-----------|
| P-NOMATCH | X | Y% | Population tidak sesuai (jika applicable) |
| C-CONCEPT-NOMATCH | X | Y% | Concept tidak sesuai operational def |
| C-CONTEXT-NOMATCH | X | Y% | Context tidak sesuai (geografis/setting/temporal) |
| STUDY-DESIGN | X | Y% | Tipe sumber di luar kriteria |
| LANGUAGE | X | Y% | Bahasa di luar filter |
| DUPLICATE | X | Y% | Duplikat yang baru terdeteksi di screening |
| NO-ABSTRACT | X | Y% | Abstract/summary tidak tersedia |
| INACCESSIBLE | X | Y% | Grey lit tidak dapat diakses |
| OTHER | X | Y% | (ringkas notes) |

Tabel ini masuk ke APPENDIX manuskrip + PRISMA-ScR flow diagram.

=== 3. KAPPA REPORT (siap-Methods) ===
- Kappa kalibrasi iterasi 1: [nilai]
- Jumlah iterasi kalibrasi: [N]
- Kappa kalibrasi final: [nilai ≥0.60]
- Kappa seluruh screening batch massal: [nilai]
- Sub-kappa PEER vs GREY (jika berbeda signifikan): [breakdown]
- Klasifikasi: [Fair/Moderate/Substantial/Almost Perfect]
- Jumlah disagreements: [N]
- Resolved via discussion → consensus: [N]
- Deferred ke full-text: [N]

=== 4. PCC-CONSISTENCY POST-SCREENING AUDIT ===

Ambil random 10% dari INCLUDED records (proporsional peer vs grey).
Baca judul+abstract + Reason_Code, verifikasi:
- Apakah keputusan INCLUDE konsisten dengan WHAT COUNTS di operational def PCC?
- Ada keputusan yang mungkin "slipped through" dan seharusnya EXCLUDE?
- Apakah perlakuan peer vs grey konsisten?

Jika ditemukan "slipped through" → flag untuk re-screening oleh reviewer lain.

=== 5. FULL-TEXT PRIORITIZATION (ScR) ===

Untuk INCLUDED + UNCERTAIN deferred records, klasifikasi ke 3 tier:

- HIGH priority: clearly match semua komponen PCC berdasar abstract
- MEDIUM priority: match sebagian besar, butuh full-text untuk verify
- LOW priority: UNCERTAIN atau deferred — full-text untuk disambiguate

Tambahan untuk ScR: sub-klasifikasi berdasarkan Source_Type
- Peer-reviewed → retrieval via library/DB/publisher
- Grey lit → retrieval via URL direct (pastikan URL masih aktif)

Output: 3 list siap dipakai di Modul 6.
```

### **Output untuk Modul 6:**

- Total INCLUDED + UNCERTAIN deferred list dengan priority tag
- Exclusion reasons table (Methods-ready)
- Kappa report (Methods-ready)
- PRISMA-ScR flow numbers updated
- Unresolved UNCERTAIN cases dengan catatan ambiguity

---

## **HASIL AKHIR**

### **Title/Abstract Screening Summary ScR (v1):**
```
=== TITLE/ABSTRACT SCREENING RESULTS (ScR) ===

KALIBRASI:
- Sample size: 25 records (15 peer + 10 grey)
- Jumlah iterasi: [N]
- Kappa iterasi 1: [X]
- Kappa lolos (iterasi final): [X ≥0.60]
- Revisi briefing selama kalibrasi: [ringkasan perubahan]

BATCH SCREENING:
- Total records screened: [N]
  - Peer-reviewed: [N]
  - Grey literature: [N]
- Screener_1 complete: [Y/N]
- Screener_2 complete: [Y/N]
- Agreement rate: [%]
- Final kappa: [X]
  - Sub-kappa peer: [X]
  - Sub-kappa grey: [X]
- AI-assistance (Claude) usage: [dideklarasikan di Methods]

DECISIONS:
- INCLUDE for full-text: [N] ([%])
  - Peer: [N], Grey: [N]
- EXCLUDE: [N] ([%])
- UNCERTAIN (deferred ke full-text): [N] ([%])

DISAGREEMENT RESOLUTION:
- Total disagreements: [N]
- Resolved via discussion → consensus: [N]
- Resolved via full-text deferral: [N]

EXCLUSION REASONS TABLE (→ Methods appendix, PRISMA-ScR flow):
[tabel lengkap dari L4]

PCC-CONSISTENCY AUDIT:
- Random sample size: [N = 10% of INCLUDED, proporsional peer vs grey]
- Slipped-through records found: [N]
- Action taken: [re-screening / none]

KAPPA REPORT (→ Methods):
- Initial (iterasi 1): [X]
- Final (seluruh batch): [Y]
- Classification: [Substantial / Almost Perfect]

PRISMA-ScR FLOW UPDATE:
- Identification: [total per source]
- Screening: [N screened, N excluded]
- Next stage (Eligibility): [N sought for retrieval]

FULL-TEXT PREPARATION (→ Modul 6):
- HIGH priority: [N records] (peer: [N], grey: [N])
- MEDIUM priority: [N records]
- LOW priority (UNCERTAIN): [N records]

FORWARD ARTIFACTS:
- Date stamp: [dari Modul 3 L4]
- Canonical terminology: [dari Modul 2 L3]
- Operational definitions PCC: [dari Modul 2 L3]
- Prioritized INCLUDED + UNCERTAIN list
- Exclusion reasons table
- Kappa report
- Methods-ready kalimat tentang AI-assistance declaration
```

---

## **TROUBLESHOOTING**

**Problem 1: Kappa awal terlalu rendah (<0.40, "Fair" atau lebih buruk)**
- Root cause paling umum: operational definitions PCC di Modul 2 L3 terlalu samar
- Lihat pattern disagreement — apakah dominan di Concept atau Context? → tajamkan komponen itu di Modul 2 L3 + regenerate Screener Briefing
- Jika disagreement tersebar → briefing kurang jelas untuk edge cases, perluas decision tree
- ScR-specific: cek apakah salah satu reviewer masih berpikiran SLR (over-exclude karena ambigu) vs ScR (default INCLUDE saat ambigu)

**Problem 2: Kappa stuck di Moderate (0.41-0.60) setelah beberapa iterasi**
- Diskusi consensus per case — bukan hanya "kenapa beda", tapi "dari perspektif kriteria PCC, yang benar yang mana"
- Ada kemungkinan operational def memang punya inherent ambiguity — pertimbangkan terima & dokumentasi di Limitations
- Alternatif: rekrut 3 reviewer (majority vote untuk disagreement cases)
- Untuk ScR dengan grey lit tinggi, pertimbangkan menerima kappa 0.55-0.60 asalkan ada prosedur resolve yang robust

**Problem 3: Banyak UNCERTAIN cases (>25% dari total)**
- Untuk ScR, UNCERTAIN rate lebih tinggi WAJAR karena prinsip "when in doubt, defer to full-text"
- Protokol: tandai UNCERTAIN untuk deferral ke full-text — wajar dan OK
- Jika >50%: cek apakah search string terlalu broad (balik ke Modul 3 L3) atau operational def terlalu samar (Modul 2 L3)

**Problem 4: Pola disagreement "systematic" antara 2 reviewer**
- Contoh: Reviewer 1 konsisten restrictive (SLR mindset), Reviewer 2 konsisten inclusive (ScR mindset)
- Ini personality/training bias — butuh diskusi eksplisit tentang prinsip ScR
- Update Screener Briefing: tetapkan default (mis. "for ScR, genuinely ambiguous = UNCERTAIN/defer, bukan EXCLUDE")

**Problem 5: Claude's recommendation sering berbeda dari human decision**
- Normal — Claude tidak punya domain expertise Anda
- Audit apakah Claude's reasoning grounded di operational def PCC yang benar (atau hallucinate)
- Jika Claude konsisten miss interpretasi kriteria tertentu → update prompt dengan contoh kasus eksplisit
- **JANGAN paksa alignment** — Claude sebagai tool, bukan authority

**Problem 6: Kappa drop mid-batch (misal awal 0.75, turun jadi 0.58 setelah 200 records)**
- Sinyal **drift interpretasi** — reviewer mulai divergen seiring fatigue atau interpretasi bergeser
- Pause batch
- Re-read Screener Briefing
- Diskusi 20-30 records terakhir yang DISAGREE
- Jika perlu, refresh briefing + lanjut

**Problem 7: Grey lit kappa jauh lebih rendah dari peer-reviewed kappa**
- Khas ScR — reviewer sering tidak nyaman dengan format non-peer-reviewed
- Briefing tambahan: grey lit di-screen dengan kriteria PCC sama; kualitas TIDAK basis eksklusi
- Jika grey lit kappa <0.50: kalibrasi tambahan dengan 15-20 grey lit sample saja
- Dokumentasikan sub-kappa di Methods sebagai transparansi

**Problem 8: Banyak grey lit EXCLUDED dengan INACCESSIBLE**
- Catat URL + tanggal akses di Notes
- Pertimbangkan request via ResearchGate, email author, atau interlibrary loan sebelum final EXCLUDE
- Untuk transparansi PRISMA-ScR, laporkan N "reports not retrieved" dengan breakdown reasons

---
