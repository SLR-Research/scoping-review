# Modul 8: Mapping, Synthesis, dan Evidence Gap Map (Claude Cowork)

> **🎯 Output Modul Ini:** Mapping lengkap (descriptive + thematic + EGM) + Gap Inventory + Interpretation Package, siap untuk manuscript writing di Modul 9.

> **🤝 Workflow Modul Ini:** Lanjutan dari Modul 7 — gunakan **folder kerja yang sama**. Claude cowork akses `charting.xlsx`, generate visualisasi langsung (PNG/PDF), dan tulis output ke file `.md`.

> **📌 Prinsip ScR:** Sintesis bersifat **deskriptif + tematik + mapping** — TIDAK ADA meta-analysis, GRADE, atau effect-size pooling. Klaim **DESCRIPTIVE**, bukan kausal/inferensial.

---

## **LANGKAH 0: PERLUASAN FOLDER KERJA (LANJUTAN MODUL 7)**

### **0.1 Tambahan Struktur Folder:**

```
ScR_Project/                       ← folder yang sama dari Modul 6-7
├── pdfs/                          ← (dari M6)
├── screening.xlsx                  ← (dari M6)
├── charting.xlsx                   ← (dari M7) — INPUT UTAMA Modul 8
├── charting_form.md                ← (dari M7)
├── mapping_prep.md                 ← (dari M7)
├── pcc_definitions.md              ← (dari M6)
├── outputs/                        ← BARU — folder hasil mapping + figures
│   ├── descriptive_summary.md
│   ├── thematic_mapping.md
│   ├── gap_inventory.md
│   ├── interpretation_package.md
│   └── figures/                    ← BARU — semua chart/figure (SVG + PNG)
│       ├── fig2_temporal.svg + .png
│       ├── fig3_egm.svg + .png   ← hero figure
│       ├── fig4_geographic.svg + .png
│       └── ...
```

> **📁 Catatan:** Jika nama folder kerja Anda bukan `ScR_Project/`, gunakan nama yang sama dari Modul 6-7.

### **0.2 Setup Tambahan via Cowork:**

```
Lanjut Modul 8 di folder kerja saya [nama folder].

CREATE struktur output:
1. CREATE folder outputs/ di dalam folder kerja
2. CREATE sub-folder outputs/figures/
3. VERIFY charting.xlsx tersedia (input utama Modul 8)
4. Konfirmasi total INCLUDED sources di charting.xlsx

No preamble.
```

### **0.3 Brief Awal Modul 8:**

```
Lanjut Modul 8 (Mapping + EGM) di folder [nama folder Anda].

Konteks:
- Input: charting.xlsx (lengkap dengan QA jika ada)
- Output: outputs/ folder (semua .md + figures/)
- Standar: JBI Manual Ch.11 + PRISMA-ScR
- Sintesis: descriptive + thematic + EGM (TIDAK ADA meta-analysis)
- Bahasa klaim: DESCRIPTIVE saja ("mapped", "identified", "reported")
- TIDAK ADA: "effective", "significant", "causes", "proves"

Output kamu: tabel/bullet ringkas, no preamble, no narasi panjang.
Bahasa Indonesia.
```

---

## **LANGKAH 1: DESCRIPTIVE NUMERICAL SUMMARY + VISUALISASI**

### **Prompt Cowork:**

```
Generate descriptive summary dari charting.xlsx + visualisasi.

1. ANALISIS DESCRIPTIVE (output ke outputs/descriptive_summary.md):

   - Source distribution: peer (N, %) vs grey (N, %)
   - Document type breakdown
   - Temporal distribution: min/max/median tahun + trend (growing/declining/stable)
   - Geographic distribution: top regions + % per region
   - Study design / Doc type breakdown
   - Sample size statistics (jika applicable)
   - PCC component distribution (P, Concept, Context kategori + frekuensi)
   - QA distribution (jika ada di charting.xlsx)

2. VISUALISASI (generate dan simpan ke outputs/figures/):

   Setiap figure WAJIB di-export dalam DUA format:
   - **SVG** (vector — scalable, untuk submission jurnal & embed di GitBook)
   - **PNG** (raster DPI 300 — untuk slide presentasi & preview cepat)

   File yang di-generate:
   - fig2_temporal.svg + fig2_temporal.png — line chart distribusi tahun
     (peer vs grey overlay)
   - fig3_geographic.svg + fig3_geographic.png — bar chart top 10 negara/region
   - fig4_doctype.svg + fig4_doctype.png — pie chart document type
   - fig5_pcc.svg + fig5_pcc.png — stacked bar PCC components
   - (fig1 = PRISMA-ScR flow diagram dari Modul 6, sudah ada)

   Generate via Python (matplotlib/seaborn). Aspect 16:9 untuk slide-friendly.

   Contoh kode export dual-format (Python matplotlib):
       plt.savefig('outputs/figures/fig2_temporal.svg', bbox_inches='tight')
       plt.savefig('outputs/figures/fig2_temporal.png', dpi=300, bbox_inches='tight')

3. GEOGRAPHIC HONESTY CHECK:
   Jika ada region dominan (>50%), generate disclosure paragraph:
   "Mapping ini didominasi sources dari [region] ([X]%). Implikasi
   generalisasi terbatas pada konteks tsb."

Output ringkas: ringkasan numerik + path semua figure yang di-generate.
No preamble.
```

> **💡 Catatan Visualisasi:** Cowork bisa generate via Python script atau langsung render. **Selalu export dual-format (SVG + PNG)** — SVG untuk submission jurnal/GitBook (vector, tidak pecah), PNG untuk slide/preview. Jika cowork tidak bisa render visual langsung, output script `.py` ke `outputs/figures/generate_figures.py` dengan dual-export untuk peserta jalankan sendiri.

---

## **LANGKAH 2: THEMATIC MAPPING + CROSS-TABULATION**

### **2.1 Categorical Analysis per Kolom Kunci:**

```
Lakukan categorical analysis dari charting.xlsx untuk kolom kunci:
- Concept Operationalization
- Context Details
- Methodology approach
- Key findings (tematik)

Untuk setiap kolom:
1. Identifikasi kategori-kategori yang muncul
2. Hitung frekuensi per kategori
3. Jika kategori >15: lakukan second-level clustering ke 5-7 meta-kategori
4. Sajikan tabel: Kategori | Frekuensi | % | Contoh sources

Tulis ke outputs/thematic_mapping.md sebagai bagian "Categorical Analysis".

No preamble.
```

### **2.2 Thematic Synthesis per RQ:**

```
Untuk setiap RQ (primary + 3 secondary), tulis thematic synthesis 100-150 kata
berdasarkan categorical analysis.

Aturan bahasa ScR:
- "N sources reported [finding]"
- "Common theme was [...]"
- "Mapping indicates [...]"
- JANGAN: "evidence shows X causes Y", "significant effect"

Append ke outputs/thematic_mapping.md sebagai bagian "Thematic Synthesis per RQ".

No preamble.
```

### **2.3 Cross-Tabulation Matrix:**

```
Generate cross-tabulation Concept × Context dari charting.xlsx.

1. Matrix: rows = Concept categories, cols = Context categories
2. Cell value = jumlah sources
3. Identifikasi:
   - DENSE cells (n > median) — well-mapped areas
   - GAP cells (n = 0 atau < 3) — underexplored

4. Output:
   - Tabel matrix di outputs/thematic_mapping.md
   - Visualisasi heatmap dual-format:
     · outputs/figures/fig6_crosstab.svg
     · outputs/figures/fig6_crosstab.png (DPI 300)

No preamble.
```

---

## **LANGKAH 3: EVIDENCE GAP MAP (EGM) + GAP INVENTORY**

### **3.1 Evidence Gap Map — Hero Figure:**

```
Generate Evidence Gap Map (EGM) — ini akan jadi figure utama manuskrip.

Pilihan struktur (rekomendasikan default berdasarkan data saya):
- 2D heatmap (Concept × Context) — paling umum untuk ScR
- Bubble plot (size = N sources, color = quality jika QA dilakukan)
- Table-based dengan shading

REKOMENDASI default: heatmap 2D dengan optional 3rd dimension (color = quality).

Generate:
1. EGM hero figure dual-format di outputs/figures/ (aspect 4:3):
   - fig3_egm.svg (vector — untuk submission jurnal)
   - fig3_egm.png (DPI 300 — untuk slide/preview)
2. Deskripsi naratif EGM (200-250 kata) di outputs/thematic_mapping.md
   sebagai bagian "Evidence Gap Map"
3. Tag dense cells + gap cells eksplisit

No preamble.
```

### **3.2 Gap Inventory:**

```
Berdasarkan EGM + cross-tabulation + categorical analysis, generate Gap
Inventory komprehensif. Tulis ke outputs/gap_inventory.md.

Struktur:

1. GAP KUANTITATIF (PCC kombinasi sparse):
   - Gap 1: [Concept X] dalam [Context Y] — n=[N]
     Mengapa penting: [...]
     Future research opportunity: [...]
   - Gap 2: [...]

2. GAP KUALITATIF / KONSEPTUAL:
   - Konsep [X] didefinisikan dengan [N] cara berbeda
   - Tension antar definisi: [...]
   - Rekomendasi terminologi: [...]

3. GAP METODOLOGIS:
   - Desain [X] underused untuk [Concept Y]
   - Pendekatan analisis yang sparse

4. GAP TEMPORAL:
   - Periode [X] sparse meski [Concept Y] tetap relevan

PRIORITISASI: pilih 3-5 priority gaps berdasarkan kombinasi:
- Signifikansi teoritis
- Kebutuhan praktik
- Feasibility penelitian

Output ringkas + path file.
No preamble.
```

---

## **LANGKAH 4: INTERPRETATION PACKAGE (BRIDGE KE MODUL 9)**

### **Prompt Cowork:**

```
Generate interpretation package siap-Modul 9. Tulis ke
outputs/interpretation_package.md.

Struktur:

1. ANSWERS TO RESEARCH QUESTIONS (ScR style — descriptive):
   - Primary RQ: [50-100 kata jawaban grounded di mapping]
   - Secondary RQ 1-3: format serupa
   ATURAN: BUKAN claim kausal/effect. ScR DESCRIBES, tidak EVALUATES.

2. KEY FINDINGS (3-5 headline messages):
   - Finding 1: descriptive statement + N sources + implikasi mapping
   - Finding 2-5: format serupa
   CONTOH BENAR: "Literatur didominasi studi dari [region] (78%); hanya
                  6% dari Asia Tenggara"
   CONTOH SALAH: "Evidence menunjukkan X efektif untuk Y" (causal claim)

3. CONCEPTUAL CLARIFICATIONS (jika Tipe Gap B):
   - Variasi definisi yang ditemukan
   - Rekomendasi unifikasi atau plurality

4. SURPRISING / UNEXPECTED MAPPING PATTERNS:
   - Pattern surprising: [statement]
   - Penjelasan: [...]

5. GAP-DRIVEN FUTURE RESEARCH AGENDA:
   - 3 HIGH priority + 2 MEDIUM + 1 LONG-TERM
   - Setiap gap: research question (PCC-aligned) + suggested methodology

6. TRIPLE-TRACK IMPLICATIONS:
   - For Research: [...]
   - For Practice: [...]
   - For Policy: [...]

7. LIMITATIONS SELF-AUDIT (3-tier):
   - Review-level: database coverage, geographic bias, timeframe, grey lit
     coverage
   - Source-level: NR rate, heterogeneity, inaccessibility
   - Mapping-level: subjectivity in categorization, EGM granularity

   ScR-SPECIFIC DISCLAIMERS (wajib):
   - "ScR maps evidence, does not assess effectiveness"
   - "Quality reported descriptively, not used for exclusion"
   - "No meta-analysis (beyond ScR methodology)"

Output ringkas + path file.
No preamble.
```

---

## **HASIL AKHIR**

```
=== MAPPING + SYNTHESIS PACKAGE (ScR) ===

DESCRIPTIVE SUMMARY (outputs/descriptive_summary.md):
- Total sources: [N] (peer: X, grey: Y)
- Temporal: [trend]
- Geographic: [breakdown + bias disclosure jika ada]
- Document type / PCC components: [breakdown]
- QA distribution: [jika ada]

THEMATIC MAPPING (outputs/thematic_mapping.md):
- Categorical analysis per kolom kunci
- Thematic synthesis per RQ (primary + 3 secondary)
- Cross-tabulation Concept × Context

EVIDENCE GAP MAP:
- Hero figure: outputs/figures/fig3_egm.png
- Naratif description: di thematic_mapping.md

GAP INVENTORY (outputs/gap_inventory.md):
- Kuantitatif / Kualitatif / Metodologis / Temporal
- 3-5 priority gaps untuk Future Research Agenda

INTERPRETATION PACKAGE (outputs/interpretation_package.md):
- Answers to RQs (descriptive)
- 3-5 key findings (mapping-grounded, not causal)
- Conceptual clarifications
- Surprising patterns
- Gap-driven future research (3 HIGH + 2 MEDIUM + 1 LONG-TERM)
- Triple-track implications (research/practice/policy)
- Limitations self-audit + ScR disclaimers

FIGURES (outputs/figures/) — semua dual-format SVG + PNG:
- fig1_prisma_scr_flow.svg + .png (dari Modul 6)
- fig2_temporal.svg + .png
- fig3_egm.svg + .png (HERO FIGURE)
- fig4_doctype.svg + .png
- fig5_pcc.svg + .png
- fig6_crosstab.svg + .png

Format guideline:
- SVG: untuk submission jurnal (scalable vector, tidak pecah saat di-resize)
  + embed di GitBook
- PNG: untuk slide presentasi, preview, manuscript draft (DPI 300)

NEXT: Manuscript Writing (Modul 9) — semua artifacts di outputs/
siap di-feed ke writing prompts.
```

---

## **TROUBLESHOOTING**

**1. Categorical analysis menghasilkan terlalu banyak kategori (>20)**
- Minta cowork: "second-level clustering ke 5-7 meta-categories"
- Laporkan both levels (detail + meta) di Results
- Sangat fragmented = temuan penting (gap konseptual)

**2. EGM terlihat "kosong" (banyak cell n=0)**
- NORMAL untuk ScR — gap visualization adalah tujuan
- Jangan paksa isi cell dengan source marjinal
- Laporkan sparse cells sebagai gap eksplisit

**3. Godaan claim kausal/effect — JANGAN**
- ScR DESCRIBES, bukan EVALUATES
- Self-audit: minta cowork "scan output untuk frasa effect/causal/significant"
- Trigger words yang HARUS diganti: "pooled", "significant effect", "causes",
  "leads to" → ganti dengan "described", "reported", "characterized", "mapped"

**4. Cowork tidak bisa generate visualisasi langsung**
- Minta output script Python (.py) atau R (.R) ke outputs/figures/
- Pastikan script include dual-export SVG + PNG.

Contoh Python (matplotlib):

```python
plt.savefig('fig.svg', bbox_inches='tight')
plt.savefig('fig.png', dpi=300, bbox_inches='tight')
```

Contoh R (ggplot2):

```r
ggsave('fig.svg', plot, width=10, height=6)
ggsave('fig.png', plot, width=10, height=6, dpi=300)
```

- Peserta jalankan sendiri
- Atau gunakan Excel chart (less professional — Excel tidak support SVG native)

**5. Reviewer/supervisor minta meta-analysis atau pooled estimate**
- Tegaskan: ini ScR, bukan SLR
- Rujuk JBI Manual Ch.11 + Munn et al. (2018) + PRISMA-ScR item 13
- Jika subset homogen dapat di-meta: pertimbangkan **mini-SLR follow-up**
  sebagai output terpisah, BUKAN gabung ke ScR ini
