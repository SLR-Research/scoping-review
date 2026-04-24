# Modul 9: Manuscript Writing Scoping Review dengan GenAI (PRISMA-ScR Compliant)

> **📌 Urutan penulisan (reverse-writing):** Methods → Results → Discussion → Future Research → Introduction → Conclusions → References → Abstract → Title → Coherence Audit. Bagian evidence-based ditulis duluan, bagian naratif (Intro, Abstract, Title) ditulis setelah semua temuan jelas.

> **📋 Standar pelaporan:** Manuskrip ini mengikuti **PRISMA-ScR checklist 22-item** (Tricco et al., 2018) dan **JBI Manual Chapter 11** (Peters et al., 2020). BUKAN PRISMA 2020 yang 27-item — reviewer akan menandai mismatch standar sebagai kesalahan mayor.

---

## **LANGKAH 1: METHODS WRITING (PRISMA-ScR COMPLIANT)**

> **🎯 Tujuan:** Tulis Methods yang memenuhi PRISMA-ScR 22-item + JBI 9-stage methodology, mengkonsolidasi SEMUA keputusan metodologis dari Modul 2-8 dengan justifikasi.

### **Prompt untuk Claude:**
```
Saya akan menulis Methods section untuk Scoping Review.
Standar: PRISMA-ScR 22-item + JBI Manual Ch.11.

Berikut semua artifacts yang perlu di-konsolidasi:

=== DARI MODUL 2 ===
- Research question ScR (primary + 3 secondary, "what/how/which" style): [...]
- Gap type (A/B/C/D) + justifikasi pilih ScR (bukan SLR): [...]
- PCC + operational definitions: [...]
- Canonical terminology: [...]
- Scope justifications (3-lapis per batasan): [...]
- Protocol registration (OSF): [URL + DOI + tanggal]

=== DARI MODUL 3 ===
- Peer-reviewed databases + justifikasi: [...]
- Grey literature sources + justifikasi (jika digunakan, atau justifikasi mengapa tidak digunakan): [...]
- Search strings per sumber (Scopus, WoS, Google Scholar, ProQuest, dll.): [...]
- Filter specifications + justifikasi: [...]
- Tanggal pencarian per sumber: [YYYY-MM-DD]
- Update search policy: [...]

=== DARI MODUL 4-6 ===
- Export records per sumber, multi-source dedup stats
- PRISMA-ScR flow numbers: identified/screened/eligibility/included (breakdown
  peer vs grey)
- Kappa abstract screening: [X] (sub-kappa peer/grey jika berbeda)
- Kappa full-text screening: [X]
- Exclusion reasons tables (abstract + full-text stages)
- Inaccessible sources: [N] ([%] breakdown peer/grey)

=== DARI MODUL 7 ===
- Charting framework (JBI standard / PCC-driven / thematic / policy-oriented /
  custom) + justifikasi
- Pilot iteration details + revisions made ("iterative refinement")
- Charting method: AI-assisted + 20% spot-verification
- Optional QA: YES/NO
  - If YES: tool + justifikasi + kappa + non-exclusionary declaration
  - If NO: justifikasi mengapa tidak dilakukan (merujuk JBI)

=== DARI MODUL 8 ===
- Mapping approach: [Descriptive / Thematic / EGM / Hybrid]
- Thematic categorization method
- EGM construction details (jika applicable)
- Gap inventory methodology

Tulis Methods section PRISMA-ScR-compliant dengan struktur 22-item:

=== STRUKTUR METHODS (MENGIKUTI PRISMA-ScR) ===

1. **Protocol and Registration** (PRISMA-ScR item 5)
   - Protokol disusun a priori berbasis JBI Manual Ch.11
   - Registered di OSF [URL + DOI + tanggal]
   - Catat bahwa PROSPERO tidak menerima ScR

2. **Eligibility Criteria** (item 6)
   - PCC framework (bukan PICO)
   - Inclusion/exclusion dari Modul 2 L3 + reason codes ScR
   - Source types: peer-reviewed + grey literature (eksplisit sebutkan)

3. **Information Sources** (item 7)
   - Databases peer-reviewed: [list + justifikasi]
   - Grey literature sources: [list + justifikasi inklusi — atau justifikasi eksklusi jika tidak digunakan]
   - Date of last search per sumber

4. **Search** (item 8)
   - Search strings lengkap per database (Boolean)
   - Adapted strings untuk grey lit (simplified queries)
   - Filter specifications + justifikasi
   - Update search policy

5. **Selection of Sources of Evidence** (item 9)
   - Screening approach (dual-reviewer independent)
   - Software/tool screening
   - AI-assistance (Claude) declaration
   - Kappa calculation + interpretation
   - Conflict resolution process

6. **Data Charting Process** (item 10)
   - CHARTING (bukan extraction) terminology — eksplisit
   - Iterative refinement per Levac et al. (2010)
   - Pilot → refine → full charting
   - Calibration + dual-reviewer spot-verification
   - AI-assistance declaration

7. **Data Items** (item 11)
   - Variabel yang di-chart per framework
   - Mapping ke PCC components
   - Table atau list kolom charting form

8. **Critical Appraisal of Individual Sources of Evidence** (item 12)
   - Jika dilakukan: tool + justifikasi + non-exclusionary statement
   - Jika tidak: justifikasi mengapa (merujuk JBI dan PRISMA-ScR item 12 yang
     menyatakan ini opsional)
   - Contoh kalimat: "Following JBI scoping review methodology (Peters et al.,
     2020) and PRISMA-ScR guidelines (Tricco et al., 2018), we did not conduct
     formal critical appraisal of individual sources, as the purpose of our
     scoping review was to map the extent of evidence rather than assess
     effectiveness."

9. **Synthesis of Results** (item 13)
   - Mapping approach: descriptive numerical + thematic + EGM
   - Categorical analysis methodology
   - TIDAK ADA meta-analysis — ScR methodology tidak mencakup ini
   - Eksplisit sebutkan: "Consistent with scoping review methodology, we did
     not conduct meta-analysis or effect size pooling. Instead, we mapped
     evidence descriptively and thematically."

ATURAN PENTING:
- Setiap keputusan disertai justifikasi (bukan hanya "we used X")
- Semua parameter yang disebut bisa di-replicate (version numbers, thresholds,
  formulas)
- AI-assistance (Claude) di-declare eksplisit sesuai standar integritas akademik
- Kalimat "We did X" → sertakan alasan: "We did X because Y"
- JANGAN gunakan istilah "systematic review", "extraction", "meta-analysis",
  "effect size", "pooled" — ini scoping review

Length target: 1200-1800 kata (ScR Methods cenderung lebih panjang dari SLR
karena perlu mencakup justifikasi tipe sumber + charting iteration; jika
grey lit digunakan, juga mencakup strategi pencariannya).

Output: draft Methods section lengkap PRISMA-ScR compliant.
```

> **💡 Tips Claude:** Methods section adalah *perisai utama* terhadap kritik reviewer. Self-check: apakah 22 item PRISMA-ScR semua ter-cover (yang applicable)? Download PRISMA-ScR checklist dari http://prisma-statement.org/Extensions/ScopingReviews.aspx dan isi sebagai supplementary material.

---

## **LANGKAH 2: RESULTS WRITING (STRUKTUR CHARTING + MAPPING + EGM)**

> **🎯 Tujuan:** Struktur Results ScR MENGIKUTI framework charting dan mapping approach dari Modul 7-8, BUKAN struktur "descriptive + thematic + gap" yang generik tanpa urutan. Reviewer PRISMA-ScR akan mengkritik Results tanpa visualisasi EGM untuk ScR yang mengklaim gap identification.

### **Prompt untuk Claude:**
```
Saya akan menulis Results. 
Framework charting: [JBI standard / PCC-driven / Thematic / Policy-oriented / Custom]
Mapping approach: [Descriptive / Thematic / EGM / Hybrid]

=== INPUT ARTIFACTS ===

Dari Modul 8 L4 (mapping output):
- Descriptive numerical summary (temporal, geographic, study design, PCC
  components, quality)
- Categorical analysis per kolom kunci
- Thematic synthesis per RQ
- Cross-tabulation matrix
- Evidence Gap Map (EGM)
- Gap inventory (quantitative/qualitative/methodological/temporal)

Dari Modul 5-6 (PRISMA-ScR flow):
- Flow numbers lengkap: identification, screening, eligibility, included
- Breakdown peer vs grey per tahap

=== STRUKTUR RESULTS — IKUTI PRISMA-ScR + MAPPING APPROACH ===

**2.1. Selection of Sources of Evidence (WAJIB — PRISMA-ScR item 14)**
- Narasi dari PRISMA-ScR flow diagram
- Angka per tahap dengan breakdown peer vs grey
- Include Figure 1: PRISMA-ScR flow diagram

Contoh kalimat: "From the initial 1,247 records identified across [list
sumber], 342 remained after duplicate removal. Title/abstract screening
excluded 198 records, leaving 144 sources for full-text review. After
full-text screening, [N] sources were included in the final mapping
(peer-reviewed: [X]; grey literature: [Y])."

**2.2. Characteristics of Sources of Evidence (item 15)**
Descriptive numerical summary dari Modul 8 L1:
- Publication year distribution + trend
- Geographic distribution (JUJUR — sebutkan dominasi regional jika ada)
- Source type breakdown (peer vs grey)
- Document type breakdown (article, conference, thesis, report, policy brief,
  preprint)
- Study design breakdown (jika empiris)
- Sample size statistics (jika applicable)

Include Table 1: "Characteristics of Included Sources of Evidence"

**2.3. Critical Appraisal within Sources of Evidence (item 16, jika applicable)**
Jika QA dilakukan (Modul 7 L3):
- Quality distribution (HIGH/MODERATE/LOW) — descriptive only
- PENEGASAN: "These ratings are presented descriptively and were not used for
  exclusion, consistent with JBI scoping review methodology."

Jika QA tidak dilakukan:
- Bagian ini di-skip, catat di Methods: "In line with JBI and PRISMA-ScR
  guidelines, formal critical appraisal was not conducted."

**2.4. Results of Individual Sources of Evidence (item 17)**
Ringkasan individu per sumber bisa dalam:
- Summary table (Supplementary Material)
- Atau narasi kelompok per kategori

**2.5. Synthesis of Results — Thematic Mapping (item 18)**

Untuk mapping approach Thematic/Hybrid, struktur per komponen PCC atau tema:

**2.5.1. Concept Operationalization (inti ScR)**
- Bagaimana Concept didefinisikan/dioperasionalisasikan di literatur?
- Kategorisasi thematic (dari Modul 8 L2)
- Variasi dan tensions antar definisi
- Table 2: "Thematic Categories of [Concept] Operationalization"

**2.5.2. Context Mapping**
- Geographic, setting, kultural, kebijakan
- Cross-tabulation Concept × Context
- Figure 2: Geographic distribution visualization

**2.5.3. Methodological Characteristics**
- Design distribution
- Data collection approaches
- Analytical methods

**2.5.4. Key Findings dari Sumber (aggregated thematic)**
- Tema-tema utama yang muncul
- Konsistensi vs divergensi antar sumber

**2.6. Evidence Gap Map (HERO FIGURE — item 18)**
- Include Figure 3: EGM 2D heatmap/bubble/table
- Deskripsi naratif EGM dari Modul 8 L3
- Dense cells vs gap cells
- Interpretasi: area well-mapped vs sparse

**2.7. Identification of Gaps (fondasi Future Research Agenda)**
Dari Gap Inventory Modul 8 L3:
- Gap kuantitatif: [list]
- Gap kualitatif/konseptual: [list]
- Gap metodologis: [list]
- Gap temporal: [list]

Jangan bahas implikasi di sini — itu ke Discussion.

ATURAN TAMBAHAN:

1. BAHASA ScR — WAJIB:
   - Gunakan "we mapped", "we identified", "we characterized", "sources described"
   - JANGAN: "studies showed", "effect was significant", "X causes Y"
   - BOLEH: "X was reported in [N] studies", "common theme was..."

2. TEMPORAL AUDIT: pastikan tidak ada sitasi sumber yang publish SETELAH
   tanggal pencarian (Modul 3 L4). Flag dan hapus jika ada.

3. CONSISTENT TERMINOLOGY: gunakan canonical terminology (Modul 2 L3) secara
   konsisten.

4. FIGURES + TABLES WAJIB untuk ScR:
   - Figure 1: PRISMA-ScR flow diagram
   - Figure 2: Geographic/Temporal distribution
   - Figure 3: Evidence Gap Map (EGM) — hero figure
   - Table 1: Characteristics of Included Sources
   - Table 2: Thematic Categories
   - Supplementary: Full charting table

5. NON-INTERPRETATION: Results section presents mapping OBJECTIVELY, tanpa
   interpretasi (interpretasi ke Discussion).

Length target: 2500-3500 kata (ScR Results cenderung lebih panjang karena wajib
mencakup descriptive + thematic + EGM).

Output: draft Results lengkap dengan figure/table callouts.
```

> **💡 Tips Claude:** Reviewer PRISMA-ScR akan check: (a) PRISMA-ScR flow diagram ada dan correct? (b) EGM ada (jika mapping approach mencakup gap)? (c) Grey literature di-laporkan secara terpisah dari peer-reviewed di mana relevan? Jika salah satu absent, akan ditanyakan di review.

---

## **LANGKAH 3: DISCUSSION WRITING**

> **🎯 Tujuan:** Discussion ScR adalah INTERPRETASI mapping, bukan repetisi Results. Berbeda dari SLR, Discussion ScR fokus pada **implications triple-track (research/practice/policy)** dan **identification of gaps for future research**, bukan GRADE-based confidence assessments.

### **Prompt untuk Claude:**
```
Saya akan menulis Discussion. Inputs:

- Results (dari L2): [ringkasan key findings mapping]
- Interpretation package (dari Modul 8 L4): [answers to RQs, key mapping
  findings, surprising patterns, conceptual clarifications, gap-driven future
  research, triple-track implications, limitations self-audit]
- Prior reviews matrix (dari Modul 2 L2): [...]
- EGM + gap inventory (dari Modul 8 L3): [...]

Pikirkan secara mendalam dan pertimbangkan perspektif kritis sebelum menulis
setiap paragraf. Pastikan setiap klaim didukung mapping evidence, bukan
spekulasi. Untuk ScR, klaim harus DESCRIPTIVE, bukan CAUSAL/INFERENTIAL.

=== STRUKTUR DISCUSSION — 6 SUBSEKSI WAJIB (PRISMA-ScR ALIGNED) ===

**3.1. Summary of Evidence (2-3 paragraf, PRISMA-ScR item 19)**
- Menjawab RQ primary + secondary secara ringkas
- BUKAN repetisi Results — sintesis high-level mapping
- Fokus pada "apa yang dipetakan" dan "apa yang diidentifikasi sebagai gap"

**3.2. Geographic and Contextual Honesty (1-2 paragraf) — DI AWAL DISCUSSION**
- Acknowledge bias geografis/sumber JIKA ADA
- Template: "A notable characteristic of this mapping is the concentration of
  sources from [region] ([X]%). This reflects [structural explanation:
  research infrastructure, grey literature availability, language of
  publication] and should frame the interpretation of subsequent findings."
- Untuk ScR Indonesia: jika 80% dari Indonesia, JANGAN klaim "Southeast Asian
  pattern"
- Alternatif framing: "Indonesian context with implications for similar
  emerging economies"
- Diskusikan kawasan/sumber underrepresented + implikasi mapping

**3.3. Conceptual Landscape dan Dialog with Literature (2-3 paragraf)**
- Bagaimana mapping ini memperkaya pemahaman konsep?
- Konsep yang ditemukan terkonsep dengan beragam cara → implikasi terminologis
- Konsep yang matang vs emerging
- Dialog dengan prior scoping reviews dan SLR sejenis (dari Modul 2 L2)
- Jika Tipe Gap B (ambiguitas konseptual): rekomendasi unifikasi atau plurality

**3.4. Nature and Extent of Evidence (1-2 paragraf)**
- Karakterisasi evidence (bukan effect size):
  - Apakah bukti seimbang antar kategori atau skewed?
  - Apakah bukti empiris dominan, atau konseptual/policy?
  - Apakah grey lit mewarnai mapping secara signifikan?
- Implikasi untuk generalisasi mapping

**3.5. Evidence Gaps dan Implications (3-4 paragraf — INTI DISCUSSION ScR)**

**3.5.1. Gaps Identified from Mapping**
Ringkas gap inventory (Modul 8 L3):
- Gap kuantitatif (kombinasi PCC sparse)
- Gap kualitatif/konseptual
- Gap metodologis
- Gap temporal

**3.5.2. Implications for Research (TRIPLE-TRACK 1)**
- Prioritas riset yang muncul dari gap
- Framework/metodologi yang perlu dikembangkan
- Konseptual clarifications yang dibutuhkan

**3.5.3. Implications for Practice (TRIPLE-TRACK 2)**
- Aplikasi yang didukung mapping
- Caveats untuk praktisi (area dengan bukti lemah)
- Rekomendasi kontekstual

**3.5.4. Implications for Policy (TRIPLE-TRACK 3)**
- Insight kebijakan dari peta bukti
- Stakeholder yang perlu dilibatkan
- Area kebijakan yang underserved oleh bukti

**3.6. Limitations (3-tier, dengan mitigasi per limitasi — PRISMA-ScR item 20)**

REVIEW-LEVEL LIMITATIONS:
- Database coverage (peer-reviewed breadth)
- Grey lit coverage + inaccessibility
- Geographic/language bias
- Timeframe
- Potential missed sources

SOURCE-LEVEL LIMITATIONS:
- Reporting quality (NR fields prevalence)
- Heterogeneity in operationalization
- Grey lit without formal methods sections

MAPPING-LEVEL LIMITATIONS:
- Subjectivity in thematic categorization (meski dual-reviewer)
- Iterative charting means kategori awal mungkin berbeda dari final
- EGM granularity decisions

ScR-SPECIFIC DISCLAIMERS (wajib):
- "This scoping review maps the evidence but does not assess effectiveness or
  causal relationships"
- "Quality of included sources varied and was reported descriptively, not used
  for exclusion (per JBI guidelines)"
- "No meta-analysis or pooled effect was conducted; such synthesis is beyond
  the methodology of scoping reviews"

ATURAN: setiap limitasi + 1 kalimat mitigasi atau implikasi untuk generalisasi.

ATURAN PENTING:
1. TIDAK BOLEH CAUSAL/INFERENTIAL CLAIMS:
   - BUKAN: "Intervention X is effective for [outcome]"
   - BENAR: "[N] sources reported applying intervention X; effectiveness was
     not assessed as this is beyond scoping review methodology"

2. TIDAK BOLEH REPETISI RESULTS: Jika Anda mengutip angka, sertakan
   interpretasi baru.

3. KUTIPAN PRIOR REVIEWS (Modul 2 L2): wajib muncul eksplisit.

4. TERMINOLOGI KANONIKAL: gunakan konsisten (Modul 2 L3).

5. HEDGING TEPAT: "mapping indicates", "evidence points to", "sources
   describe" — bukan "proves", "demonstrates significantly".

Length target: 2500-3500 kata.

Output: draft Discussion dengan 6 subseksi lengkap.
```

> **💡 Tips Claude:** Reviewer akan check: (a) apakah geographic bias diakui DI AWAL Discussion (bukan hanya di Limitations)? (b) apakah triple-track implications (research/practice/policy) eksplisit? (c) apakah TIDAK ADA causal/inferential claim? (d) apakah Limitations mencakup ScR-specific disclaimers? Keempat ini sering lemah di draft pertama.

---

## **LANGKAH 4: FUTURE RESEARCH AGENDA (SUBSEKSI KHUSUS)**

> **🎯 Tujuan:** Future Research Agenda adalah SUBSEKSI TERSENDIRI dengan matriks prioritas, turunan langsung dari Gap Inventory Modul 8 L3. Untuk ScR, ini sering jadi kontribusi utama — reviewer mengharapkan agenda yang actionable.

### **Prompt untuk Claude:**
```
Saya akan menulis Future Research Agenda sebagai subseksi khusus.

INPUTS:
- Gap inventory (Modul 8 L3): kuantitatif / kualitatif / metodologis / temporal
- EGM sparse cells (Modul 8 L3)
- Prior reviews matrix gaps (Modul 2 L2)
- Research questions yang belum fully answered by mapping

=== STRUKTUR ===

**4.1. Pendahuluan Agenda (1 paragraf)**
Justify mengapa agenda ini kritis + bagaimana turunan dari mapping findings.
Tekankan: scoping review mengidentifikasi gap, ini adalah agenda yang ScR
buka untuk penelitian lanjutan.

**4.2. Matriks Prioritas (tabel)**

| Priority | Timeframe | Rationale (linked to gap) | Research Question | Suggested Methodology |
|----------|-----------|---------------------------|-------------------|----------------------|
| HIGH | 1-2 years | [gap kuantitatif spesifik] | [RQ] | [mis. cross-sectional survey, qualitative case study, SLR] |
| HIGH | 1-2 years | [gap konseptual spesifik] | [RQ] | [conceptual paper, Delphi study] |
| MEDIUM | 2-3 years + infrastruktur | [gap metodologis] | [RQ] | [longitudinal study, mixed-methods] |
| LONG-TERM | 3+ years | [gap teoretis] | [RQ] | [grand theory development] |

Aturan:
- Setiap agenda HARUS trace balik ke gap konkret dari EGM/Gap Inventory
- Formulasikan sebagai RESEARCH QUESTION (bukan topik umum)
  ❌ "Future research on generative AI in education"
  ✓ "How do Indonesian faculty members in non-metropolitan universities
     integrate generative AI into undergraduate teaching, and what
     institutional/cultural factors enable or constrain adoption?"
- Minimum 3 HIGH priority, 2-3 MEDIUM, 1-2 LONG-TERM
- Suggested methodology eksplisit (ScR sering diikuti SLR atau empirical study)

**4.3. Prioritasi Rationale (2-3 paragraf)**

Untuk HIGH priority agenda:
- Mengapa addressable sekarang?
- Data/infrastruktur yang tersedia
- Impact potensial

Untuk LONG-TERM agenda:
- Mengapa tidak bisa diaddress sekarang?
- Apa yang perlu berkembang dulu?

**4.4. Methodological Advancements Needed (1-2 paragraf)**
- Gap metodologis yang teridentifikasi dari mapping
- Rekomendasi: dataset baru, framework baru, measurement tools baru
- Jika ScR adalah prekursor untuk SLR: sebutkan SLR lanjutan sebagai next step

**4.5. Scoping Review → SLR Pathway (jika Tipe Gap D)**
Jika ScR ini dirancang sebagai prekursor untuk SLR:
- Sebutkan eksplisit bahwa ScR mapping menunjukkan kesiapan untuk SLR
- Identifikasi subset spesifik yang dapat menjadi fokus SLR (misalnya,
  intervensi dengan bukti homogen cukup)
- Outline methodology SLR yang direkomendasikan

Length target: 1000-1500 kata.

Output: draft Future Research Agenda siap dipakai sebagai subseksi manuskrip.
```

> **💡 Tips Claude:** Kalau Future Research Agenda Anda berisi "more research needed", itu FAIL. Setiap item harus (a) specific gap dari mapping, (b) research question formulation, (c) prioritization rationale, (d) suggested methodology. Reviewer ScR khusus akan test kualitas agenda ini karena gap identification adalah nilai utama ScR.

---

## **LANGKAH 5: INTRODUCTION WRITING (5 SUBSEKSI WAJIB)**

> **🎯 Tujuan:** Introduction setelah Results+Discussion+Future Research selesai. Urutan reverse-writing ini memastikan Anda TAHU apa yang akan di-klaim, sehingga Intro dapat di-tune untuk preview mapping findings.

### **Prompt untuk Claude:**
```
Saya akan menulis Introduction untuk Scoping Review.

=== DARI MODUL 2 ===
- Topic + research area: [...]
- Gap characterization + tipe gap (A/B/C/D): [...]
- Justifikasi pilih ScR (bukan SLR) merujuk Munn et al. (2018): [...]
- Prior reviews matrix (untuk subseksi "Review of Prior Reviews"): [...]
- PCC + operational definitions: [...]
- Canonical terminology: [...]
- Scope justifications (3-lapis per batasan): [...]
- Research questions: [primary + secondary, "what/how/which" style]

=== DARI MODUL 7-8-9 ===
- Charting framework: [JBI/PCC-driven/Thematic/Policy/Custom]
- Mapping approach: [Descriptive/Thematic/EGM/Hybrid]
- Key findings (preview): [...]
- Geographic/source context: [...]

=== STRUKTUR — 5 SUBSEKSI WAJIB ===

**5.1. Background (2-3 paragraf)**
- Field overview + importance
- Current state of knowledge (high-level, cite foundational works)
- Why this field matters now (contextual relevance — SDGs, policy,
  technological shifts, post-COVID)

**5.2. Review of Prior Reviews (SUBSEKSI TERSENDIRI — KRITIS)**
Panduan PRISMA-ScR + reviewer EKSPLISIT meminta ini.

Konten:
- Referensi prior reviews matrix dari Modul 2 L2 (3-5 review terdekat —
  prioritas: scoping review, evidence gap map, SLR terkait)
- Untuk masing-masing: scope, methodology (ScR/SLR/other), key findings,
  limitations
- Paragraf "Sintesis Novelty": apa yang SUDAH dipetakan prior reviews
  kolektif, apa yang BELUM atau butuh update, dan mengapa ScR ini MENUTUP
  gap

Format bisa dalam bentuk paragraf naratif atau tabel inline (tergantung
target journal style).

Length: 400-600 kata.

**5.3. Problem Statement dengan Tipe Gap + Justifikasi ScR (1-2 paragraf)**

Argumentasi gap yang EKSPLISIT + justifikasi pilih ScR:

- TIPE A (Fragmentasi pemetaan): "Literature on [topic] remains fragmented
  across [sub-topics], with no systematic mapping of the evidence landscape.
  A scoping review is needed to map the extent, range, and nature of
  evidence [Munn et al., 2018]."

- TIPE B (Ambiguitas konseptual): "The concept of [X] has been
  operationalized in diverse ways across studies, with no prior review
  clarifying these conceptualizations. A scoping review is appropriate to
  identify and compare operational definitions."

- TIPE C (Ketiadaan karakterisasi): "No prior review has systematically
  examined how research on [topic] has been conducted — the types of designs,
  populations, or contexts studied. A scoping review can characterize this
  methodological landscape."

- TIPE D (Prekursor SLR): "While primary studies exist on [topic], evidence
  heterogeneity precludes immediate systematic review. A scoping review is a
  necessary precursor to map the available evidence and identify feasible
  sub-questions for subsequent SLR."

Rujuk Munn et al. (2018) secara eksplisit untuk justifikasi metodologis.

**5.4. Scope Justification (1-2 paragraf)**
Justify setiap batasan SECARA EKSPLISIT (dari Modul 2 L4, 3-lapis).

Per batasan (dalam paragraf terintegrasi):
- Mengapa population didefinisikan seperti ini? (atau N/A — conceptual)
- Mengapa rentang tahun X-Y?
- Mengapa geografis/setting tertentu?
- Mengapa bahasa tertentu?
- Mengapa tipe sumber (peer-reviewed + grey lit)?

Rujukan teoretis + metodologis + praktis dari Modul 2 L4.

**5.5. Research Questions + Objectives (1 paragraf)**
- Primary research question (ScR-style: "what/how/which")
- 3 secondary questions
- Brief preview objektif review (tanpa spoil findings)
- Sebutkan framework charting + mapping approach yang digunakan

ATURAN:
- JANGAN repetisi dengan Discussion atau Conclusion (akan di-audit di L10)
- Gunakan canonical terminology secara konsisten
- Jangan klaim "global" jika data Anda regional (disclose di 5.4 scope
  justification)
- Preview mapping approach (descriptive/thematic/EGM) yang Anda adopsi
- EKSPLISIT sebutkan: "This is a scoping review conducted following JBI
  methodology and reported according to PRISMA-ScR guidelines."

Length target: 1200-1800 kata TOTAL.

Output: draft Introduction dengan 5 subseksi terstruktur.
```

> **💡 Tips Claude:** "Review of Prior Reviews" + justifikasi pilih ScR vs SLR adalah *marquee features* untuk ScR manuscript. Jika Intro Anda tidak ada subseksi ini + justifikasi metodologis, reviewer akan langsung minta revisi mayor.

---

## **LANGKAH 6: CONCLUSIONS WRITING (LEAN VERSION)**

> **🎯 Tujuan:** Conclusions lean (3-4 paragraf), tidak duplikat Future Research (sudah di L4) atau Discussion (sudah detail di L3).

### **Prompt untuk Claude:**
```
Saya akan menulis Conclusions untuk ScR. Future Research Agenda sudah dibahas
terpisah (L4). Implications for research/practice/policy sudah di Discussion (L3).

INPUTS:
- Key mapping findings (3-5 headline): [...]
- Conceptual clarifications (jika applicable): [...]
- Triple-track implications highlights: [...]

=== STRUKTUR (3-4 PARAGRAF) ===

**Paragraf 1 — Main Mapping Findings:**
- Direct answer ke primary research question (ScR-style, descriptive)
- Key mapping evidence (brief, tidak repetisi Results)
- Highlight EGM/gap identification contributions

**Paragraf 2 — Conceptual/Methodological Contributions:**
- Apa yang mapping ini tambahkan ke pemahaman lanskap bukti?
- Konseptual clarifications (jika Tipe Gap B)
- Methodological insights (jika Tipe Gap C)

**Paragraf 3 — Overarching Implications:**
- Ringkas triple-track implications (research + practice + policy)
- Tetap grounded di evidence dari mapping
- Jangan overclaim — hedging tepat ("This mapping indicates", "Sources
  suggest")

**Paragraf 4 — Brief Forward Look (OPTIONAL)**
- 1-2 kalimat mengarahkan pembaca ke Future Research Agenda subseksi
- JANGAN detail future research di sini (sudah di L4)

ATURAN:
- JANGAN repetisi Discussion substansial
- Canonical terminology konsisten
- Geographic/source honesty: jika bias disclosed di Discussion, jangan
  overclaim di Conclusions
- TIDAK ADA causal/inferential claim (prinsip ScR)
- Length: 500-700 kata

Output: draft Conclusions lean.
```

---

## **LANGKAH 7: REFERENCES — FORMAT + VERIFY + TEMPORAL AUDIT + COMPLETENESS**

> **⚠️ PERINGATAN KRITIS:** Ini tahap paling rawan hallucination Claude. JANGAN minta Claude membuat referensi dari nol. Hanya format, verify, dan audit yang sudah ada.

### **7.1 Format Referensi yang Sudah Ada:**

```
[Upload file manuscript atau paste daftar referensi yang sudah ada]

TARGET JOURNAL: [nama journal atau style: APA 7th / Vancouver / Harvard / etc.]

PENTING: JANGAN generate referensi baru. Hanya format yang SUDAH ADA.

1. FORMAT REFERENCE LIST:
   - Format sesuai style [nama style]
   - Ensure completeness setiap entri (author, year, title, journal, vol,
     pages, DOI, URL untuk grey lit)
   - Grey lit: cantumkan URL + tanggal akses jika tidak ada DOI
   - Urutkan sesuai aturan journal

2. IN-TEXT CITATION CHECK:
   - Verify semua in-text citations ada di reference list
   - Cek konsistensi format citation
   - Identifikasi orphaned citations

3. CONSISTENCY CHECK:
   - Cek duplikasi referensi
   - Standardisasi format author names dan organization names
   - Pastikan DOI ada jika diperlukan (untuk peer-reviewed)
   - Grey lit: pastikan URL masih aktif (gunakan Wayback Machine jika URL mati)

Output: formatted reference list + daftar orphaned citations + grey lit URL
status.
```

### **7.2 Verifikasi Referensi via Web (WAJIB):**

```
Saya memiliki daftar referensi yang perlu diverifikasi:
[Paste daftar referensi]

Gunakan web search untuk memverifikasi setiap referensi.

Untuk peer-reviewed:
1. Cari di Google Scholar / CrossRef / database akademik
2. Verifikasi: Author, Year, Title, Journal, Volume, Pages, DOI
3. Status: ✅ VERIFIED / ⚠️ PARTIAL / ❌ NOT FOUND

Untuk grey literature:
1. Cek URL masih aktif (coba akses langsung)
2. Jika mati, cek di Wayback Machine (web.archive.org)
3. Verifikasi: Author/Organization, Year, Title, URL, Retrieved date
4. Status: ✅ VERIFIED / ⚠️ URL-DEAD-WAYBACK-AVAILABLE / ❌ INACCESSIBLE

Sajikan hasil dalam tabel.
```

> **💡 Tips:** Referensi ❌ NOT FOUND harus Anda cek manual. Untuk grey lit dengan URL mati, gunakan Wayback Machine untuk mendapatkan versi arsip + cantumkan URL arsip di referensi.

### **7.3 Audit Konsistensi Temporal:**

```
Search date per sumber (dari Modul 3 L4): [YYYY-MM-DD]

Audit daftar referensi saya terhadap window pencarian:

1. Kategorisasi referensi berdasarkan publication date:
   - BEFORE search date: OK, bisa jadi sumber yang dipetakan OR konteks
   - AFTER search date: perlu audit
     * Jika kategori "context citation" (Intro/Discussion): OK tapi flag
     * Jika di-include sebagai SUMBER YANG DIPETAKAN: INKONSISTEN — harus
       dihapus atau di-justify sebagai update-search

2. Flag referensi yang "publish after search date dan digunakan sebagai
   sumber yang dipetakan":
   - Hapus dari charting table
   - ATAU justifikasi sebagai update-search addition (Modul 3 L4 policy)

3. Output: audit report dengan flagged references + recommendations.
```

### **7.4 Completeness + Foundational Works Check:**

```
Gunakan web search untuk:

1. FOUNDATIONAL WORKS CHECK (khusus ScR methodology):
   - Arksey & O'Malley (2005) — original 5-step framework
   - Levac et al. (2010) — methodological enhancement
   - Peters et al. (2020) JBI Manual Ch.11 — standar saat ini
   - Tricco et al. (2018) PRISMA-ScR
   - Munn et al. (2018) — when to choose ScR vs SLR
   
   Cek apakah foundational works ini di-cite. Jika absent: WAJIB tambahkan.

2. TOPIC FOUNDATIONAL WORKS:
   - Di bidang [topic], ada foundational works yang umumnya disitasi?
   - Cek apakah referensi saya mencakup foundational works ini

3. GREY LITERATURE COMPLETENESS:
   - Apakah referensi mencakup laporan lembaga kunci yang di-chart?
   - Pastikan WHO/Bappenas/Kemendikbud/UNESCO yang di-include punya entry
     referensi lengkap (organization, year, title, URL, retrieved date)

Output: audit report + rekomendasi additional references (semua harus lolos
7.2 verifikasi dan 7.3 temporal audit).
```

---

## **LANGKAH 8: ABSTRACT WRITING (PRISMA-ScR ABSTRACT CHECKLIST)**

### **Prompt untuk Claude:**
```
Saya akan menulis structured abstract untuk Scoping Review.
Target: 250-300 kata, mengikuti PRISMA-ScR abstract items (12 items).

INPUTS:
- Methods summary: [...]
- Results summary (mapping findings): [...]
- Discussion key points: [...]
- Framework charting: [...]
- Mapping approach: [...]
- Final N sources: [breakdown peer/grey]
- Geographic coverage: [jujur]
- Top-3 future research priorities: [...]

=== STRUKTUR ABSTRACT (4 BAGIAN, PRISMA-ScR ITEM 2) ===

**Background & Objective (2-3 kalimat):**
- Problem statement + rationale
- ScR objective
- Gap type yang ditarget
- Eksplisit sebutkan: "scoping review" (bukan "systematic review")

**Methods (3-4 kalimat):**
- WAJIB cantum:
  * "scoping review following JBI methodology and PRISMA-ScR guidelines"
  * Search: [databases + grey lit sources + date range + date of search]
  * Eligibility: PCC-based (eksplisit)
  * Charting framework: [...]
  * Mapping approach: [descriptive/thematic/EGM]
  * Final N included (breakdown peer/grey)

**Results (4-5 kalimat):**
- Number of sources mapped (peer-reviewed: X, grey lit: Y)
- Key mapping findings (2-3 poin deskriptif)
- Geographic coverage JUJUR: "Sources predominantly originated from [region]
  ([X]%)"
- Key gaps identified (brief)
- EGM mention (jika hero figure)

**Conclusions (2-3 kalimat):**
- Main mapping conclusions (descriptive, NOT causal)
- Overarching gap insights
- Top-3 future research priorities (brief mention)
- Methodological contribution (jika applicable)

ATURAN:
1. WAJIB CANTUM di abstract:
   [ ] "scoping review" (eksplisit, bukan "review" saja)
   [ ] PCC framework
   [ ] JBI + PRISMA-ScR guideline adherence
   [ ] Jumlah final sources (breakdown peer/grey)
   [ ] Grey literature inclusion
   [ ] Geographic coverage (jujur, bukan global jika regional)
   [ ] Key gaps identified
   [ ] Top-3 future research priorities (brief)

2. ANTI-OVERCLAIMING:
   - JANGAN: "effective", "significant", "causes", "proves"
   - BOLEH: "mapped", "identified", "characterized", "described"
   - Jika 80% Indonesia, JANGAN "global scoping review" — "Indonesian context"

3. NO JARGON: hindari istilah teknis yang tidak dijelaskan.

Output: draft abstract 250-300 kata dengan checklist compliance.
```

---

## **LANGKAH 9: TITLE CREATION**

### **Prompt untuk Claude:**
```
Saya akan membuat title untuk Scoping Review. Berikan 3-5 alternatif dengan
justifikasi.

INPUTS:
- Abstract (dari L8): [...]
- Charting framework + mapping approach
- Geographic coverage: [jujur]
- Key mapping findings
- Tipe gap

=== TITLE CRITERIA (7 POIN) ===

1. **DESCRIPTIVE**: jelas tentang topik + approach
2. **SPECIFIC**: include key components
3. **METHODOLOGY EKSPLISIT**: WAJIB mencantumkan "scoping review" — ini aturan
   PRISMA-ScR item 1
4. **CONCISE**: 12-18 kata optimal untuk ScR
5. **ENGAGING**: attractive untuk readers
6. **SEARCHABLE**: include keywords untuk discoverability
7. **GEOGRAPHIC HONESTY**:
   - JANGAN klaim "global" jika dominasi regional
   - Alternatif framing:
     * "Indonesian context: [topic]"
     * "[Topic] in Southeast Asian higher education"
     * "Evidence from Indonesia: [topic]"

=== ANTI-OVERCLAIMING CHECKLIST ===

Untuk setiap title candidate:
- [ ] "Scoping review" EKSPLISIT?
- [ ] Geographic scope jujur?
- [ ] Tidak klaim effectiveness/causality?
- [ ] Framework tidak di-misrepresent?

=== FORMAT ALTERNATIF TITLE ===

Template umum untuk ScR:
- "[Topic]: A Scoping Review"
- "Mapping [Concept] in [Context]: A Scoping Review"
- "[Region-qualified topic]: A Scoping Review"
- "Toward Understanding [topic]: A Scoping Review of [evidence type]"
- "[Concept] in [Context]: Evidence from a Scoping Review"

=== OUTPUT: 3-5 ALTERNATIF ===

Untuk tiap alternatif:
- Title candidate
- Word count
- Keywords yang tercakup
- "Scoping review" ditampilkan? PASS/FAIL
- Geographic scope honesty: PASS/FAIL
- Rationale (2-3 kalimat)

Di akhir, REKOMENDASI title terbaik dengan justifikasi.
```

---

## **LANGKAH 10: COHERENCE AUDIT + PRISMA-ScR COMPLIANCE + PROOFREAD**

> **🎯 Tujuan:** Final quality gate sebelum submit. Audit repetisi, konsistensi terminologi, PRISMA-ScR 22-item compliance, dan professional proofread.

### **10.1 Audit Repetisi Intro↔Discussion↔Conclusion:**

```
[Upload atau paste: Introduction + Discussion + Conclusions lengkap]

Cek repetisi yang berlebihan antara 3 bagian:

1. IDENTIFIKASI KALIMAT REPETITIF:
   - Kalimat atau frasa yang muncul nyaris identik di ≥2 bagian
   - Ide yang disampaikan 3+ kali dalam manuskrip
   - Claim yang dibuat berulang tanpa menambah nuansa

2. PATTERN YANG HARUS DIHINDARI:
   - "This scoping review maps the evidence" muncul di Intro, Methods, Discussion,
     Conclusion
   - "Our findings show X" + "This mapping demonstrated X" + "We conclude that X"

3. REKOMENDASI PER BAGIAN:
   - INTRODUCTION: bukan tempat menyampaikan findings — hanya preview objektif
   - DISCUSSION: interpretasi mapping + dialog, bukan repetisi angka Results
   - CONCLUSIONS: synthesis singkat, bukan repetisi Discussion

Output: daftar kalimat/frasa repetitif + saran rewrite per bagian.
```

### **10.2 Audit Konsistensi Terminologi:**

```
Canonical terminology (dari Modul 2 L3):
- Term kanonikal: [...]
- Definisi baku: [...]
- Alternatif yang DITOLAK: [...]

Scan seluruh manuskrip:

1. IDENTIFIKASI INKONSISTENSI:
   - Apakah kanonikal dipakai konsisten?
   - Apakah alternatif yang DITOLAK muncul?
   - Apakah ada sinonim tidak disengaja?

2. CEK KONSISTENSI SCR TERMINOLOGY:
   - "Scoping review" konsisten (bukan "systematic review", "literature review")?
   - "Charting" konsisten (bukan "extraction")?
   - "Mapping" konsisten (bukan "synthesis", "meta-analysis")?
   - "PCC" konsisten (bukan "PICO")?
   - "Sources" atau "evidence" konsisten (bukan "studies" saja)?

3. REKOMENDASI PERBAIKAN:
   - Replace inkonsistensi dengan terminologi yang tepat

Output: daftar inkonsistensi + replacement suggestions.
```

### **10.3 PRISMA-ScR 22-Item Compliance Check:**

```
Download PRISMA-ScR checklist dari:
http://prisma-statement.org/Extensions/ScopingReviews.aspx

Audit manuskrip saya terhadap 22 item:

TITLE:
[ ] Item 1: Identify the report as a scoping review

ABSTRACT:
[ ] Item 2: Structured summary (objectives, eligibility criteria, sources,
    charting methods, results, conclusions)

INTRODUCTION:
[ ] Item 3: Rationale
[ ] Item 4: Objectives (PCC-based)

METHODS:
[ ] Item 5: Protocol and registration
[ ] Item 6: Eligibility criteria
[ ] Item 7: Information sources
[ ] Item 8: Search
[ ] Item 9: Selection of sources of evidence
[ ] Item 10: Data charting process
[ ] Item 11: Data items
[ ] Item 12: Critical appraisal (opsional — jika skip, justifikasi)
[ ] Item 13: Synthesis of results

RESULTS:
[ ] Item 14: Selection of sources (PRISMA-ScR flow diagram)
[ ] Item 15: Characteristics of sources
[ ] Item 16: Critical appraisal results (jika dilakukan)
[ ] Item 17: Results of individual sources
[ ] Item 18: Synthesis of results

DISCUSSION:
[ ] Item 19: Summary of evidence
[ ] Item 20: Limitations
[ ] Item 21: Conclusions (termasuk implications + future directions)

FUNDING:
[ ] Item 22: Funding sources

Untuk setiap item, tunjukkan di section/paragraf mana item tsb di-cover.
Jika item absent: flag untuk revisi.

Output: completed PRISMA-ScR checklist (akan jadi supplementary material).
```

### **10.4 Professional Proofread Recommendation:**

```
Setelah L10.1, L10.2, L10.3, manuskrip masih memerlukan:

1. PROFESSIONAL PROOFREAD (highly recommended untuk non-native English):
   - Services: editage.com, enago.com, atau journal-recommended
   - Fokus: grammar, academic register, clarity

2. SELF-CHECK FINAL:
   - Tables/figures sesuai panggilan di teks?
   - Nomor figure/table konsisten?
   - Appendix/Supplementary complete?
   - All citations have references + vice versa?
   - Grey lit URL + retrieved date lengkap?

3. COMPLIANCE CHECK vs JOURNAL REQUIREMENTS:
   - Word count (total + abstract)?
   - Reference style?
   - Figure quality (DPI)?
   - Supplementary materials format?
   - PRISMA-ScR checklist sebagai supplementary?

4. ETHICAL DECLARATION:
   - Protocol registration (OSF) disclosed?
   - AI-assistance (Claude) dideklarasikan di Methods?
   - Funding sources?
   - Conflict of interest?

Output: final checklist sebelum submit.
```

---

## **HASIL AKHIR**

### **Complete Manuscript Package ScR (v1):**
```
=== MANUSCRIPT WRITING RESULTS (SCR) ===

SECTIONS (urutan final di manuskrip):
- Title: "Scoping review" eksplisit + geographic honesty
- Abstract: PRISMA-ScR item 2 (4 bagian, 250-300 kata)
- Introduction (5 subseksi):
  - Background
  - Review of Prior Reviews (subseksi tersendiri)
  - Problem statement dengan tipe gap + justifikasi ScR (Munn et al. 2018)
  - Scope justification (3-lapis per batasan)
  - Objectives + RQ (PCC-based)
- Methods (PRISMA-ScR items 5-13)
- Results (PRISMA-ScR items 14-18, struktur charting + mapping + EGM)
- Discussion (6 subseksi):
  - Summary of evidence
  - Geographic/source honesty (DI AWAL)
  - Conceptual landscape dialog
  - Nature and extent of evidence
  - Evidence gaps + triple-track implications (research/practice/policy)
  - Limitations 3-tier dengan mitigasi + ScR-specific disclaimers
- Future Research Agenda (subseksi tersendiri dengan matriks prioritas)
- Conclusions (lean, 3-4 paragraf)
- References (formatted + verified + temporal audit + foundational ScR works)
- Funding + Ethical Declaration

WRITING SEQUENCE (reverse-writing):
1. Methods (L1)
2. Results (L2)
3. Discussion (L3)
4. Future Research Agenda (L4)
5. Introduction (L5)
6. Conclusions (L6)
7. References (L7)
8. Abstract (L8)
9. Title (L9)
10. Coherence + PRISMA-ScR Compliance Audit (L10)

QUALITY GATES (dari L10):
- Repetisi audit: passed
- Terminology consistency (incl. ScR-specific): passed
- PRISMA-ScR 22-item compliance: all items covered
- Professional proofread: done
- Journal requirements: compliant

REVIEWER-PROOF ELEMENTS (ScR-specific):
- "Scoping review" eksplisit di Title, Abstract, Methods
- PCC framework (bukan PICO) di seluruh manuskrip
- PRISMA-ScR flow diagram (bukan PRISMA 2020)
- Grey literature transparency (reporting terpisah dari peer-reviewed)
- Critical appraisal: non-exclusionary (jika dilakukan) atau dijustifikasi tidak dilakukan
- Charting (bukan extraction) dengan iterative refinement
- EGM (jika mapping mencakup gap identification)
- Triple-track implications (research/practice/policy)
- Future Research Agenda dengan matriks prioritas
- TIDAK ADA causal/effect/meta-analysis claims
- JBI Manual Ch.11 + PRISMA-ScR + Munn et al. (2018) dalam references
- Protocol registration di OSF disclosed

SUBMISSION READY: YES
```

---

## **TROUBLESHOOTING**

**Problem 1: Draft Introduction masih "descriptive" tanpa argumentasi gap + justifikasi ScR**
- Check: apakah tipe gap (A/B/C/D) dari Modul 2 L1 di-articulate eksplisit?
- Check: apakah "Review of Prior Reviews" subseksi ada?
- Check: apakah justifikasi pilih ScR (bukan SLR) merujuk Munn et al. 2018?
- Solusi: kembali ke L5, rewrite dengan template problem statement

**Problem 2: Discussion ada causal/effect claims**
- ScR TIDAK dapat menarik kesimpulan kausal
- Self-audit: setiap paragraf, apakah ada "X causes Y", "effective", "significant"?
- Solusi: reframe jadi descriptive ("N sources reported X"; "evidence describes Y")

**Problem 3: Klaim "global" di Title/Abstract padahal regional**
- Audit dengan L9 anti-overclaiming checklist
- Solusi: pakai alternatif framing ("Indonesian context", "Southeast Asian")

**Problem 4: Future Research hanya 1 paragraf dengan "more research needed"**
- Solusi: kembali ke L4, buat matriks prioritas dengan minimum 3 HIGH + 2-3 MEDIUM + 1-2 LONG-TERM
- Setiap item sebagai RQ spesifik + suggested methodology

**Problem 5: Terminologi inkonsisten (ScR vs SLR)**
- Jangan campur "systematic review" dan "scoping review"
- Jangan campur "extraction" dan "charting"
- Jangan campur "PICO" dan "PCC"
- Solusi: L10.2 audit, replace semua instances

**Problem 6: PRISMA-ScR item tidak semua ter-cover**
- Item 12 (critical appraisal): jika skip, WAJIB justifikasi mengapa (merujuk JBI)
- Item 5 (protocol): jika tidak registered, akui di Limitations
- Solusi: L10.3 compliance check, isi semua item atau justifikasi absence

**Problem 7: Reviewer menyampaikan "meta-analysis missing"**
- Jelaskan: ScR bukan SLR — meta-analysis bukan bagian methodology
- Rujuk JBI Manual Ch.11 + Munn et al. (2018) + PRISMA-ScR item 13
- Response letter: cite specific methodology references

**Problem 8: Grey lit URL dead di referensi**
- Gunakan Wayback Machine untuk mendapat archive
- Format ref: "[Org]. ([Year]). [Title]. Retrieved [date] from [URL].
  Archived at [Wayback URL]"

**Problem 9: Reviewer menanyakan "why not PROSPERO registration?"**
- Jelaskan: PROSPERO tidak menerima scoping reviews
- Rujuk kebijakan PROSPERO + alternatif (OSF, Figshare)
- Ini pertanyaan umum karena reviewer SLR-trained

**Problem 10: Hero figure (EGM) sulit dipublikasikan (formatting/resolution)**
- Render dalam software profesional (R ggplot2, Python matplotlib, Excel dengan conditional formatting)
- DPI minimum 300 untuk print, PNG/PDF untuk submission
- Konsultasi journal style guide untuk aspect ratio
- Jika EGM sangat kompleks: sediakan versi simple di main text + detailed di supplementary

---
