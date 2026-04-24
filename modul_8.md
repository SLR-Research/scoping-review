# Modul 8: Collating, Summarizing, dan Reporting Results (Scoping Review)

---

## **LANGKAH 1: DESCRIPTIVE NUMERICAL SUMMARY**

> **🎯 Tujuan:** Pahami karakter data secara menyeluruh SEBELUM membangun peta tematik. Untuk ScR, ini **fondasi WAJIB** — descriptive numerical summary adalah komponen inti Results (Arksey & O'Malley step 5; JBI Manual Ch.11 step 7-8). Tidak ada meta-analysis di ScR; sintesis bersifat deskriptif + tematik.

### **Prompt untuk Claude:**
```
[Upload charting_scr_[topik].xlsx dari Modul 7]

Context dari Modul 7:
- Charting framework: [JBI standard / PCC-driven / Thematic / Policy-oriented / Custom]
- Total final INCLUDED sources: [N] (peer: [X], grey: [Y])
- Optional QA performed: [YES / NO]
- Mapping approach verdict (Modul 7 L4): [Descriptive / Thematic / Gap Map / Hybrid]

Pikirkan secara mendalam dan bertahap sebelum memberikan kesimpulan.

=== TUGAS 1: DESCRIPTIVE NUMERICAL SUMMARY ===

1. SOURCE TYPE DISTRIBUTION:
   - Peer-reviewed: [N] ([%])
   - Grey literature: [N] ([%]) — breakdown per sub-type (report, thesis, policy brief, preprint)

2. DOCUMENT TYPE DISTRIBUTION (untuk peer-reviewed):
   - Journal article: [N]
   - Conference paper: [N]
   - Review: [N]
   - Book chapter: [N]

3. TEMPORAL DISTRIBUTION:
   - Tahun publikasi (min, max, median)
   - Time trend: apakah meningkat (growing field), menurun (declining), atau stable?
   - Identifikasi burst period (tahun dengan banyak publikasi)
   - Implikasi: apakah konsep yang dipetakan masih emerging atau mature?

4. GEOGRAPHIC DISTRIBUTION:
   - Negara/region breakdown
   - Identifikasi dominance (jika ada) — mis. 70% dari USA/Europe
   - % dari Global North vs Global South
   - Breakdown Indonesia vs non-Indonesia (jika Context Indonesia)
   - PENTING: ini akan jadi bahan disclosure bias geografis di Discussion

5. STUDY DESIGN / DOCUMENT TYPE DISTRIBUTION:
   - Design breakdown (jika empiris): RCT, cross-sectional, qualitative, mixed, dll.
   - Document type breakdown (jika mixed): empirical, conceptual, policy, review
   - % empirical vs conceptual vs policy

6. SAMPLE SIZE STATISTICS (jika applicable):
   - Range (min, max)
   - Median, mean
   - Total participants across studies

7. PCC COMPONENT DISTRIBUTION:
   - P (Population): breakdown karakteristik
   - C (Concept): breakdown jenis/variasi Concept
   - C (Context): breakdown setting, kultural, temporal

8. QUALITY DISTRIBUTION (jika QA dilakukan, Modul 7 L3):
   - HIGH: [N] ([%])
   - MODERATE: [N] ([%])
   - LOW: [N] ([%])
   - CATATAN: dilaporkan deskriptif, bukan exclusionary

=== TUGAS 2: VISUAL SUMMARY RECOMMENDATIONS ===

Untuk setiap distribusi di atas, rekomendasikan jenis visualisasi yang paling
informatif untuk Results section:

- Temporal trend → line chart atau stacked bar per tahun
- Geographic → world/region map atau bar chart
- Source type × Document type → stacked bar atau grouped bar
- PCC component breakdown → pie chart atau horizontal bar
- Quality distribution (jika ada) → stacked bar

Daftar figur yang akan jadi output di Modul 9:
- Figure 1: PRISMA-ScR flow diagram (dari Modul 4-6)
- Figure 2: Temporal distribution
- Figure 3: Geographic distribution
- Figure 4: [PCC-related mapping]
- [dst — 5-7 figur umumnya ideal untuk ScR]

Output: comprehensive descriptive numerical summary + list rekomendasi figur.
```

> **💡 Tips Claude:** Descriptive numerical summary untuk ScR **lebih penting** daripada untuk SLR. Ini bukan "gambaran tabel" tapi **substansi Results**. Investasi tinggi di sini (jam kerja + iterasi visualisasi) akan terbayar di Modul 9.

---

## **LANGKAH 2: THEMATIC / CATEGORICAL MAPPING**

> **🎯 Tujuan:** Kelompokkan sumber ke dalam kategori/tema yang informatif untuk menjawab RQ. Ini **inti analytical** ScR — bagaimana konsep/fenomena dipetakan dalam lanskap bukti.

### **Prompt untuk Claude:**
```
[Upload charting_scr_[topik].xlsx + descriptive summary dari L1]

Research Questions ScR (dari Modul 2 L5):
- Primary: [question]
- Secondary: [3 RQs]

Framework charting (dari Modul 7): [...]

=== TUGAS 1: CATEGORICAL ANALYSIS PER KOLOM KUNCI ===

Untuk setiap kolom kunci di charting form, lakukan categorical analysis:

Kolom kunci (sesuaikan dengan framework Anda):
- Concept Operationalization
- Context Details (setting, kultural)
- Methodology approach
- Key findings (tematik)
- Gap/future research noted

Untuk tiap kolom:
1. Identifikasi kategori-kategori yang muncul (open coding awal)
2. Hitung frekuensi per kategori
3. Deteksi pola: dominance, clusters, outliers
4. Minta Claude lakukan clustering awal jika kategori banyak (>15)

Contoh output untuk "Concept Operationalization":

| Kategori | Frekuensi | % | Contoh sumber |
|----------|-----------|---|---------------|
| Kategori A | 12 | 27% | SCR003, SCR015, ... |
| Kategori B | 8 | 18% | SCR007, SCR022, ... |
| ... | ... | ... | ... |

=== TUGAS 2: THEMATIC SYNTHESIS (NARRATIVE) ===

Untuk setiap RQ, tulis narrative synthesis berdasarkan categorical analysis:

PRIMARY RQ thematic synthesis:
- Tema 1: [label]
  - Dijumpai di [N] sumber
  - Karakteristik: [...]
  - Variasi yang ditemukan: [...]
- Tema 2: [...]
- ...

SECONDARY RQ thematic synthesis (per RQ):
- [format serupa]

ATURAN BAHASA ScR (WAJIB):
- Gunakan "mapping", "characterization", "describing", "identifying"
- JANGAN pakai "pooled effect", "meta-analysis shows", "significant effect across studies"
- BOLEH: "N studies reported [finding]", "common theme was [...]"
- BOLEH: indicative ranges jika relevan — mis. "sample sizes ranged from 50 to 5000"
- HINDARI causal claims yang tidak didukung single sumber

=== TUGAS 3: CROSS-TABULATION ===

Bangun matriks 2D untuk mencari pola:

Contoh:
- Concept × Context matriks (Concept kategori × Context kategori)
- Cell berisi N sumber yang punya kombinasi tsb
- Identifikasi cell dengan N tinggi (well-mapped area) dan N=0 (gap)

Contoh hasil:
                Context A   Context B   Context C
Concept X       15          3           0
Concept Y       8           12          2
Concept Z       2           5           7

Interpretasi:
- Well-mapped: Concept X dalam Context A (n=15)
- GAP: Concept X dalam Context C (n=0) — opportunity untuk future research
- Emerging: Concept Z dalam Context C (n=7)

Output:
- Categorical analysis per kolom kunci
- Thematic synthesis per RQ
- Cross-tabulation matriks
- Preliminary identification of well-mapped areas + gaps
```

> **💡 Tips Claude:** Thematic mapping seringkali **iteratif**: coba kategorisasi awal → bahas dengan co-author → refine kategori → final. Untuk ScR >50 sumber, pertimbangkan pakai Claude untuk clustering otomatis dulu ("group these 60 operationalizations into 5-7 thematic categories"), lalu human-review hasil clustering.

---

## **LANGKAH 3: EVIDENCE GAP MAP (EGM)**

> **🎯 Tujuan:** Gap identification adalah **kekuatan unik ScR** (Munn et al., 2018). Evidence Gap Map (EGM) adalah visualisasi sistematis area bukti yang kaya vs kosong. Ini sering jadi "hero figure" manuskrip ScR.

### **Prompt untuk Claude:**
```
[Upload cross-tabulation dari L2 + descriptive summary dari L1]

Tipe gap ScR (dari Modul 2 L1): [A/B/C/D]
Primary RQ gap identification component: [...]

=== TUGAS 1: EGM STRUCTURE DECISION ===

Pilih struktur EGM yang paling informatif:

OPSI A — 2D MATRIX / HEATMAP (paling umum)
  Sumbu X: [mis. Concept categories atau Intervention types]
  Sumbu Y: [mis. Context / Population / Outcome types]
  Cell value: jumlah sumber dengan kombinasi tsb
  Color intensity: menunjukkan density bukti
  Contoh EGM yang baik: 3ie Evidence Gap Map, Campbell Collaboration EGM

OPSI B — BUBBLE PLOT
  Serupa matrix tapi dengan bubble size = N sumber
  Warna bubble bisa encode dimensi ketiga (mis. quality level)

OPSI C — INTERACTIVE EGM (online tools)
  3ie EGM tool, Campbell EGM tool — untuk presentasi web
  Cocok jika publikasi punya supplementary online material

OPSI D — TABLE-BASED EGM
  Tabel dengan shading (untuk publikasi print)
  Simpler dan universal

Rekomendasi untuk ScR saya: [pilih + alasan]

=== TUGAS 2: EGM CONSTRUCTION ===

Untuk struktur terpilih, bangun EGM:

1. Tentukan sumbu:
   - Sumbu X: [kategori dari Modul 7 charting]
   - Sumbu Y: [kategori dari Modul 7 charting]

2. Isi cell values:
   - Count sumber per kombinasi
   - Tandai cell dengan N=0 sebagai "GAP CELL"
   - Tandai cell dengan N>median sebagai "DENSE CELL"

3. Optional 3rd dimension (jika QA dilakukan):
   - Color/pattern per quality tier dalam cell

4. Annotation:
   - Tambah row/column totals
   - Tambah legend untuk kategori (deskripsi singkat)

Format output:
- EGM matrix (siap dirender di Excel/R/Python)
- Deskripsi naratif EGM (paragraf siap-Results)

=== TUGAS 3: GAP INVENTORY (DARI EGM) ===

Berdasarkan EGM, buat inventory gap sistematis:

GAP KUANTITATIF (area dengan sedikit/tanpa bukti):
- Gap 1: [kombinasi X×Y, n=0 atau n<3]
  - Mengapa gap ini penting? [alasan]
  - Future research opportunity: [spesifik]
- Gap 2: [...]

GAP KUALITATIF (area dengan bukti, tapi masih belum terkonsep jelas):
- Gap A: Konsep [X] didefinisikan dengan 5 cara berbeda di literatur
  - Perlu klarifikasi konseptual
- Gap B: [...]

GAP METODOLOGIS:
- Gap M1: Tidak ada studi longitudinal untuk Concept X dalam Context Y
  - Opportunity untuk design selanjutnya
- Gap M2: [...]

GAP TEMPORAL (jika trend analysis menunjukkan):
- Gap T1: Dalam 3 tahun terakhir, publikasi tentang [X] sparse
  - Mungkin emerging atau declining area

Output:
- EGM visualization spec (siap-render)
- EGM narrative description
- Gap inventory kategorisasi (kuantitatif / kualitatif / metodologis / temporal)
- Future research agenda preview
```

> **💡 Tips Claude:** EGM adalah **value-add utama** ScR — reviewer dan pembaca akan sangat menghargai. Investasi tinggi di kualitas EGM (clarity, kategori yang meaningful, visual yang readable). Konsultasi dengan supervisor untuk validasi kategorisasi sebelum final. Untuk EGM yang publish di jurnal top, pertimbangkan tool profesional seperti **3ie EGM builder** atau **Campbell Collaboration EGM platform**.

---

## **LANGKAH 4: INTERPRETATION PREPARATION (BRIDGE KE MODUL 9)**

> **🎯 Tujuan:** Siapkan "mapping-to-manuscript bridge" — output L4 akan langsung masuk ke Modul 9 Results & Discussion.

### **Prompt untuk Claude:**
```
[Upload semua output L1-L3: descriptive summary, thematic mapping, EGM]

Research Questions (dari Modul 2 L5):
- Primary: [...]
- Secondary: [3 RQs]

Gunakan penalaran mendalam. Sebelum menjawab, pertimbangkan:
- Apa yang DIDUKUNG mapping jelas (density tinggi di EGM)?
- Apa yang MUNCUL sebagai pola thematic kuat?
- Apa GAP yang paling signifikan untuk implikasi riset/praktik?
- Apa yang TIDAK BISA diklaim (ingat: ScR memetakan, bukan mensintesis effect)?

=== TUGAS 1: ANSWERS TO RESEARCH QUESTIONS (ScR Style) ===

Untuk setiap RQ, formulasi jawaban gaya ScR ("what is known", "how is X defined",
"which methods are used"):

PRIMARY RQ: [question]
Answer (50-100 kata):
- Direct answer grounded di mapping
- Kuantifikasi (N sumber, breakdown utama)
- Kualifikasi (konteks, heterogenitas)
- BUKAN claim kausal atau effect size

SECONDARY RQ 1-3: (format serupa)

=== TUGAS 2: KEY FINDINGS (3-5 POIN) ===

Identifikasi 3-5 key findings ScR yang akan jadi "headline messages":
- Finding 1: [statement deskriptif/mapping grounded]
- Finding 2: [...]
- ...

Setiap finding:
- Apa yang dipetakan (descriptive claim)?
- Apa implikasi bagi pemahaman lanskap bukti?
- Apa kontribusi untuk riset/praktik/kebijakan?

CONTOH ScR findings yang TEPAT:
- "Literatur didominasi oleh studi berbasis Negara Barat (78%), dengan hanya
  6% studi dari Asia Tenggara."
- "Concept [X] dioperasionalisasikan dengan 5 cara berbeda di literatur,
  dengan definisi [A] paling dominan (n=23)."
- "Tidak ada studi longitudinal yang mengeksplorasi [Concept] dalam [Context]."

CONTOH ScR findings yang SALAH (SLR-style):
- "Evidence menunjukkan bahwa [X] meningkatkan [Y]" (causal claim)
- "Pooled effect size menunjukkan..." (meta-analysis claim)
- "Mayoritas studi membuktikan [X]" (inferential claim)

=== TUGAS 3: SURPRISING/UNEXPECTED MAPPING PATTERNS ===

Pattern yang tidak sesuai ekspektasi awal atau prior reviews:
- Pattern surprising: [statement]
- Kemungkinan penjelasan: [...]
- Implikasi untuk pemahaman bidang: [...]

=== TUGAS 4: CONCEPTUAL CLARIFICATIONS ===

Jika RQ mencakup klarifikasi konsep (Tipe Gap B):
- Konsep [X] didefinisikan dalam [N] cara:
  · Definisi A (n=X studies): [deskripsi]
  · Definisi B (n=Y studies): [deskripsi]
  · ...
- Tension antar definisi: [...]
- Rekomendasi terminologi: [proposal untuk unifikasi atau mengakui plurality]

=== TUGAS 5: GAP-DRIVEN FUTURE RESEARCH AGENDA ===

Dari Gap Inventory (L3), formulasikan future research agenda spesifik
(bukan "more research needed"):

GAP 1: [dari inventory]
  Future research question: [spesifik, PCC-aligned]
  Suggested methodology: [...]
  Priority: [HIGH/MEDIUM/LOW]

GAP 2: [...]
...

ScR value: dari N gap yang teridentifikasi, rekomendasikan [3-5] priority
areas berdasarkan kombinasi (a) signifikansi teoritis, (b) kebutuhan praktik,
(c) feasibility penelitian.

=== TUGAS 6: IMPLICATIONS FOR RESEARCH/PRACTICE/POLICY ===

Untuk ScR, Discussion sering terorganisir per stakeholder:

FOR RESEARCH:
- Dialog dengan teori existing: [konfirmasi / ekspansi / tantangan]
- Konsep yang butuh unifikasi atau ketajaman
- Metodologi yang perlu dikembangkan

FOR PRACTICE:
- Panduan aplikatif berdasarkan mapping
- Area dengan bukti kuat → rekomendasi praktik
- Area dengan bukti lemah → caveat untuk praktisi

FOR POLICY:
- Insight kebijakan dari peta bukti
- Gap yang relevan dengan agenda kebijakan
- Stakeholder yang perlu dilibatkan

=== TUGAS 7: LIMITATIONS SELF-AUDIT ===

Kategorisasi limitations ScR (untuk Modul 9 Discussion):

REVIEW-LEVEL LIMITATIONS:
- Database coverage (peer-reviewed breadth, grey lit breadth)
- Geographic/language bias (dari L1 descriptive)
- Timeframe (dari Modul 2 L4)
- Grey lit inaccessibility (Modul 6 L3)

SOURCE-LEVEL LIMITATIONS:
- Reporting quality (NR fields prevalence)
- Heterogeneity in operationalization (membuat kategorisasi challenging)
- Potential publication bias (untuk peer-reviewed portion)

MAPPING-LEVEL LIMITATIONS:
- Subjectivity in thematic categorization
- Iterative charting means kategori awal mungkin berbeda dari final
- ScR tidak dapat menarik kesimpulan kausal atau effect

ScR-SPECIFIC DISCLAIMERS:
- "This scoping review maps the evidence but does not assess effectiveness"
- "Quality of included sources varied and was reported descriptively, not used
  for exclusion (per JBI guidelines)"
- "No meta-analysis was conducted as ScR methodology focuses on mapping, not
  pooling"

Setiap limitation + mitigation / implikasi untuk generalisasi mapping.

Output: package lengkap siap feed ke Modul 9 Results + Discussion + Future Research.
```

---

## **HASIL AKHIR**

### **Collating + Summarizing + Reporting Package ScR (v1):**
```
=== ANALYSIS + MAPPING RESULTS (ScR) ===

DESCRIPTIVE NUMERICAL SUMMARY (→ Modul 9 Results):
- Sources analyzed: [N] (peer: [X], grey: [Y])
- Document type breakdown: [...]
- Temporal distribution: [...] (trend: growing/declining/stable)
- Geographic distribution: [...] (includes potential bias disclosure)
- Study design / Document type breakdown: [...]
- Sample size statistics (jika applicable): [...]
- PCC component distribution:
  · P: [breakdown]
  · C (Concept): [breakdown]
  · C (Context): [breakdown]
- Quality distribution (jika QA dilakukan): [HIGH/MODERATE/LOW, descriptive only]

VISUAL SUMMARY:
- Figures planned: [list 5-7 figur]
  · Figure 1: PRISMA-ScR flow diagram
  · Figure 2: Temporal trend
  · Figure 3: Geographic distribution
  · Figure 4: PCC component mapping
  · Figure 5: EGM (evidence gap map) — hero figure
  · [dst]

THEMATIC / CATEGORICAL MAPPING (→ Modul 9 Results):
- Categorical analysis per key column:
  · Concept Operationalization: [kategori + frekuensi]
  · Context Details: [kategori + frekuensi]
  · Methodology: [kategori + frekuensi]
  · Key findings (tematik): [kategori + frekuensi]
- Thematic synthesis per RQ (narrative ready-Results)
- Cross-tabulation matrix: [Concept × Context, dll.]

EVIDENCE GAP MAP (→ Modul 9 Results hero figure):
- EGM structure: [2D matrix / bubble / table-based]
- EGM axes: [X axis + Y axis]
- Dense cells (well-mapped): [list]
- Gap cells (n=0 atau sparse): [list]
- Optional 3rd dim (quality): [encoding]
- EGM narrative description (ready-Results)

GAP INVENTORY:
- Kuantitatif: [list gap with priority]
- Kualitatif/konseptual: [list]
- Metodologis: [list]
- Temporal: [list]

INTERPRETATION PACKAGE (→ Modul 9):
- Answers to RQs (ScR style, descriptive/mapping)
- Key findings (3-5 headline messages, ScR-appropriate)
- Surprising mapping patterns
- Conceptual clarifications (jika Tipe Gap B)
- Gap-driven future research agenda (priority areas)
- Implications for research/practice/policy (triple-track)
- Limitations self-audit (3-tier: review/source/mapping + ScR-specific disclaimers)

FORWARD ARTIFACTS (→ Modul 9):
- Framework charting (akan jadi struktur Results)
- Mapping approach (descriptive/thematic/EGM/hybrid)
- Geographic bias disclosure (akan jadi Discussion paragraph)
- Gap inventory (akan jadi Future Research agenda + Discussion)
- PRISMA-ScR compliance checklist items ready
```

---

## **TROUBLESHOOTING**

**Problem 1: Categorical analysis menghasilkan terlalu banyak kategori (>20)**
- Lakukan second-level clustering: group kategori serupa
- Contoh: 20 operationalizations → 5 meta-categories
- Gunakan Claude untuk suggest clustering, lalu human-review
- Laporkan both levels (detail + meta) di Results

**Problem 2: Kategori yang muncul terlalu sedikit (mayoritas n<3)**
- Sinyal bahwa literatur sangat fragmented (justru temuan penting)
- Laporkan heterogeneity in operationalization sebagai finding
- Gabungkan micro-kategori ke meta-category untuk visualisasi
- Diskusikan fragmentasi di Discussion sebagai gap konseptual

**Problem 3: EGM terlihat "kosong" (banyak cell n=0)**
- Ini NORMAL untuk ScR — gap visualization adalah tujuan
- Jangan paksa isi cell dengan sumber yang marjinal
- Laporkan sparse cells sebagai gap explicit dalam narrative
- Beberapa gap = opportunity, terlalu banyak gap = mungkin need to broaden Concept/Context

**Problem 4: Godaan menarik kesimpulan kausal / effect size — JANGAN**
- ScR TIDAK menarik kesimpulan kausal, effect size, atau inferential
- Self-audit dengan Claude: "periksa apakah ada claim effect/kausal di draft ini"
- Trigger words yang HARUS diganti: "pooled", "significant effect", "causes", "leads to"
- Alternatif: "described", "reported", "characterized", "mapped"

**Problem 5: Grey lit heterogeneity sangat tinggi — sulit dikategorisasikan**
- Terima heterogeneity sebagai karakteristik ScR multi-source
- Buat kategori terpisah untuk grey lit jika struktur sangat berbeda
- Alternatif: sub-analysis terpisah untuk peer-only vs mixed
- Laporkan transparan di Results

**Problem 6: Gap yang teridentifikasi terlalu banyak — prioritisasi?**
- Kriteria prioritisasi: (a) signifikansi teoritis, (b) kebutuhan praktik, (c) feasibility
- Pilih 3-5 priority gap untuk ditonjolkan; sisanya tetap dilaporkan di Appendix
- Konsultasi supervisor untuk validasi prioritisasi

**Problem 7: Reviewer/supervisor minta meta-analysis atau pooled estimate**
- Tegaskan: ini ScR, bukan SLR — meta-analysis bukan bagian dari methodology
- Rujuk JBI Manual Ch.11 + Munn et al. (2018) tentang perbedaan ScR vs SLR
- Jika subset homogen ada: pertimbangkan follow-up mini-SLR sebagai output terpisah

**Problem 8: Ragu apakah EGM atau thematic mapping yang lebih informatif**
- Hybrid approach (keduanya) adalah rekomendasi default untuk ScR berkualitas
- EGM untuk visualisasi gap/density
- Thematic mapping untuk kedalaman narrative
- Keduanya saling melengkapi — EGM memberikan overview, thematic memberikan depth

---
