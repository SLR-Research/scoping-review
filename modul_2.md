# Modul 2: Perumusan Research Question Scoping Review dengan GenAI

---

## **LANGKAH 1: TENTUKAN TOPIK PENELITIAN + KLASIFIKASI TIPE GAP (SCR-SPECIFIC)**

### **Prompt untuk Claude:**
```
Saya seorang peneliti di bidang [sebutkan bidang spesifik, misal: teknologi pendidikan].

Saya tertarik pada area [sebutkan area yang diminati, misal: penggunaan generative AI
dalam pembelajaran perguruan tinggi, dsb].

Saya berencana melakukan SCOPING REVIEW (bukan SLR) mengikuti pedoman
JBI Manual Chapter 11 + PRISMA-ScR.

Gunakan web search untuk:
1. Cari scoping review terbaru (3 tahun terakhir) di bidang ini
2. Cek evidence gap map yang sudah ada pada topik terkait
3. Identifikasi apakah topik yang saya minati sudah pernah di-scope secara sistematis
4. Cek juga SLR terbaru yang mungkin menunjukkan heterogenitas bukti tinggi
   (indikator bagus bahwa ScR diperlukan sebagai prekursor / komplementer)

Berdasarkan hasil pencarian, suggest 3 topik penelitian yang:
1. Memiliki gap yang sesuai dengan tujuan ScR (Munn et al., 2018):
   - Memetakan jenis bukti yang tersedia
   - Mengklarifikasi konsep/definisi kunci
   - Mengkaji bagaimana penelitian dilakukan
   - Memetakan karakteristik kunci
   - Mengidentifikasi gap untuk riset selanjutnya
   - Prekursor sebelum SLR
2. Cocok untuk scoping review (bukan SLR) — literatur heterogen, konsep masih ambigu,
   atau belum pernah dipetakan
3. Relevan dengan praktik/kebijakan saat ini

Untuk setiap gap, KLASIFIKASIKAN ke salah satu tipe berikut
(penting untuk argumentasi Introduction nanti):

- TIPE A — FRAGMENTASI PEMETAAN: studi-studi tersebar di berbagai disiplin/database
  tanpa pemetaan sistematis; jenis dan sebaran bukti belum diketahui utuh.
- TIPE B — AMBIGUITAS KONSEPTUAL: konsep kunci didefinisikan dengan beragam cara
  di literatur; belum ada tinjauan yang mengklarifikasi.
- TIPE C — KETIADAAN KARAKTERISASI METODOLOGIS: belum ada tinjauan yang mengkaji
  bagaimana riset dilakukan pada topik ini (desain, populasi, konteks, setting).
- TIPE D — PREKURSOR UNTUK SLR: bukti heterogen atau belum matang untuk SLR;
  ScR dibutuhkan sebagai langkah awal untuk memetakan lanskap.

Format output:
TOPIK 1: [nama topik]
- Gap: [research gap yang ditemukan dari web search]
- Tipe gap: [A / B / C / D] — penjelasan singkat mengapa masuk tipe tsb
- Bukti gap: [referensi/sumber dengan DOI atau URL jika ada]
- Mengapa ScR (bukan SLR)?: [justifikasi pilih ScR dengan merujuk Munn et al. 2018]
- Mengapa penting: [alasan urgensi]

TOPIK 2: [...]
TOPIK 3: [...]
```

> **💡 Tips Claude:** Klasifikasi tipe gap bukan kosmetik — tiap tipe menuntut *angle argumentasi* yang berbeda di Introduction. Tipe A → "memetakan yang tersebar"; Tipe B → "mengklarifikasi konsep yang ambigu"; Tipe C → "mengkarakterisasi lanskap metodologis"; Tipe D → "persiapan SLR berikutnya". Reviewer ketat akan menolak Intro yang hanya "topik penting, gap ada" tanpa tipe yang jelas, apalagi ScR yang membutuhkan justifikasi pilihan ScR-vs-SLR di awal.

**Pilih 1 topik** yang paling sesuai dengan minat, expertise, dan tujuan pemetaan.

---

## **LANGKAH 2: REVIEW OF PRIOR SCOPING/SYSTEMATIC REVIEWS (MATRIKS)**

> **🎯 Tujuan:** Bangun matriks komparatif scoping review dan SLR terdahulu yang terdekat dengan topik Anda. Matriks ini menjadi bahan **subseksi "Review of Prior Reviews"** di Introduction manuskrip. Tanpa matriks ini, klaim *novelty* ScR akan dipertanyakan reviewer — apalagi ScR rentan dituduh "overlap dengan ScR lain".

### **Prompt untuk Claude:**
```
Topik penelitian saya: [topik yang dipilih dari Langkah 1]
Tipe gap: [A/B/C/D dari Langkah 1]
Jenis review: Scoping Review (JBI + PRISMA-ScR)

Gunakan web search untuk mengidentifikasi 3-5 review TERDEKAT dengan topik saya
(5-10 tahun terakhir), dengan prioritas:
1. Scoping review pada topik sama atau beririsan
2. Evidence gap map yang sudah ada
3. Systematic review yang menunjukkan heterogenitas bukti tinggi
4. Mapping review atau rapid review terkait

Untuk setiap review, bangun matriks dengan kolom:

| # | Author (Year) | Jenis Review (ScR/SLR/Map/Rapid) | PCC/PICO yang dipakai | Scope (Population, Concept, Context, Period) | Methodology (DB, grey lit, charting/extraction, QA?) | Key Findings | Gap yang disebut | Selisih dengan ScR saya |

Kolom "Selisih dengan ScR saya" HARUS eksplisit menunjukkan salah satu atau kombinasi:
- BEDA POPULATION: [apa bedanya]
- BEDA CONCEPT: [konsep yang mereka petakan vs yang saya petakan]
- BEDA CONTEXT: [konteks geografis/setting/kultural yang berbeda]
- BEDA PERIODE: [periode review vs periode saya]
- BEDA METODE: [mis. mereka tidak pakai JBI 9-stage, atau tanpa grey lit]
- BEDA TIPE SUMBER: [mis. mereka hanya peer-reviewed, saya juga grey lit]
- BEDA TUJUAN: [mis. mereka mapping saja, saya gap identification]

Setelah matriks, tuliskan 1 paragraf (150-200 kata) bertajuk "SINTESIS NOVELTY"
yang merangkum: apa yang SUDAH dipetakan prior reviews kolektif, apa yang BELUM
atau butuh update, dan mengapa ScR saya MENUTUP gap yang tersisa.

Jika hanya ada 1-2 prior reviews, sampaikan apa adanya — jangan dipaksakan ke 5.
Jika tidak ada scoping review sama sekali pada topik ini, itu JUSTRU kekuatan
novelty — catat eksplisit "No prior scoping review identified" dan tunjukkan
SLR/narrative review terdekat sebagai titik banding.

Catatan penting: Jika ada scoping review yang SANGAT mirip publish <2 tahun,
pertimbangkan mengubah arah (beda Context, Population, atau update temporal)
alih-alih memaksakan novelty semu.
```

> **💡 Tips Claude:** Matriks ini punya dua fungsi: (1) input langsung ke Introduction di Modul 9; (2) amunisi untuk *response letter* saat reviewer berkomentar "overlaps with existing scoping review". Simpan outputnya — akan terpakai dua kali.

**Simpan matriks** dalam format tabel (Word/Excel). Akan direferensi sampai tahap penulisan manuskrip.

---

## **LANGKAH 3: PCC FRAMEWORK + DEFINISI OPERASIONAL + TERMINOLOGI KANONIKAL**

### **Prompt untuk Claude:**
```
Topik penelitian saya: [topik yang dipilih dari Langkah 1]
Tipe gap: [A/B/C/D]
Prior reviews matrix: [ringkasan atau upload matriks dari Langkah 2]

Bantu saya buat PCC framework YANG TAJAM (standar JBI untuk scoping review),
dengan 3 lapisan:

=== LAPISAN 1: PILIHAN PCC ===

P (Population): Siapa/apa partisipan atau kelompok target?
   Catatan: Population OPSIONAL untuk ScR konseptual — jika tidak relevan,
   tandai "Not applicable — conceptual scoping" dengan justifikasi.

C (Concept): Konsep sentral apa yang akan dipetakan?
   Ini WAJIB dan menjadi inti ScR. Bisa berupa: teori, fenomena, praktik,
   intervensi, metodologi, kebijakan.

C (Context): Konteks spesifik apa yang membatasi tinjauan?
   Geografis (negara/region), setting (sekolah/klinik/komunitas), kultural,
   kebijakan, atau temporal.

=== LAPISAN 2: DEFINISI OPERASIONAL (untuk tiap P/C/C) ===

Untuk setiap komponen, tuliskan:
- WHAT COUNTS: kriteria eksplisit yang MEMBUAT sebuah studi memenuhi komponen ini
- WHAT DOESN'T COUNT: kriteria eksplisit yang MENGGUGURKAN
- EDGE CASES: kasus borderline dengan keputusan default (include/exclude + alasan)

Contoh untuk Concept "generative AI dalam pembelajaran":
  WHAT COUNTS: penggunaan LLM (ChatGPT, Claude, Gemini, Copilot) atau tool berbasis
    LLM oleh dosen/mahasiswa untuk aktivitas belajar-mengajar formal
  WHAT DOESN'T: AI klasik non-generatif (rule-based tutoring system, adaptive
    learning tanpa LLM); penggunaan generative AI di luar konteks pembelajaran
    (administrasi, riset dosen non-pengajaran)
  EDGE CASES:
    - ChatGPT dipakai mahasiswa untuk plagiarisme → INCLUDE (masih dalam
      konteks pembelajaran, meski etis bermasalah)
    - AI detection tool (Turnitin AI) → INCLUDE jika studi membahas dampaknya
      ke pembelajaran; EXCLUDE jika hanya evaluasi teknis akurasi deteksi
    - Embedded AI di LMS (Canvas, Moodle) → INCLUDE jika fitur generatif aktif

=== LAPISAN 3: TERMINOLOGI KANONIKAL ===

Untuk komponen Concept (dan Population jika ada), pilih SATU istilah kanonikal
yang akan dipakai konsisten di seluruh manuskrip.

Format:
- Kanonikal: "[term]"
- Definisi baku 1 kalimat: [definisi]
- Alternatif yang DITOLAK: [list alternatif + alasan singkat mengapa ditolak]

Contoh:
- Kanonikal: "generative AI-assisted learning"
- Definisi baku: Penggunaan large language model (LLM) atau tool berbasis LLM
  oleh dosen atau mahasiswa perguruan tinggi untuk mendukung aktivitas
  pembelajaran formal (kurikuler maupun ko-kurikuler).
- Alternatif yang DITOLAK:
  · "AI in education" → terlalu luas, mencakup AI non-generatif
  · "ChatGPT for learning" → terlalu sempit, hanya 1 platform
  · "AI literacy" → berbeda fokus (kompetensi user, bukan aktivitas pembelajaran)

=== CEK KHUSUS UNTUK SCR ===

PENTING: ScR berbeda dari SLR — pastikan:
1. Concept DIUTAMAKAN, bukan Intervention-Outcome
2. Definisi operasional CUKUP JELAS untuk screening, tapi TIDAK TERLALU SEMPIT
   sehingga mengeksklusi keragaman bukti yang ingin dipetakan
3. Jangan formulasikan sebagai "Intervention → Outcome" — itu PICO, bukan PCC

Output harus READY untuk dipakai langsung sebagai INCLUSION CRITERIA di Modul 5.
```

> **💡 Tips Claude:** Banyak peneliti pemula membuat ScR tetapi merumuskan dengan PICO — reviewer JBI/PRISMA-ScR akan langsung menandai ini sebagai kesalahan fundamental. Jika Claude menawarkan format "Intervention-Comparison-Outcome", hentikan dan minta ulang dalam format PCC. Investasi ekstra 15 menit di sini menghindari revisi metodologis mayor di Modul 5-6.

---

## **LANGKAH 4: JUSTIFIKASI BATASAN SCOPE**

> **🎯 Tujuan:** Untuk tiap batasan yang Anda tetapkan (population, rentang tahun, context, bahasa, tipe sumber bukti), rumuskan justifikasi 3-lapis yang bisa langsung disalin ke Introduction. Reviewer akan menolak batasan yang tampak arbitrer, dan ScR secara khusus rentan dikritik "terlalu luas" atau "terlalu sempit".

### **Prompt untuk Claude:**
```
Berdasarkan PCC dan definisi operasional dari Langkah 3:

P: [...] (atau "N/A — conceptual scoping")
C (Concept): [...]
C (Context): [...]

Batasan-batasan yang saya tetapkan:
- Rentang tahun publikasi: [mis. 2020-2025]
- Batasan geografis: [mis. global / Asia Tenggara / Indonesia]
- Batasan setting (jika ada): [mis. perguruan tinggi / pendidikan vokasi]
- Batasan bahasa publikasi: [mis. English / English + Bahasa Indonesia]
- Tipe sumber bukti: [mis. peer-reviewed + grey literature / only peer-reviewed]
- Batasan lain: [mis. hanya studi empiris / termasuk konseptual-teoretis]

Untuk SETIAP batasan, bangun justifikasi 3-lapis:

1. JUSTIFIKASI TEORETIS
   Apa landasan konseptual/teoretis batasan ini?
   Contoh: 2020-2025 → era pasca rilis publik ChatGPT (November 2022) yang
   secara struktural mengubah lanskap generative AI; studi pra-2020 kurang
   komparabel. Atau: konteks perguruan tinggi Indonesia → merujuk UU
   Pendidikan Tinggi No.12/2012 + Permendikbudristek.

2. JUSTIFIKASI METODOLOGIS
   Mengapa batasan ini memperbaiki kualitas scoping review?
   Contoh: inklusi grey literature → direkomendasikan JBI ketika laporan
   lembaga/kebijakan signifikan untuk topik (bukan wajib, tapi memperkaya
   peta bukti). Atau: batasan bahasa Indonesia + English → feasible untuk tim
   + tidak mengeksklusi literatur lokal yang signifikan.

3. JUSTIFIKASI PRAKTIS
   Apa relevansi kebijakan/praktik dari batasan ini?
   Contoh: fokus perguruan tinggi Indonesia → relevansi Permendikbudristek
   tentang integrasi AI di kurikulum, agenda Kampus Merdeka, dan keputusan
   konsorsium perguruan tinggi 2024.

Gunakan web search untuk MEMVERIFIKASI klaim teoretis
(mis. tanggal rilis ChatGPT yang tepat, nomor/tahun Permendikbudristek,
dokumen kebijakan yang diacu).

Format output:
=== JUSTIFIKASI BATASAN SCOPE ===

BATASAN 1: [nama batasan, mis. "Rentang tahun 2020-2025"]
- Teoretis: [150-200 kata dengan sitasi yang terverifikasi]
- Metodologis: [100-150 kata]
- Praktis: [100-150 kata]

BATASAN 2: [...]
[dst untuk setiap batasan]

CATATAN KHUSUS ScR — PRINSIP ITERATIF:
Jika di Modul 5-6 nanti Anda menemukan bahwa suatu batasan membuat review
terlalu sempit atau melewatkan bukti penting, JBI/Levac membenarkan revisi
batasan — asalkan didokumentasikan sebagai "post-hoc refinement" dengan alasan.
Tandai batasan yang berpotensi iteratif dengan label [ITERATIVE] di bawah.

Output ini akan dimasukkan ke Introduction manuskrip (Modul 9).
```

> **💡 Tips Claude:** Jika Anda tidak bisa menuliskan justifikasi meyakinkan untuk salah satu batasan, itu sinyal bahwa batasan tsb perlu **diubah atau dihapus**. Batasan yang bertahan hanya yang lolos argumen 3-lapis — ini akan menjadi perisai terhadap kritik "scope arbitrer" dari reviewer. Untuk ScR, keputusan tentang tipe sumber (termasuk/tidak termasuk grey literature) wajib dijustifikasi secara eksplisit di Methods, baik keputusannya inklusif maupun restriktif.

---

## **LANGKAH 5: FORMULASIKAN RESEARCH QUESTION (SCR STYLE)**

### **Prompt untuk Claude:**
```
Berdasarkan pondasi yang sudah dibangun:

- Tipe gap (L1): [A/B/C/D + deskripsi]
- Prior reviews matrix (L2): [ringkasan kolom "selisih"]
- PCC + definisi operasional (L3): [ringkasan]
- Justifikasi scope (L4): [poin-poin kunci]

Tolong formulasikan Research Questions GAYA SCR — berbeda dari SLR,
ScR RQ umumnya berbentuk "what/how/which" untuk pemetaan, BUKAN
"does X cause Y" atau "is X more effective than Y":

1. PRIMARY RESEARCH QUESTION yang jelas, fokus, dan dapat dijawab scoping review.
   Contoh bentuk:
   - "What is known about [Concept] in [Context]?"
   - "How is [Concept] defined/operationalized in [Context]?"
   - "What types of [Population] have been studied in relation to [Concept]?"
   - "What methods are used to study [Concept] in [Context]?"
   - "What gaps exist in the literature on [Concept]?"

2. 3 SECONDARY QUESTION yang mendukung primary. Umumnya mengcover aspek:
   - Karakteristik studi (desain, populasi, setting)
   - Definisi/konseptualisasi yang digunakan
   - Temuan utama yang dipetakan
   - Gap yang teridentifikasi

3. GAP-RQ TRACEABILITY: untuk primary + setiap secondary, tunjukkan 3 jejak:
   (a) Menjawab gap apa (trace ke Tipe A/B/C/D dan deskripsi gap di L1)
   (b) Berbeda dari prior reviews di aspek apa (trace ke kolom "selisih" di L2)
   (c) Dapat dijawab dengan PCC + definisi operasional saya (trace ke L3)

Format output:

PRIMARY RQ: [question]
  → Menjawab gap: [referensi ke tipe gap + deskripsi dari L1]
  → Selisih dari prior reviews: [referensi ke entri matriks L2]
  → Answerable via PCC: [komponen PCC yang menyediakan data untuk menjawab]

SECONDARY RQ 1: [question]
  → Menjawab gap: [...]
  → Selisih dari prior reviews: [...]
  → Answerable via PCC: [...]

SECONDARY RQ 2: [...]
SECONDARY RQ 3: [...]

PERINGATAN:
- Jika ada RQ yang TIDAK bisa ditrace ke salah satu dari 3 elemen,
  TANDAI sebagai "RQ-orphan" — akan dibuang atau direvisi sebelum lanjut.
- Jika ada RQ yang berbentuk "apakah X efektif?" atau "apakah X menyebabkan Y?",
  TANDAI sebagai "RQ-SLR-style" — itu bukan RQ ScR, harus direformulasi.
```

**Evaluasi** apakah semua RQ lolos traceability dan bergaya ScR. RQ-orphan atau RQ-SLR-style harus diperbaiki sebelum lanjut ke Langkah 6.

---

## **LANGKAH 6: CEK KUALITAS DENGAN FINER + NOVELTY GAP vs PRIOR REVIEWS**

### **Prompt untuk Claude:**
```
Research questions saya:
Primary: [primary RQ dari Langkah 5]
Secondary: [3 secondary RQs]

Paket pendukung:
- Prior reviews matrix (L2): [matriks lengkap]
- PCC + definisi operasional (L3): [ringkasan]
- Justifikasi scope (L4): [ringkasan]

Evaluasi dengan FINER criteria (disesuaikan untuk ScR):

F - FEASIBLE
- Bisa dijawab dengan scoping review mengingat ketersediaan studi + grey lit?
- Gunakan web search untuk estimasi kasar: berapa records yang mungkin
  ditemukan di Scopus + WoS + grey lit dengan kombinasi PCC + batasan ini?
  Benchmark ScR: 50-500 records ideal (ScR umumnya lebih luas dari SLR);
  <30 berisiko thin mapping; >1000 pertimbangkan penyempitan Context atau
  temporal.

I - INTERESTING
- Menarik untuk komunitas akademik dan praktisi?
- Audience primer: siapa (peneliti, praktisi, policymaker, educator)?
- Apakah hasil mapping akan menjadi rujukan bagi penelitian selanjutnya?

N - NOVEL (bagian paling kritis — ScR rentan overlap dengan ScR lain)
- Untuk SETIAP entri di prior reviews matrix (L2), tunjukkan eksplisit
  apa selisih RQ saya.
- Gunakan web search untuk cross-check: apakah ada scoping review atau
  evidence gap map publish dalam 6 bulan terakhir yang mungkin belum
  tertangkap di L2?
- Output: tabel "Novelty per Prior Review" dengan kolom:

  | Prior Review | Aspek yang overlap | Aspek yang BARU di ScR saya | Signifikansi novelty |

- CATATAN: untuk ScR, novelty dapat datang dari: (a) Concept baru yang belum
  dipetakan; (b) Context baru (geografis/setting/kultural); (c) update
  temporal dari ScR sebelumnya; (d) inklusi tipe sumber bukti yang lebih
  luas (mis. grey lit lokal).

E - ETHICAL
- Tidak ada masalah etika (hak cipta, plagiarism, representasi kelompok)?
- Apakah ada populasi sensitif (minoritas, anak-anak, kelompok rentan)
  yang perlu perlakuan etis khusus dalam pelaporan?

R - RELEVANT
- Berguna untuk praktik/kebijakan? Lihat justifikasi praktis di L4.
- Apakah sejalan dengan agenda besar (SDGs, Permendikbudristek, prioritas
  sektoral, rencana strategis institusi)?
- Hasil mapping akan membantu siapa membuat keputusan apa?

=== CROSS-CHECK TAMBAHAN (internal coherence) ===

1. Apakah PCC + definisi operasional (L3) BENAR-BENAR cukup untuk menjawab
   primary RQ? Jika RQ menanyakan "how is X defined in Context Y" tapi
   Context di PCC terlalu sempit → inkoherensi, RQ atau PCC harus direvisi.

2. Apakah batasan scope (L4) tidak terlalu sempit hingga membuat RQ tidak
   feasible? Jika estimasi feasibility <30 records, pertimbangkan pelonggaran
   (hapus satu batasan atau perluas temporal).

3. Apakah terminologi kanonikal (L3) benar-benar dipakai konsisten di RQ?
   Jika RQ menyebut istilah alternatif yang ditolak, revisi.

4. Apakah RQ SCR-style (what/how/which), bukan SLR-style (does/is/can)?
   Jika masih SLR-style, revisi.

5. Apakah AT LEAST 1 secondary RQ mencakup identifikasi GAP?
   Gap identification adalah salah satu kekuatan unik ScR — seharusnya
   eksplisit di RQ.

Berikan assessment per kriteria + rekomendasi.
Jika ada item yang FAIL, tunjukkan langkah mana yang harus direvisi
(L1/L2/L3/L4/L5).
```

> **💡 Tips Claude:** Verifikasi novelty via web search + matriks L2 adalah **pagar terakhir** sebelum Anda menginvestasikan waktu berbulan-bulan. Jika Claude menemukan scoping review yang sangat mirip, jangan langsung ganti topik — minta Claude mengidentifikasi aspek mana di matriks L2 yang bisa diperluas sebagai *differentiator* (Context baru, update temporal, grey lit inclusion, gap angle).

**Jika ada yang perlu diperbaiki**, kembali ke langkah terkait untuk revisi sebelum lanjut ke Modul 3. Setelah lolos, ini saat yang tepat untuk **mendaftarkan protokol di OSF** sebelum memulai pencarian (JBI best practice).

---

## **HASIL AKHIR**

### **Final Research Question Package ScR (v1):**
```
=== SCOPING REVIEW QUESTION PACKAGE ===

RESEARCH AREA: [bidang penelitian]
SELECTED TOPIC: [topik yang dipilih]
REVIEW TYPE: Scoping Review (JBI Manual Ch.11 + PRISMA-ScR)

--- 1. GAP CHARACTERIZATION ---
(→ feed ke Modul 9 Introduction: problem statement + justifikasi ScR)
Gap type: [A / B / C / D]
Gap description: [deskripsi singkat]
Justifikasi pilih ScR (bukan SLR): [merujuk Munn et al. 2018 purpose]
Evidence: [sumber verifikasi dari web search]

--- 2. PRIOR REVIEWS MATRIX ---
(→ feed ke Modul 9 Introduction: subseksi "Review of Prior Reviews")
[Tabel matriks lengkap]
Novelty synthesis: [1 paragraf 150-200 kata]

--- 3. PCC + OPERATIONAL DEFINITIONS ---
(→ feed ke Modul 5 inclusion criteria)
P (Population): [population atau "N/A — conceptual scoping"]
   WHAT COUNTS: [...]
   WHAT DOESN'T: [...]
   EDGE CASES: [...]
C (Concept): [...] (dengan definisi operasional lengkap)
C (Context): [...] (dengan definisi operasional lengkap)

--- 4. CANONICAL TERMINOLOGY ---
(→ dipakai konsisten di seluruh modul)
Istilah kanonikal: "[term]"
Definisi baku: [1 kalimat]
Alternatif yang ditolak: [list alternatif + alasan]

--- 5. SCOPE JUSTIFICATION ---
(→ feed ke Modul 9 Introduction: justifikasi batasan)
Batasan 1: [nama]
  - Teoretis: [...]
  - Metodologis: [...]
  - Praktis: [...]
  [ITERATIVE: ya/tidak]
Batasan 2: [...]
[dst]

--- 6. RESEARCH QUESTIONS (SCR STYLE) ---
(→ feed ke Modul 9 objectives; Modul 8 struktur hasil charting/mapping)
PRIMARY RQ: [question — "what/how/which" style]
  Traceability: gap [...], selisih prior [...], answerable via PCC [...]
SECONDARY RQ 1: [...] (dengan traceability)
SECONDARY RQ 2: [...] (dengan traceability)
SECONDARY RQ 3: [...] (dengan traceability)
[At least 1 RQ mencakup gap identification]

--- 7. FINER + NOVELTY CHECK ---
(→ dokumentasi metodologis)
F: ✓ Passed — [estimasi feasibility: ~N records di Scopus + grey lit]
I: ✓ Passed — [audience teridentifikasi]
N: ✓ Passed — [tabel Novelty per Prior Review]
E: ✓ Passed
R: ✓ Passed — [relevansi praktis terdokumentasi]
Internal coherence: ✓ RQ ↔ PCC ↔ Scope konsisten, ScR-style confirmed

--- 8. PROTOCOL REGISTRATION (REKOMENDASI JBI) ---
(→ wajib sebelum Modul 3)
Target platform: OSF (Open Science Framework) / Figshare
Target tanggal registrasi: [sebelum mulai pencarian]
Isi protokol: PCC, inclusion/exclusion criteria, search strategy draft,
  charting form draft, timeline, tim reviewer

NEXT STEP: Develop search strategy untuk Scopus + grey literature (Modul 3)
```

---
