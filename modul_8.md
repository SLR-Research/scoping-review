# Modul 8: Mapping, Synthesis, dan Evidence Gap Map (Claude Cowork)

> **🎯 Output Modul Ini:** Mapping lengkap (descriptive + thematic + EGM) + Gap Inventory + Interpretation Package, siap untuk manuscript writing di Modul 9.

> **🤝 Workflow Modul Ini:** Lanjutan dari Modul 7 — gunakan **folder kerja yang sama**. Claude cowork akses `charting.xlsx`, generate visualisasi langsung (PNG/PDF), dan tulis output ke file `.md`.

> **📌 Prinsip ScR:** Sintesis bersifat **deskriptif + tematik + mapping** — TIDAK ADA meta-analysis, GRADE, atau effect-size pooling. Klaim **DESCRIPTIVE**, bukan kausal/inferensial.

---

## **LANGKAH 0: PERLUASAN FOLDER KERJA (LANJUTAN MODUL 7)**

> **📁 Catatan:** Jika nama folder kerja Anda bukan `ScR_Project/`, gunakan nama yang sama dari Modul 6-7.

### **Prompt Cowork (single prompt — setup outputs/ + brief context):**

```
Lanjut Modul 8 (Mapping + EGM) di folder kerja saya [nama folder dari M7].
Eksekusi dua hal sekaligus:

=== BAGIAN A: SETUP STRUKTUR OUTPUT ===

Target struktur akhir:

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
│   └── figures/                    ← BARU — chart/figure (SVG + PNG)
│       ├── fig2_temporal.svg + .png
│       ├── fig3_egm.svg + .png   ← hero figure
│       ├── fig4_geographic.svg + .png
│       └── ...

Steps:
1. CREATE folder outputs/ di dalam folder kerja
2. CREATE sub-folder outputs/figures/
3. VERIFY charting.xlsx tersedia (input utama Modul 8)
4. Konfirmasi total INCLUDED sources di charting.xlsx

=== BAGIAN B: BRIEF AWAL CONTEXT ===

Setelah setup, simpan context untuk seluruh sesi Modul 8:

- Input: charting.xlsx (lengkap dengan QA jika ada)
- Output: outputs/ folder (semua .md + figures/)
- Standar: JBI Manual Ch.11 + PRISMA-ScR
- Sintesis: descriptive + thematic + EGM (TIDAK ADA meta-analysis)
- Bahasa klaim: DESCRIPTIVE saja ("mapped", "identified", "reported")
- TIDAK ADA: "effective", "significant", "causes", "proves"
- Output format default: tabel/bullet ringkas, no preamble
- Bahasa: Indonesia

Konfirmasi: setup folder + context siap untuk eksekusi L1-L4.
No preamble.
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

### **Prompt Cowork (single prompt — 3 fase otomatis):**

```
Generate thematic mapping lengkap dari charting.xlsx. Tulis semua ke
outputs/thematic_mapping.md (sequential append per fase).

=== FASE 1: CATEGORICAL ANALYSIS PER KOLOM KUNCI ===
Untuk kolom: Concept Operationalization, Context Details, Methodology, Key Findings.
Untuk setiap kolom:
- Identifikasi kategori yang muncul
- Hitung frekuensi per kategori
- Jika kategori >15: second-level clustering ke 5-7 meta-kategori
- Sajikan tabel: Kategori | Frekuensi | % | Contoh sources

=== FASE 2: THEMATIC SYNTHESIS PER RQ ===
Untuk setiap RQ (primary + 3 secondary), tulis synthesis 100-150 kata
berdasarkan categorical analysis Fase 1.

Aturan bahasa ScR (WAJIB):
- "N sources reported [finding]"
- "Common theme was [...]"
- "Mapping indicates [...]"
- JANGAN: "evidence shows X causes Y", "significant effect"

=== FASE 3: CROSS-TABULATION MATRIX ===
- Matrix Concept × Context (rows × cols), cell value = N sources
- Identifikasi DENSE cells (n > median) + GAP cells (n=0 atau <3)
- Tabel matrix di thematic_mapping.md
- Visualisasi heatmap dual-format ke outputs/figures/:
  · fig6_crosstab.svg (vector)
  · fig6_crosstab.png (DPI 300)

OUTPUT FINAL: konfirmasi semua 3 fase tertulis + path file + ringkasan
top-3 dense cells + top-3 gap cells.
No preamble.
```

> **💡 Manfaat single prompt:** Cowork eksekusi categorical → thematic → cross-tab berurutan dalam satu sesi. Tidak ada break antar fase, hemat token.

---

## **LANGKAH 3: EVIDENCE GAP MAP (EGM) + GAP INVENTORY**

### **Prompt Cowork (single prompt — EGM + Gap Inventory bersamaan):**

```
Berdasarkan thematic_mapping.md (cross-tabulation) dari L2, generate dua
output bersamaan:

=== OUTPUT 1: EVIDENCE GAP MAP (HERO FIGURE) ===

Pilihan struktur (rekomendasikan default berdasarkan data):
- 2D heatmap (Concept × Context) — paling umum untuk ScR
- Bubble plot (size = N sources, color = quality jika QA ada)
- Table-based dengan shading

DEFAULT: heatmap 2D dengan optional 3rd dim (color = quality).

Generate:
1. EGM hero figure dual-format di outputs/figures/ (aspect 4:3):
   - fig3_egm.svg (vector — submission jurnal)
   - fig3_egm.png (DPI 300 — slide/preview)
2. Naratif EGM (200-250 kata) — append ke outputs/thematic_mapping.md
   sebagai section "Evidence Gap Map"
3. Tag dense cells + gap cells eksplisit di naratif

=== OUTPUT 2: GAP INVENTORY ===

Tulis ke outputs/gap_inventory.md dengan struktur:

1. GAP KUANTITATIF (PCC kombinasi sparse):
   - Gap 1: [Concept X] dalam [Context Y] — n=[N]
     Mengapa penting: [...]
     Future research opportunity: [...]
   - Gap 2: [...]

2. GAP KUALITATIF / KONSEPTUAL:
   - Konsep [X] didefinisikan dengan [N] cara berbeda
   - Tension antar definisi + rekomendasi terminologi

3. GAP METODOLOGIS:
   - Desain [X] underused untuk [Concept Y]
   - Pendekatan analisis sparse

4. GAP TEMPORAL:
   - Periode [X] sparse meski [Concept Y] tetap relevan

PRIORITISASI: pilih 3-5 priority gaps berdasarkan signifikansi teoritis +
kebutuhan praktik + feasibility penelitian.

OUTPUT FINAL: konfirmasi 2 file tersimpan + path absolut + ringkasan
3-5 priority gaps yang dipilih.
No preamble.
```

---

## **LANGKAH 4: INTERPRETATION PACKAGE + FINAL SUMMARY (BRIDGE KE MODUL 9)**

### **Prompt Cowork (single prompt — generate 2 file output):**

```
Generate dua file output dari semua artifact L1-L3 (descriptive_summary.md,
thematic_mapping.md, gap_inventory.md, charting.xlsx, figures/).

=== OUTPUT 1: outputs/interpretation_package.md (UNTUK MODUL 9) ===

Struktur 7 komponen:

1. ANSWERS TO RESEARCH QUESTIONS (ScR style — DESCRIPTIVE only):
   - Primary RQ: [50-100 kata, grounded di mapping]
   - Secondary RQ 1-3: format serupa
   ATURAN: BUKAN claim kausal/effect. ScR DESCRIBES, tidak EVALUATES.

2. KEY FINDINGS (3-5 headline messages):
   - Format: descriptive statement + N sources + implikasi mapping
   ✓ BENAR: "Literatur didominasi studi dari [region] (78%); 6% dari Asia Tenggara"
   ✗ SALAH: "Evidence menunjukkan X efektif untuk Y" (causal claim)

3. CONCEPTUAL CLARIFICATIONS (jika Tipe Gap B):
   - Variasi definisi + rekomendasi unifikasi atau plurality

4. SURPRISING / UNEXPECTED MAPPING PATTERNS:
   - Pattern + penjelasan

5. GAP-DRIVEN FUTURE RESEARCH AGENDA:
   - 3 HIGH + 2 MEDIUM + 1 LONG-TERM
   - Setiap gap: RQ (PCC-aligned) + suggested methodology

6. TRIPLE-TRACK IMPLICATIONS:
   - For Research / Practice / Policy

7. LIMITATIONS SELF-AUDIT (3-tier):
   - Review-level (database, geographic bias, timeframe, grey lit coverage)
   - Source-level (NR rate, heterogeneity, inaccessibility)
   - Mapping-level (subjectivity, EGM granularity)
   ScR-SPECIFIC DISCLAIMERS (wajib disertakan):
   - "ScR maps evidence, does not assess effectiveness"
   - "Quality reported descriptively, not used for exclusion"
   - "No meta-analysis (beyond ScR methodology)"

=== OUTPUT 2: outputs/modul8_summary.md (HASIL AKHIR MODUL 8) ===

Format ringkas:

=== MAPPING + SYNTHESIS PACKAGE (ScR) ===

L1 DESCRIPTIVE SUMMARY:
- Total sources: [N] (peer: X, grey: Y) | Temporal trend | Geographic breakdown
- QA distribution (jika ada)

L2 THEMATIC MAPPING (outputs/thematic_mapping.md):
- Categorical analysis per kolom kunci [ringkas top-3]
- Thematic synthesis per RQ
- Cross-tabulation Concept × Context [top dense + gap cells]

L3 EVIDENCE GAP MAP:
- Hero figure: outputs/figures/fig3_egm.svg + .png
- Gap Inventory (outputs/gap_inventory.md): 4 jenis gap + 3-5 priority

L4 INTERPRETATION PACKAGE (outputs/interpretation_package.md):
- Answers to RQs (descriptive)
- 3-5 key findings (mapping-grounded, NOT causal)
- Conceptual clarifications, surprising patterns
- Future Research Agenda (3 HIGH + 2 MEDIUM + 1 LONG-TERM)
- Triple-track implications, Limitations + ScR disclaimers

FIGURES (outputs/figures/) — semua dual-format SVG + PNG:
- fig1_prisma_scr_flow (dari M6) | fig2_temporal | fig3_egm (HERO)
- fig4_doctype | fig5_pcc | fig6_crosstab

Format guideline:
- SVG: submission jurnal + embed GitBook (vector)
- PNG: slide/preview/draft (DPI 300)

NEXT: Manuscript Writing (Modul 9) — semua artifacts di outputs/ siap-feed.

=== KONFIRMASI ===
Konfirmasi 2 file tersimpan + path absolut.
No preamble.
```

> **💡 Manfaat single prompt:** L4 sekaligus menghasilkan input utama Modul 9 (interpretation_package.md) dan checkpoint summary (modul8_summary.md). Tidak butuh section "HASIL AKHIR" terpisah — file `modul8_summary.md` sudah menggantikannya.

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
