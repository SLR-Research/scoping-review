# Modul 3: Strategi Pencarian Scoping Review dengan GenAI

---

## **LANGKAH 1: DATABASE SELECTION + JUSTIFICATION**

> **🎯 Tujuan:** Tentukan database peer-reviewed dan — **jika relevan dan feasible** — sumber grey literature, dengan justifikasi eksplisit. JBI Manual Ch.11 merekomendasikan grey lit untuk ScR tapi tidak mewajibkan; keputusan tipe sumber harus dijustifikasi secara eksplisit baik inklusif maupun restriktif.

### **Prompt untuk Claude:**
```
Berdasarkan output Modul 2:

Topik penelitian: [dari Modul 2 L1]
PCC + istilah kanonikal: [ringkasan dari Modul 2 L3]
Batasan geografis: [dari Modul 2 L4]
Batasan bahasa: [dari Modul 2 L4]
Tipe sumber bukti (L4): [peer-reviewed + grey lit / hanya peer-reviewed]

Saya melakukan SCOPING REVIEW (JBI + PRISMA-ScR). Grey literature perlu
dipertimbangkan jika relevan dengan topik (opsional, bukan wajib) — berbeda
dari SLR yang umumnya peer-reviewed only.

Gunakan web search untuk menganalisis lanskap sumber yang relevan:

1. CEK COVERAGE BIDANG SAYA:
   - Apakah Scopus + WoS mencakup mayoritas jurnal inti di bidang ini?
   - Apakah ada literatur penting (regional, non-English, grey lit) yang
     TIDAK ter-index tetapi relevan untuk memetakan Concept saya?
   - Apakah bidang saya kaya di laporan kebijakan/lembaga (WHO, Bank Dunia,
     UNESCO, Bappenas, Kemendikbud, dsb)?
   - Apakah ada disertasi/tesis yang memetakan Concept ini dengan baik?

2. BANGUN MATRIKS SUMBER (dual-layer: peer-reviewed + grey lit):

=== LAYER 1: DATABASE PEER-REVIEWED ===
| Database | Coverage strength | Limitation | Fit dengan PCC saya |
|----------|-------------------|------------|----------------------|
| Scopus | Global peer-reviewed, citation-rich | Bias Anglo-Saxon, minim regional | [penilaian] |
| Web of Science | Similar Scopus, strong sciences | Lebih selektif | [penilaian] |
| PubMed/MEDLINE | Biomedical komprehensif | Terbatas biomedical | [penilaian] |
| ERIC | Education literature | Terbatas pendidikan | [penilaian] |
| IEEE Xplore | Engineering/CS | Terbatas domain | [penilaian] |
| Garuda (Indonesia) | Jurnal SINTA, publikasi nasional | Terbatas Indonesia | [penilaian] |
| DOAJ | Open access global | Hanya OA | [penilaian] |

=== LAYER 2: SUMBER GREY LITERATURE (OPSIONAL, JIKA RELEVAN) ===
| Sumber | Tipe bukti | Cara pencarian | Fit dengan PCC saya |
|--------|-----------|-----------------|----------------------|
| Google Scholar | Mixed (peer + grey) | Query + filter 200 hits pertama | [penilaian] |
| ProQuest Dissertations | Tesis/disertasi | Query database | [penilaian] |
| OpenGrey / GreyNet | Grey lit Eropa | Query katalog | [penilaian] |
| OSF / arXiv / SSRN | Preprint | Query platform | [penilaian] |
| WHO / World Bank / UNESCO | Laporan lembaga internasional | Website search | [penilaian] |
| Bappenas / Kemendikbud / BPS | Laporan kebijakan nasional | Website search | [penilaian] |
| Website organisasi terkait | Working paper, policy brief | Targeted browsing | [penilaian] |
| Google (hand-search) | Web umum | Query + screening 50-100 hits | [penilaian] |

3. DECISION RULES (ScR-specific, bukan SLR):
   - MINIMUM 2 database peer-reviewed (mis. Scopus + WoS) untuk coverage
     inti. Grey lit opsional — tambahkan jika salah satu kondisi berikut
     terpenuhi:
   - Jika Concept terkait kebijakan/praktik → pertimbangkan situs lembaga
     (WHO, Bappenas, UNESCO, dll)
   - Jika Concept Anda konseptual/teoretis dan banyak tesis relevan → pertimbangkan
     ProQuest Dissertations
   - Jika Context = Indonesia dan publikasi lokal penting → pertimbangkan Garuda
     + Google Scholar berbahasa Indonesia
   - Jika topik sangat baru (<3 tahun) dan preprint signifikan → pertimbangkan
     arXiv, OSF, SSRN
   - Jika grey lit TIDAK dibutuhkan atau tidak feasible → boleh peer-reviewed
     saja, justifikasikan keputusan tsb di Methods

4. TULIS JUSTIFIKASI FINAL (150-250 kata, siap dipindah ke Methods):

   Template A (jika TERMASUK grey lit):
   "We searched [database peer-reviewed list] for peer-reviewed literature
   because [alasan coverage]. Consistent with JBI scoping review guidelines
   (Peters et al., 2020), we also searched the following sources of grey
   literature: [list + method]. Grey literature was included to [alasan —
   relevansi kebijakan, publikasi lokal, emerging topic]. We acknowledge
   [limitation], mitigated by [strategi]. All searches were conducted on
   [YYYY-MM-DD]."

   Template B (jika HANYA peer-reviewed):
   "We searched [database peer-reviewed list] for peer-reviewed literature
   because [alasan coverage]. Grey literature was not formally searched
   because [alasan — topik dominan peer-reviewed, feasibility, scope fokus].
   We acknowledge this may [potential limitation] and addressed this by
   [mitigasi — misal, hand-searching reference lists of key reviews,
   snowballing]. All searches were conducted on [YYYY-MM-DD]."

Output harus READY untuk dipindah ke Methods section (Modul 9).
```

> **💡 Tips Claude:** Grey literature bukan wajib tetapi dapat memperkaya ScR ketika topik kaya di laporan lembaga/kebijakan, emerging (banyak preprint), atau Context lokal (publikasi berbahasa Indonesia). Jika Anda memilih tidak menyertakannya, justifikasikan eksplisit di Methods — ini juga pilihan yang defensible asal beralasan. Yang tidak dapat diterima reviewer adalah **tidak ada justifikasi** terhadap keputusan tipe sumber.

**Dokumentasikan** pilihan database + (opsional) sumber grey lit + justifikasi sebelum lanjut. Akan dirujuk di Methods dan protokol OSF.

---

## **LANGKAH 2: KEMBANGKAN KEYWORDS DARI PCC + TERMINOLOGI KANONIKAL**

### **Prompt untuk Claude:**
```
Berdasarkan PCC + operational definitions dari Modul 2 L3:

P (Population) — jika applicable:
   Canonical term: [istilah kanonikal dari Modul 2 L3, atau "N/A — conceptual"]
   WHAT COUNTS: [kriteria dari Modul 2 L3]
   WHAT DOESN'T COUNT: [kriteria dari Modul 2 L3]
   Alternatif yang DITOLAK (Modul 2 L3): [list]

C (Concept):
   Canonical term: [dari Modul 2 L3]
   WHAT COUNTS: [...]
   WHAT DOESN'T COUNT: [...]
   Alternatif yang DITOLAK: [list]

C (Context):
   Canonical term/definisi: [dari Modul 2 L3]
   WHAT COUNTS: [...]
   WHAT DOESN'T COUNT: [...]

Sumber terpilih (L1): [peer-reviewed DBs + grey lit sources]

Bantu saya develop keywords untuk setiap komponen PCC dengan PRINSIP BERIKUT:

PRINSIP KUNCI UNTUK SCR:
- ScR cenderung LEBIH RECALL-ORIENTED daripada SLR (tujuan memetakan luas,
  bukan menyaring ketat). Sinonim boleh lebih luas TAPI tetap lolos
  operational definition "what counts".
- Istilah kanonikal WAJIB ada di daftar utama.
- AVOID list tetap penting — untuk mencegah menangkap "what doesn't count"
  (mis. AI klasik saat yang ingin dipetakan adalah generative AI).
- Untuk grey lit + publikasi lokal, pertimbangkan SINONIM BAHASA LOKAL
  (Bahasa Indonesia jika Context = Indonesia).

=== P - POPULATION KEYWORDS ===
(Jika Population = N/A — conceptual, tulis "N/A" dan lewati)
- Canonical term: [sesuai Modul 2 L3]
- Main synonyms (lolos "what counts" test): [3-5 terms]
- Alternative terms: [2-4 terms]
- Bahasa lokal (jika relevan): [terms dalam Bahasa Indonesia]
- AVOID list: [istilah yang akan menangkap "what doesn't count"]

=== C - CONCEPT KEYWORDS (INTI SCR) ===
- Main terms: [3-5]
- Synonyms: [3-5]
- Alternative terms (termasuk istilah emerging): [2-4]
- Bahasa lokal (jika relevan): [terms dalam Bahasa Indonesia]
- AVOID list: [istilah yang menangkap konsep beda, mis. AI klasik non-generatif]
- Catatan: Concept adalah KOMPONEN TERPENTING untuk ScR — investasi lebih
  banyak sinonim di sini.

=== C - CONTEXT KEYWORDS ===
- Geographic terms: [negara/region + variasi — mis. "Indonesia" OR "Indonesian"
  OR "South East Asia*"]
- Setting terms: [mis. "higher education" OR "universit*" OR "undergraduate*"]
- Temporal qualifiers (jika tidak di-handle lewat filter tahun): [...]
- AVOID list: [mis. jika Context = higher education, avoid "secondary school"
  "high school" "K-12"]

Verifikasi terminologi via web search untuk kasus yang Anda tidak yakin —
mis. jika istilah lokal kurang umum di literatur internasional, identifikasi
terminologi internasional yang SETARA untuk dimasukkan sebagai alternative
term. Untuk Context Indonesia, cek terminologi resmi (mis. "higher education"
vs "tertiary education" — keduanya dipakai Kemendikbud/UNESCO).
```

**Review keywords** dan pastikan AVOID list benar-benar lengkap untuk ketiga komponen PCC. Untuk ScR, Concept memerlukan kedalaman sinonim terbanyak — itu jantung mapping Anda.

---

## **LANGKAH 3: KONSTRUKSI SEARCH STRING + JUSTIFIKASI FILTER**

### **Prompt untuk Claude:**
```
Berdasarkan keywords yang sudah di-filter (Langkah 2):

P keywords: [list, atau N/A]
C (Concept) keywords: [list]
C (Context) keywords: [list]

Sumber terpilih (L1): [peer-reviewed DBs + grey lit]

Scope justifications dari Modul 2 L4:
- Rentang tahun: [periode] — justifikasi (ringkasan): [...]
- Batasan bahasa: [bahasa] — justifikasi: [...]
- Document type: [tipe — mis. Article + Review + Conference Paper] — justifikasi: [...]
- Tipe sumber bukti: [peer + grey] — justifikasi: [...]

Tolong buat empat output:

=== OUTPUT 1: SEARCH STRING UTAMA (SCOPUS) ===

Format PCC untuk Scopus:
TITLE-ABS-KEY((P1 OR P2 OR P3)
           AND (C_concept1 OR C_concept2 OR C_concept3)
           AND (C_context1 OR C_context2 OR C_context3))

(Jika P = N/A conceptual, gunakan hanya Concept AND Context.)

Aturan:
- OR untuk synonyms dalam komponen PCC yang sama
- AND untuk menghubungkan antar komponen PCC
- Wildcard (*) untuk variations (mis. educat* → education, educational, educating)
- Quotation marks untuk phrase searching ("generative artificial intelligence")
- Hindari sinonim dari AVOID list (Langkah 2)
- Untuk ScR: miringkan ke RECALL — lebih baik hasil lebih banyak lalu difilter
  di screening, daripada missed coverage.

=== OUTPUT 2: ADAPTASI UNTUK DATABASE LAIN ===

Untuk setiap database sekunder (WoS, Garuda, PubMed, ERIC, dll), adaptasi syntax:
- WoS: TS=(... AND ... AND ...)
- Garuda: query Bahasa Indonesia + English
- PubMed: MeSH terms + free-text
- ERIC: Thesaurus terms + free-text
- Google Scholar: simplifikasi (quote + OR + intitle jika perlu)

Sajikan untuk setiap database tersebut dalam format siap-jalankan.

=== OUTPUT 3: STRATEGI GREY LITERATURE ===

Untuk setiap sumber grey lit dari L1:
- Search terms yang disederhanakan (grey lit sering tidak mendukung Boolean kompleks)
- Prosedur pencarian (website query, catalog search, top-N hits)
- Cut-off untuk screening (mis. "top-200 hits di Google Scholar yang relevan
  by title")
- Target jumlah records

=== OUTPUT 4: TABEL FILTER DENGAN JUSTIFIKASI ===

| Filter | Nilai | Diterapkan di | Justifikasi (1-2 kalimat dari Modul 2 L4) |
|--------|-------|---------------|-------------------------------------------|
| Publication year | [periode] | Semua DB | [justifikasi singkat] |
| Language | [bahasa] | Semua DB | [justifikasi singkat] |
| Document type | [Article/Review/Conference] | Peer-reviewed DB | [justifikasi singkat] |
| Subject area (jika dibatasi) | [area] | Scopus/WoS | [justifikasi singkat] |
| Open access only | [yes/no] | Semua DB | [justifikasi singkat] |

ATURAN PENTING: Filter TANPA justifikasi → HAPUS dari daftar.
Reviewer PRISMA-ScR akan menanyakan "mengapa filter ini ada" — jika Anda tidak
punya jawaban berbasis Scope Justification (L4 Modul 2), filter tsb arbitrer
dan akan jadi kerentanan.

CATATAN SCR: Batasan document type biasanya LEBIH LUAS untuk ScR — termasuk
book chapters, conference papers, dan grey lit. Jangan memaksa hanya Article
kecuali ada justifikasi kuat.

Output akhir READY untuk dijalankan + disalin ke Methods section.
```

**Copy search string + tabel filter** ke dokumentasi. Siap untuk testing di setiap database.

---

## **LANGKAH 4: PRE-VALIDASI, TEST, FINALISASI + DATE STAMP & UPDATE POLICY**

### **Pre-Validasi Search String dengan Claude (Sebelum ke Database):**
```
Sebelum saya menjalankan search string ini di database, tolong bantu validasi:

Search string utama (Scopus):
[search string dari Langkah 3]

Adaptasi untuk DB lain:
[WoS, Garuda, PubMed, dsb dari Langkah 3]

Strategi grey lit:
[ringkasan dari Langkah 3]

Filter settings:
[tabel filter dari Langkah 3]

1. VERIFIKASI SYNTAX:
   - Apakah format TITLE-ABS-KEY (atau equivalen) sudah benar di tiap DB?
   - Apakah penggunaan Boolean operators (AND, OR) sudah tepat?
   - Apakah wildcard (*) dan quotation marks sudah pada posisi yang benar?
   - Untuk Garuda/DB lokal: apakah sinonim Bahasa Indonesia sudah included?
   - Identifikasi potensi error yang bisa menyebabkan zero results

2. VERIFIKASI RELEVANSI KEYWORDS VIA WEB:
   - Gunakan web search untuk cek apakah keywords benar-benar digunakan
     dalam literatur bidang saya
   - Apakah ada terminologi lebih umum yang saya lewatkan (tapi harus tetap
     lolos operational definition dari Modul 2 L3)?
   - Apakah ada "trap keyword" — istilah yang mirip tapi akan menangkap
     "WHAT DOESN'T COUNT"?

3. ESTIMASI AWAL:
   - Perkiraan apakah search string akan menghasilkan terlalu banyak,
     terlalu sedikit, atau cukup hasil?
     Benchmark ScR: 50-500 records (setelah dedup) ideal; <30 thin;
     >1000 pertimbangkan penyempitan.
   - Jika terlalu sempit: saran sinonim tambahan yang lolos operational def
   - Jika terlalu luas: saran ketatkan komponen mana

4. SANITY CHECK DENGAN KEY PAPERS:
   Sebelum menjalankan search penuh, saya akan cek 5-10 paper kunci yang
   saya tahu ada di bidang saya. Tolong bantu saya: apakah search string
   HARUSNYA menangkap paper-paper ini? Jika tidak, di mana celahnya?

Berikan revised search string jika ada perbaikan yang diperlukan.
```

> **💡 Tips Claude:** Pre-validasi ini menghemat waktu — Anda tidak perlu bolak-balik ke database berkali-kali. Untuk ScR dengan multi-source, pre-validasi PER SUMBER (peer-reviewed DB + grey lit) penting karena syntax berbeda.

### **Praktik di Database:**

**A. Database Peer-Reviewed (Scopus, WoS, dll.):**
1. **Login** dan masuk ke Advanced Search
2. **Input search string** yang sudah divalidasi Claude
3. **Apply filters** sesuai tabel di Langkah 3
4. **Jalankan search** dan catat:
   - Total hits (sebelum filter)
   - Total setelah filter
   - **Tanggal pencarian dijalankan** (YYYY-MM-DD) — ini WAJIB dicatat

**B. Grey Literature Sources:**
1. **Google Scholar**: input query sederhana, screen top-200 hits by title, catat relevan
2. **ProQuest Dissertations**: query database, apply filter tahun, export metadata
3. **Situs lembaga (WHO, Bappenas, dll.)**: gunakan search box website, catat query + tanggal + top-N hits yang di-screen
4. **OSF/arXiv/SSRN**: query platform, filter tahun
5. **Dokumentasikan setiap sumber** (query yang dipakai, tanggal, jumlah records)

### **Evaluasi dan Finalisasi dengan Claude:**
```
Hasil search (semua sumber):

=== PEER-REVIEWED DATABASES ===
- Scopus: search string [...], total [N], filter [N], tanggal [YYYY-MM-DD]
- WoS: search string [...], total [N], filter [N], tanggal [YYYY-MM-DD]
- [DB lain]: [...]

=== GREY LITERATURE ===
- Google Scholar: query [...], top-200 screened, relevan [N], tanggal [...]
- ProQuest Dissertations: [...]
- WHO/Bappenas/lembaga: [...]
- OSF/arXiv: [...]

Sample judul 5-10 pertama per sumber: [paste judul]

Tolong bantu:
1. EVALUASI HASIL:
   - Apakah TOTAL results (gabungan semua sumber) reasonable untuk ScR?
     Benchmark: 50-500 post-dedup ideal; adjust jika di luar range.
   - Cek apakah sample judul relevan dengan PCC
   - Cek apakah ada judul yang masuk karena "trap keyword"
   - Apakah distribusi sumber sehat (tidak didominasi 1 DB)?

2. JIKA PERLU ADJUSTMENT:
   - Berikan revised search string dengan penjelasan perubahan spesifik
   - Jelaskan trade-off (precision vs recall) — untuk ScR, prefer recall
   - Jika grey lit terlalu sedikit, sarankan sumber tambahan

3. FINALISASI:
   - Konfirmasi complete search strategy untuk protokol OSF
   - Format ready untuk tahap data mining/export (Modul 4)
```

### **TAMBAHAN WAJIB — Date Stamp & Update Policy:**

```
Setelah search final di-run (semua sumber), tetapkan dan dokumentasikan:

=== DATE STAMP ===
- Tanggal pencarian final: [YYYY-MM-DD] per sumber
- Signifikansi: tanggal ini jadi titik cut-off temporal. Semua referensi
  yang dipublikasi SETELAH tanggal ini dan di-include sebagai studi primer =
  inkonsistensi temporal (lihat Modul 9 audit).
- Referensi yang publish setelah tanggal ini boleh muncul HANYA sebagai:
  · Sitasi konteks di Introduction/Discussion (bukan dalam mapping)
  · Prior review yang diacu di L2 Modul 2 (sebagai titik banding)

=== UPDATE SEARCH POLICY (ScR-specific) ===
Tetapkan kebijakan eksplisit kapan harus re-run search:

TRIGGER WAJIB RE-RUN:
- Manuscript belum di-submit dalam [default: 6 bulan] sejak search date
- Reviewer meminta update search di revision round
- Mayor breakthrough publication di topik inti (antara search date dan
  submission), terutama yang berpotensi mengubah peta Concept
- Untuk topik yang sangat dinamis (mis. generative AI), bisa dipertimbangkan
  update setiap 3 bulan

PROSEDUR RE-RUN:
1. Run ulang search string yang sama, per sumber, dengan tanggal cut-off baru
2. Catat records baru yang muncul (publish setelah previous cut-off)
3. Screening records baru dengan inclusion/exclusion criteria yang sama
4. Charting records baru yang lolos, integrasikan ke peta existing
5. Dokumentasi di Methods: "Search was updated on [date] to include
   publications through [new cut-off]. An additional [N] records were
   identified and [X] were included in the charting."

Dokumentasikan kebijakan ini di protokol OSF Anda (plus di Methods manuscript).
```

---

## **HASIL AKHIR**

### **Complete Search Strategy Package (ScR v1):**
```
=== COMPLETE SEARCH STRATEGY (ScR) ===

RESEARCH QUESTION: [dari Modul 2]
REVIEW TYPE: Scoping Review (JBI + PRISMA-ScR)

--- 1. SOURCE SELECTION (→ Methods Modul 9) ---

Layer 1 — Peer-Reviewed Databases:
- Primary: [mis. Scopus, WoS]
- Supplementary: [mis. ERIC, Garuda]
- Justification: [150-200 words]

Layer 2 — Grey Literature Sources (OPSIONAL — isi jika digunakan):
- Sources used: [Google Scholar, ProQuest, WHO, Bappenas, OSF, dll.]
- Search method per source: [brief description]
- Justification inklusi: [50-100 words mengapa sumber ini dipilih]
- (Jika tidak digunakan) Justifikasi eksklusi grey lit: [alasan + mitigasi]

Known coverage limitations: [apa yang tidak ter-cover + mitigasi]

--- 2. KEYWORDS (→ dokumentasi metodologis) ---
Canonical terminology: [dari Modul 2 L3]
P keywords (jika applicable): [main + synonyms + alternative + bahasa lokal]
C (Concept) keywords: [main + synonyms + alternative + bahasa lokal]
C (Context) keywords: [geographic + setting + temporal]
AVOID list (trip wire vs "what doesn't count"): [eksplisit per komponen]

--- 3. SEARCH STRINGS (→ appendix manuskrip) ---
Primary (Scopus):
[string lengkap dengan format PCC: P AND Concept AND Context]

Adapted strings:
- WoS: [...]
- ERIC: [...]
- Garuda: [... dengan Bahasa Indonesia]
- PubMed: [... dengan MeSH]
- Google Scholar: [simplified query]

Grey Literature strategies:
- Google Scholar: [query + top-N]
- ProQuest: [query + filter]
- WHO/Bappenas/UNESCO: [website search terms]
- OSF/arXiv: [query]

--- 4. FILTER SPECIFICATIONS (→ Methods) ---
| Filter | Nilai | Diterapkan di | Justifikasi |
[tabel lengkap dari L3]

--- 5. SEARCH EXECUTION RECORD ---
Per sumber:
- Scopus: tanggal [YYYY-MM-DD], pre-filter [N], post-filter [N]
- WoS: [...]
- [Grey lit sources]: tanggal, query, records screened, relevan [N]
Total gabungan (pre-dedup): [N]
Expected post-dedup: [estimasi]
Expected post-screening: [estimasi]

--- 6. UPDATE SEARCH POLICY (→ Methods) ---
Trigger re-run: [daftar trigger eksplisit]
Procedure: [ringkasan prosedur]
Documentation format: [template kalimat untuk Methods]

--- 7. PRISMA-ScR ALIGNMENT CHECK ---
✓ Item 7 (Information Sources) — daftar sumber + justifikasi (grey lit inklusi/eksklusi terjustifikasi): [confirm]
✓ Item 8 (Search) — full search strategy per source documented: [confirm]
✓ Item 9 (Selection of Sources) — eligibility dari PCC: [confirm]

NEXT STEP: Export data + setup screening database (Modul 4)
```

---

## **TROUBLESHOOTING**

**Problem 1: Results terlalu banyak (>1000 post-dedup)**
- Tambahkan specific terms dari operational definition "what counts" di Concept
- Narrow Context (mis. spesifikkan negara atau setting)
- Narrow temporal window (tapi update justifikasi scope di Modul 2 L4)
- Minta Claude analisis sample 20 judul untuk identifikasi noise pattern — apakah dari "trap keyword" yang terlewat di AVOID list?
- CATATAN: untuk ScR tidak selalu perlu mempersempit — 1000+ records masih manageable jika tim besar dan tools screening efisien.

**Problem 2: Results terlalu sedikit (<30 post-dedup)**
- Cek: apakah operational definition "what counts" terlalu ketat? Konsultasi balik ke Modul 2 L3.
- Gunakan broader synonyms di Concept (yang tetap lolos operational def)
- Reduce number of AND operators — atau perluas Context
- Pertimbangkan tambah sumber grey lit (update Langkah 1)
- Extend time period (update justifikasi di Modul 2 L4)
- Periksa: apakah Anda sudah memasukkan Bahasa Indonesia untuk publikasi lokal (jika Context Indonesia)?

**Problem 3: Search string error di database**
- Check bracket placement
- Verify quotation marks
- Ensure proper Boolean operators (AND, OR, bukan &, |)
- Cek wildcard position — Scopus butuh minimum 3 huruf sebelum `*`
- Untuk Garuda: cek apakah query panjang di-support (kadang perlu split)

**Problem 4: Irrelevant results (noise)**
- Identifikasi pattern noise — apakah dari "trap keyword"?
- Update AVOID list di Langkah 2, lalu regenerasi search string
- Add NOT operators untuk exclusion spesifik (hati-hati: NOT juga menggugurkan studi borderline — untuk ScR prefer RECALL, screening di Modul 5-6)
- Refine operational definitions di Modul 2 L3 jika pattern noise menunjukkan kriteria inklusi yang ambigu

**Problem 5: Grey literature susah didokumentasikan**
- Screenshot halaman hasil pencarian sebagai bukti
- Gunakan Zotero/Mendeley untuk simpan record grey lit (dengan metadata lengkap: judul, penulis, tahun, URL, tanggal akses)
- Untuk PRISMA-ScR flow diagram, grey lit counted separately dari peer-reviewed
- Buat log terpisah "Grey Literature Search Log" dengan kolom: Sumber, Query, Tanggal, Total Hits, Screened, Included

**Problem 6: Database coverage meragukan**
- Jalankan "sanity check" — cari 5-10 paper kunci + 2-3 laporan lembaga yang Anda tahu relevan. Apakah muncul di hasil search? Jika tidak, audit mengapa.
- Jika banyak paper/laporan kunci tidak ter-cover → tambah sumber atau longgarkan keywords

**Problem 7: Ragu apakah sumber grey lit cukup**
- Tidak ada angka minimum wajib — sesuaikan dengan relevansi dan feasibility
- Jika menyertakan: pertimbangkan kombinasi (a) repositori tesis, (b) situs lembaga relevan dengan topik, (c) preprint platform jika topik baru, (d) Google Scholar sebagai safety net
- Jika tidak menyertakan: justifikasikan eksplisit di Methods (mis. topik dominan peer-reviewed, feasibility, scope fokus)
- Pertimbangkan konsultasi dengan librarian/information specialist untuk topik spesifik

---
