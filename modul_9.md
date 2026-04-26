# Modul 9: Manuscript Writing PRISMA-ScR Compliant (Claude Cowork)

> **🎯 Output Modul Ini:** Manuskrip ScR lengkap PRISMA-ScR-compliant dalam dua format: `manuscript_final.md` (master) + `manuscript_final.docx` (siap submit ke jurnal).

> **🤝 Workflow Modul Ini:** Lanjutan dari Modul 8 — gunakan **folder kerja yang sama**. Claude cowork akses semua file output dari Modul 2-8, generate setiap section sebagai file `.md` terpisah, lalu compile final jadi `.docx`.

> **📌 Urutan penulisan (reverse-writing):** Methods → Results → Discussion → Future Research → Introduction → Conclusions → References → Abstract → Title → Audit + Compile.

> **📋 Standar:** PRISMA-ScR checklist 22-item (Tricco et al., 2018) + JBI Manual Ch.11 (Peters et al., 2020). BUKAN PRISMA 2020 yang 27-item.

---

## **LANGKAH 0: SETUP + ATURAN GLOBAL**

> **📁 Catatan:** Jika nama folder kerja Anda bukan `ScR_Project/`, gunakan nama yang sama dari Modul 6-8.

### **Prompt Cowork (single prompt — setup + brief + aturan global):**

```
Lanjut Modul 9 (Manuscript Writing) di folder kerja [nama folder dari M8].
Eksekusi tiga hal sekaligus:

=== BAGIAN A: SETUP STRUKTUR OUTPUT ===

Target struktur akhir:

ScR_Project/                       ← folder yang sama dari Modul 6-8
├── pdfs/                           ← (dari M6)
├── screening.xlsx                  ← (dari M6)
├── charting.xlsx                   ← (dari M7)
├── pcc_definitions.md              ← (dari M6)
├── outputs/
│   ├── descriptive_summary.md      ← (dari M8)
│   ├── thematic_mapping.md         ← (dari M8)
│   ├── gap_inventory.md            ← (dari M8)
│   ├── interpretation_package.md   ← (dari M8) — INPUT UTAMA M9
│   ├── figures/                    ← (dari M8) — SVG + PNG
│   ├── manuscript/                 ← BARU — section .md per langkah
│   │   ├── methods.md
│   │   ├── results.md
│   │   ├── discussion.md
│   │   ├── future_research.md
│   │   ├── introduction.md
│   │   ├── conclusions.md
│   │   ├── references.md
│   │   ├── abstract.md
│   │   └── title.md
│   ├── manuscript_final.md         ← BARU — master compile
│   ├── manuscript_final.docx       ← BARU — siap submit
│   └── prisma_scr_checklist.md     ← BARU — supplementary

Steps:
1. CREATE outputs/manuscript/ (kosong, diisi per langkah L1-L9)
2. VERIFY input artifacts dari M2-8 tersedia:
   - outputs/interpretation_package.md (dari M8 — wajib)
   - outputs/gap_inventory.md, outputs/thematic_mapping.md,
     outputs/descriptive_summary.md
   - outputs/figures/ (semua SVG + PNG)
   - charting.xlsx, screening.xlsx (untuk PRISMA-ScR flow numbers)

=== BAGIAN B: BRIEF AWAL CONTEXT ===

INPUT UTAMA: outputs/interpretation_package.md (dari M8) + semua file di
outputs/ dan outputs/figures/

OUTPUT TARGET:
- Per langkah L1-L9: file .md terpisah di outputs/manuscript/
- Final (L10): outputs/manuscript_final.md + manuscript_final.docx +
               prisma_scr_checklist.md + coherence_audit.md +
               modul9_summary.md

=== BAGIAN C: ATURAN GLOBAL (BERLAKU UNTUK L1-L10) ===

A. STANDAR: PRISMA-ScR 22-item + JBI Manual Ch.11
   (BUKAN PRISMA 2020 27-item — beda standar)

B. BAHASA ScR — DESCRIPTIVE ONLY:
   ✓ "we mapped", "identified", "characterized", "sources reported",
     "common theme was", "evidence describes", "mapping indicates"
   ✗ "studies showed effect", "X causes Y", "significantly", "effective",
     "pooled effect", "meta-analysis demonstrates"

C. TERMINOLOGI WAJIB:
   - "Scoping review" (BUKAN systematic review/literature review)
   - "Charting" (BUKAN extraction)
   - "Mapping" (BUKAN synthesis/meta-analysis)
   - "PCC" (BUKAN PICO)
   - Canonical terminology dari pcc_definitions.md (konsisten end-to-end)

D. GEOGRAPHIC HONESTY:
   - Jangan klaim "global" jika dominasi regional
   - Disclose bias geografis di Discussion DI AWAL

E. ANTI-OVERCLAIMING:
   - Hedging tepat sesuai kekuatan bukti
   - Tidak mengklaim effectiveness/causality (di luar metodologi ScR)

F. OUTPUT FORMAT:
   - Tulis langsung ke file .md di outputs/manuscript/
   - No preamble, no narasi panjang di chat
   - Paragraf akademik standar (bukan bullet list panjang)

G. FOUNDATIONAL REFERENCES (wajib di-cite di Methods + Intro):
   - Arksey & O'Malley (2005)
   - Levac et al. (2010)
   - Peters et al. (2020) JBI Manual Ch.11
   - Tricco et al. (2018) PRISMA-ScR
   - Munn et al. (2018)

VERIFY: setup folder selesai + semua input artifact terkonfirmasi + aturan
global di-pegang. Selanjutnya saya akan request langkah demi langkah (L1-L10).
No preamble.
```

> **💡 Manfaat single prompt:** Setup folder + brief context + aturan global ditetapkan **sekali** dalam 1 sesi. Langkah L1-L10 berikutnya cukup pointer "ikuti aturan global". Hemat token + konsistensi otomatis.

---

## **LANGKAH 1: METHODS WRITING**

```
Tulis Methods section PRISMA-ScR-compliant ke outputs/manuscript/methods.md.

Konsolidasi keputusan metodologis dari semua artifacts (baca file langsung):
- screening.xlsx (PRISMA-ScR flow numbers, kappa)
- charting.xlsx (charting framework + QA jika ada)
- pcc_definitions.md (PCC + scope)
- outputs/descriptive_summary.md (untuk source breakdown)

Struktur 22-item PRISMA-ScR (yang applicable untuk Methods, items 5-13):

1. Protocol and Registration (item 5) — OSF URL/DOI, catat PROSPERO tidak
   menerima ScR
2. Eligibility Criteria (item 6) — PCC + reason codes
3. Information Sources (item 7) — peer-reviewed DBs + grey lit (jika ada)
4. Search (item 8) — Boolean strings + filter + tanggal + update policy
5. Selection of Sources (item 9) — dual-reviewer + AI-assist + kappa
6. Data Charting Process (item 10) — CHARTING (bukan extraction) +
   iterative refinement (Levac)
7. Data Items (item 11) — kolom charting form
8. Critical Appraisal (item 12, OPSIONAL) — jika dilakukan: tool +
   non-exclusionary; jika tidak: justifikasi merujuk JBI
9. Synthesis of Results (item 13) — descriptive + thematic + EGM, eksplisit
   "no meta-analysis"

Length target: 1200-1800 kata.
Ikuti aturan global L0.3.
No preamble.
```

---

## **LANGKAH 2: RESULTS WRITING**

```
Tulis Results section ke outputs/manuscript/results.md.

Input: charting.xlsx + outputs/descriptive_summary.md + outputs/thematic_mapping.md
       + outputs/figures/ (semua SVG + PNG)

Struktur PRISMA-ScR items 14-18:

2.1. Selection of Sources (item 14) — narasi PRISMA-ScR flow + Figure 1
     (fig1_prisma_scr_flow)
2.2. Characteristics of Sources (item 15) — distribusi tahun/geografis/tipe
     dokumen + Table 1
2.3. Critical Appraisal Results (item 16) — jika QA dilakukan, deskriptif saja
2.4. Results of Individual Sources (item 17) — summary table di Supplementary
     atau narasi kelompok
2.5. Synthesis of Results (item 18) — thematic mapping per RQ:
     - Concept Operationalization (inti ScR)
     - Context Mapping
     - Methodological Characteristics
     - Key Findings (aggregated thematic)
2.6. Evidence Gap Map — Figure 3 (fig3_egm) HERO + naratif EGM
2.7. Identification of Gaps — dari outputs/gap_inventory.md (ringkas, BUKAN
     interpretasi — interpretasi ke Discussion)

FIGURES + TABLES (referensi dengan filename, format SVG untuk submission):
- Figure 1: fig1_prisma_scr_flow.svg
- Figure 2: fig2_temporal.svg
- Figure 3: fig3_egm.svg (HERO)
- Figure 4: fig4_geographic.svg (atau doctype tergantung mapping approach)
- Figure 5: fig5_pcc.svg
- Figure 6: fig6_crosstab.svg
- Table 1: Characteristics of Included Sources
- Table 2: Thematic Categories of [Concept]

Length target: 2500-3500 kata.
Ikuti aturan global L0.3 (terutama bahasa descriptive + non-interpretation).
No preamble.
```

---

## **LANGKAH 3: DISCUSSION WRITING**

```
Tulis Discussion section ke outputs/manuscript/discussion.md.

Input: outputs/interpretation_package.md (utama) + outputs/manuscript/results.md
       + Modul 2 prior reviews matrix (paste atau dari file)

Struktur 6 subseksi WAJIB (PRISMA-ScR aligned):

3.1. Summary of Evidence (item 19) — 2-3 paragraf, jawab RQ + interpretasi
     high-level (BUKAN repetisi Results)

3.2. Geographic and Contextual Honesty — 1-2 paragraf, DI AWAL Discussion
     - Acknowledge bias regional jika ada
     - Reframe claim sesuai konteks ("Indonesian context" bukan "global")

3.3. Conceptual Landscape + Dialog with Literature — 2-3 paragraf
     - Konsep yang ditemukan terkonsep dengan beragam cara
     - Dialog dengan prior reviews
     - Jika Tipe Gap B: rekomendasi unifikasi/plurality terminologi

3.4. Nature and Extent of Evidence — 1-2 paragraf
     - Karakterisasi evidence (BUKAN effect size)
     - Skewness, dominance empirical vs konseptual, peran grey lit

3.5. Evidence Gaps + Triple-Track Implications — 3-4 paragraf (INTI ScR)
     - 3.5.1 Gaps Identified (ringkas dari gap_inventory.md)
     - 3.5.2 Implications for Research
     - 3.5.3 Implications for Practice
     - 3.5.4 Implications for Policy

3.6. Limitations (item 20) — 3-tier dengan mitigasi:
     - Review-level (database, geographic, language, timeframe, grey lit)
     - Source-level (NR rate, heterogeneity, inaccessibility)
     - Mapping-level (subjectivity, EGM granularity)
     - WAJIB ScR-disclaimers:
       · "Maps evidence, does not assess effectiveness"
       · "Quality reported descriptively, not exclusionary"
       · "No meta-analysis (beyond ScR methodology)"

Length target: 2500-3500 kata.
Ikuti aturan global L0.3 (terutama anti-causal claims + non-repetisi Results).
No preamble.
```

---

## **LANGKAH 4: FUTURE RESEARCH AGENDA**

```
Tulis Future Research Agenda sebagai subseksi tersendiri ke
outputs/manuscript/future_research.md.

Input: outputs/gap_inventory.md (utama) + outputs/interpretation_package.md
       (priority gaps)

Struktur:

4.1. Pendahuluan Agenda (1 paragraf) — justify mengapa agenda kritis,
     turunan dari mapping findings

4.2. Matriks Prioritas (tabel):

| Priority | Timeframe | Rationale (linked to gap) | Research Question | Suggested Methodology |
|----------|-----------|---------------------------|-------------------|----------------------|
| HIGH | 1-2 yr | [gap konkret] | [RQ PCC-aligned] | [survey/qualitative/SLR] |
| MEDIUM | 2-3 yr | [...] | [...] | [...] |
| LONG-TERM | 3+ yr | [...] | [...] | [...] |

Aturan:
- Setiap agenda HARUS trace ke gap konkret di gap_inventory.md
- Formulasikan sebagai RESEARCH QUESTION spesifik (BUKAN topik umum)
  ❌ "Future research on AI in education"
  ✓ "How do Indonesian non-metropolitan faculty integrate generative AI...?"
- Minimum: 3 HIGH + 2-3 MEDIUM + 1-2 LONG-TERM
- Suggested methodology eksplisit

4.3. Prioritization Rationale (2-3 paragraf) — mengapa HIGH addressable
     sekarang, mengapa LONG-TERM tidak

4.4. Methodological Advancements Needed (1-2 paragraf) — gap metodologis
     dari mapping

4.5. ScR → SLR Pathway (jika Tipe Gap D) — ScR sebagai prekursor SLR

Length target: 1000-1500 kata.
Ikuti aturan global L0.3. No "more research needed" — selalu spesifik.
No preamble.
```

---

## **LANGKAH 5: INTRODUCTION WRITING**

```
Tulis Introduction ke outputs/manuscript/introduction.md.

Input: pcc_definitions.md + outputs/manuscript/results.md (untuk preview) +
       Modul 2 prior reviews matrix

Struktur 5 subseksi WAJIB:

5.1. Background (2-3 paragraf) — field overview + importance + contextual
     relevance (SDGs, policy, technological shifts)

5.2. Review of Prior Reviews (SUBSEKSI TERSENDIRI — KRITIS untuk ScR)
     - 3-5 prior reviews terdekat (prioritas: ScR, evidence gap map, SLR
       relevan)
     - Per review: scope, methodology, key findings, limitations
     - Paragraf "Sintesis Novelty": apa yang SUDAH dipetakan, apa yang
       BELUM, mengapa ScR ini menutup gap
     - Length: 400-600 kata

5.3. Problem Statement + Justifikasi ScR (1-2 paragraf)
     Pakai template sesuai tipe gap (A/B/C/D). Rujuk Munn et al. (2018):

     - TIPE A: "Literature on [topic] remains fragmented... A scoping
       review is needed to map the extent, range, and nature of evidence
       (Munn et al., 2018)."
     - TIPE B: "[Concept] has been operationalized in diverse ways... A
       scoping review is appropriate to identify and compare definitions."
     - TIPE C: "No prior review has systematically examined how research
       on [topic] has been conducted... A scoping review can characterize
       this methodological landscape."
     - TIPE D: "Evidence heterogeneity precludes immediate systematic
       review. A scoping review is a necessary precursor..."

5.4. Scope Justification (1-2 paragraf) — justify setiap batasan dari
     pcc_definitions.md (3-lapis: teoretis + metodologis + praktis)

5.5. Research Questions + Objectives (1 paragraf) — primary RQ + 3
     secondary (ScR-style "what/how/which") + brief preview framework
     charting + mapping approach
     EKSPLISIT: "This is a scoping review conducted following JBI
     methodology and reported according to PRISMA-ScR guidelines."

Length target: 1200-1800 kata.
Ikuti aturan global L0.3.
JANGAN repetisi Discussion/Conclusion (akan diaudit di L10).
No preamble.
```

---

## **LANGKAH 6: CONCLUSIONS WRITING (LEAN)**

```
Tulis Conclusions ke outputs/manuscript/conclusions.md.

Input: outputs/interpretation_package.md (key findings) +
       outputs/manuscript/discussion.md (untuk avoid repetisi)

Struktur 3-4 paragraf (LEAN):

Paragraf 1 — Main Mapping Findings: jawab primary RQ + key mapping
            evidence + EGM contribution (BUKAN repetisi Results)

Paragraf 2 — Conceptual/Methodological Contributions: apa yang mapping
            tambahkan ke pemahaman lanskap bukti

Paragraf 3 — Overarching Implications: ringkas triple-track (jangan
            detail — sudah di Discussion)

Paragraf 4 (OPTIONAL) — Brief Forward Look: 1-2 kalimat arahkan ke
            Future Research Agenda

Length target: 500-700 kata.
Ikuti aturan global L0.3 (terutama anti-causal + tidak overclaim).
No preamble.
```

---

## **LANGKAH 7: REFERENCES**

> **⚠️ PERINGATAN:** Tahap paling rawan hallucination Claude. JANGAN minta Claude generate referensi dari nol. Hanya format, verify, audit.

```
Audit + format references ke outputs/manuscript/references.md.

Input: scan semua file di outputs/manuscript/ untuk in-text citations.

Target style: [APA 7th / Vancouver / Harvard — sesuai jurnal target]

7.1. EXTRACT in-text citations dari semua manuscript section files,
     kompilasi ke daftar referensi unik

7.2. FORMAT semua entries sesuai style:
     - Peer-reviewed: Author, Year, Title, Journal, Vol(Issue), Pages, DOI
     - Grey lit: Author/Org, Year, Title, URL, Retrieved date

7.3. WEB VERIFICATION (gunakan web search):
     - Peer-reviewed: cek Google Scholar/CrossRef
     - Grey lit: cek URL aktif, fallback Wayback Machine
     - Status per entry: ✅ VERIFIED / ⚠️ PARTIAL / ❌ NOT FOUND

7.4. TEMPORAL AUDIT vs search date dari Modul 3:
     - Hapus referensi yang publish setelah search date jika di-cite sebagai
       "sumber yang dipetakan"
     - OK jika sebagai "context citation" (Intro/Discussion)

7.5. FOUNDATIONAL WORKS CHECK (wajib di-cite untuk ScR):
     - Arksey & O'Malley (2005)
     - Levac et al. (2010)
     - Peters et al. (2020) JBI Manual Ch.11
     - Tricco et al. (2018) PRISMA-ScR
     - Munn et al. (2018)
     Jika absent: WAJIB tambahkan.

7.6. ORPHAN CHECK: in-text citations tanpa entry → flag untuk peserta
     resolve.

Output: references.md (formatted) + verification table + orphan list.
No preamble.
```

---

## **LANGKAH 8: ABSTRACT WRITING**

```
Tulis structured abstract ke outputs/manuscript/abstract.md.
Target: 250-300 kata, PRISMA-ScR item 2.

Input: outputs/manuscript/methods.md + results.md + conclusions.md +
       interpretation_package.md (top-3 future research priorities)

Struktur 4 bagian:

Background & Objective (2-3 kalimat) — problem + objective + tipe gap +
    eksplisit "scoping review"

Methods (3-4 kalimat) — WAJIB cantum:
    "scoping review following JBI methodology and PRISMA-ScR guidelines"
    + databases + grey lit (jika ada) + date + PCC + charting framework +
    mapping approach + final N (peer/grey breakdown)

Results (4-5 kalimat) — N sources + key mapping findings (descriptive) +
    geographic coverage JUJUR + key gaps + EGM mention

Conclusions (2-3 kalimat) — main mapping conclusions (descriptive) +
    overarching gap insights + top-3 future research priorities

CHECKLIST WAJIB di abstract:
[ ] "scoping review" eksplisit
[ ] PCC framework
[ ] JBI + PRISMA-ScR adherence
[ ] N sources (peer/grey breakdown)
[ ] Geographic coverage jujur
[ ] Key gaps + top-3 priorities

Ikuti aturan global L0.3 (terutama anti-overclaiming + descriptive).
No preamble.
```

---

## **LANGKAH 9: TITLE CREATION**

```
Generate 3-5 alternatif title ke outputs/manuscript/title.md.

Input: outputs/manuscript/abstract.md + key findings + geographic coverage

Title criteria:
1. DESCRIPTIVE — jelas tentang topik + approach
2. SPECIFIC — include key components
3. METHODOLOGY EKSPLISIT — WAJIB cantumkan "scoping review" (PRISMA-ScR
   item 1)
4. CONCISE — 12-18 kata
5. SEARCHABLE — keywords untuk discoverability
6. GEOGRAPHIC HONESTY — jangan klaim "global" jika regional

Format alternatif:
- "[Topic]: A Scoping Review"
- "Mapping [Concept] in [Context]: A Scoping Review"
- "[Region-qualified topic]: A Scoping Review"

Output untuk tiap alternatif: title + word count + keywords + checklist
PASS/FAIL ("scoping review" + geographic honesty + anti-causal) + rationale
2-3 kalimat.

Di akhir: REKOMENDASI title terbaik + justifikasi.
Ikuti aturan global L0.3.
No preamble.
```

---

## **LANGKAH 10: AUDIT + COMPILE FINAL + HASIL AKHIR**

### **Prompt Cowork (single prompt — 5 fase otomatis, multi-file output):**

```
Eksekusi audit + compile final manuskrip end-to-end. Generate semua file
deliverable dalam satu sesi.

=== FASE 1: COHERENCE AUDIT ===
Tulis ke outputs/coherence_audit.md (daftar issue + saran replacement):

A. AUDIT REPETISI (Intro ↔ Discussion ↔ Conclusion):
   - Kalimat/frasa nyaris identik di ≥2 bagian + saran rewrite

B. AUDIT TERMINOLOGI (canonical dari pcc_definitions.md):
   - Konsistensi term kanonikal end-to-end
   - Cek ScR-style: "scoping review", "charting", "mapping", "PCC", "sources"
   - Cek tidak ada SLR-style: "systematic review", "extraction", "PICO",
     "meta-analysis"

C. AUDIT BAHASA DESCRIPTIVE (anti-causal):
   - Scan trigger words: "effective", "significant", "causes", "proves",
     "pooled", "leads to"
   - Replacement: "described", "reported", "characterized", "mapped"

=== FASE 2: PRISMA-ScR 22-ITEM COMPLIANCE ===
Tulis ke outputs/prisma_scr_checklist.md (supplementary material).

Format tabel: | # | Item | Section/Paragraf | Status (✓/⚠/✗) |

- Item 1 (Title) → title.md
- Item 2 (Abstract) → abstract.md
- Item 3-4 (Intro) → introduction.md
- Item 5-13 (Methods) → methods.md
- Item 14-18 (Results) → results.md
- Item 19-21 (Discussion) → discussion.md + conclusions.md
- Item 22 (Funding) → tambahkan di compile (Fase 3)
- Item 12 opsional (Critical Appraisal): jika skip, justifikasi wajib di Methods

Untuk MISSING/PARTIAL: rekomendasi fix spesifik.

=== FASE 3: COMPILE .md MASTER ===
Compile semua section dari outputs/manuscript/ ke outputs/manuscript_final.md.

Urutan 16 section:
1. Title (dari title.md, pilih rekomendasi)
2. Abstract
3. Keywords (3-5, generate dari abstract)
4. Introduction
5. Methods
6. Results
7. Discussion
8. Future Research Agenda
9. Conclusions
10. Funding [placeholder]
11. Conflict of Interest [placeholder]
12. AI Assistance Declaration:
    "We used Claude (Anthropic) as an AI assistant for [list tahap].
    All final decisions and content remained the responsibility of the
    authors."
13. References
14. Figure Captions (semua dari outputs/figures/, gunakan SVG filename)
15. Tables (dari results.md)
16. Supplementary list: prisma_scr_checklist.md, charting.xlsx,
    screening.xlsx, protocol OSF [URL]

Pastikan: smooth transitions, heading hierarchy konsisten, figure/table
callouts ke SVG filename, canonical terminology.

=== FASE 4: COMPILE .docx (SUBMISSION-READY) ===
Convert outputs/manuscript_final.md → outputs/manuscript_final.docx.

Pilih metode yang feasible di sistem peserta:

OPSI A — Pandoc (recommended):
  pandoc outputs/manuscript_final.md -o outputs/manuscript_final.docx \
    --reference-doc=[template jurnal jika ada] \
    --citeproc --bibliography=outputs/manuscript/references.bib

OPSI B — Python python-docx (jika Pandoc tidak ada):
  Generate convert_to_docx.py: parse heading hierarchy → Word styles,
  insert tables, figure placeholders, save .docx

OPSI C — Manual fallback: output instruksi install Pandoc + run command

Formatting targets: Times New Roman 12pt, double-spaced, margin 1",
heading styles built-in, references hanging indent 0.5", page numbers
bottom right, line numbers continuous.

Catatan SVG: Word tidak embed SVG native — gunakan PNG version dari
outputs/figures/ untuk insert (atau convert SVG→PNG/EMF dulu).

=== FASE 5: PRE-SUBMISSION CHECKLIST + HASIL AKHIR ===

Tulis ke outputs/modul9_summary.md (HASIL AKHIR + checklist):

=== MANUSCRIPT WRITING COMPLETE (ScR) ===

PER-SECTION FILES (outputs/manuscript/):
- methods.md, results.md, discussion.md, future_research.md,
  introduction.md, conclusions.md, references.md, abstract.md, title.md

FINAL DELIVERABLES:
- outputs/manuscript_final.md (master compile)
- outputs/manuscript_final.docx (submission-ready)
- outputs/prisma_scr_checklist.md (supplementary 22-item)
- outputs/coherence_audit.md (audit log)
- outputs/modul9_summary.md (file ini)

PRE-SUBMISSION CHECKLIST:
[ ] manuscript_final.docx generated
[ ] Word count total + abstract sesuai jurnal target
[ ] Reference style sesuai jurnal target
[ ] Figures (SVG submission, PNG preview): 6+ files
[ ] Tables embedded di docx
[ ] Funding section diisi (BUKAN placeholder)
[ ] Conflict of Interest diisi
[ ] AI Assistance Declaration ada
[ ] Author info + affiliations + ORCID
[ ] Cover letter (terpisah)
[ ] PRISMA-ScR checklist (supplementary)
[ ] Protocol URL (OSF) disclosed
[ ] charting.xlsx + screening.xlsx siap supplementary
[ ] Ethical statement (jika applicable)

REVIEWER-PROOF ELEMENTS (ScR-specific):
- "Scoping review" eksplisit di Title, Abstract, Methods
- PCC framework (bukan PICO) end-to-end
- PRISMA-ScR flow diagram (bukan PRISMA 2020)
- Critical appraisal: non-exclusionary / justifikasi skip
- Charting (bukan extraction) iteratif
- EGM hero figure
- Triple-track implications
- Future Research Agenda matriks prioritas
- TIDAK ADA causal/effect/meta-analysis claims
- JBI + PRISMA-ScR + Munn et al. (2018) di references
- Protocol OSF disclosed + AI Declaration di Methods

NEXT: Submission ke jurnal target. Cover letter dibuat terpisah.

=== KONFIRMASI AKHIR ===
Konfirmasi semua file deliverable tersimpan + path absolut + langkah manual
yang masih perlu peserta selesaikan (insert figures di Word, isi funding/COI
placeholders, write cover letter).
No preamble.
```

> **💡 Manfaat single prompt:** L10 mengeksekusi 5 fase berurutan dalam satu sesi cowork — audit → compliance → compile .md → compile .docx → checklist + summary. Tidak butuh section "HASIL AKHIR" terpisah; file `modul9_summary.md` menggantikannya.

---

## **TROUBLESHOOTING**

**1. Compile .docx gagal (Pandoc tidak ada / error)**
- Install Pandoc: https://pandoc.org/installing.html
- Alternatif: gunakan Python python-docx (script di L10.4 Opsi B)
- Last resort: copy-paste manuscript_final.md ke Word, format manual

**2. Figures SVG tidak masuk .docx**
- Word tidak embed SVG native (versi lama). Solusi: convert SVG → PNG/EMF
- Cowork bisa generate script convert: `cairosvg fig.svg -o fig.png`
- Insert PNG version dari outputs/figures/ secara manual

**3. PRISMA-ScR item ada yang MISSING di compliance check**
- Item 12 (Critical Appraisal) skip → justifikasi di Methods (rujuk JBI)
- Item 5 (Protocol) tidak registered → akui di Limitations
- Item 22 (Funding) → tidak boleh kosong, isi "None" jika tidak ada

**4. Reviewer minta meta-analysis atau pooled estimate**
- Tegaskan: ini ScR, bukan SLR (rujuk JBI Manual Ch.11 + Munn et al. 2018)
- Response letter: cite PRISMA-ScR item 13 (mapping, bukan pooling)
- Jika subset homogen ada: pertimbangkan mini-SLR follow-up terpisah

**5. Klaim causal slip masuk Discussion/Abstract**
- Re-run L10.1 audit dengan trigger words check
- Replace dengan: "described", "reported", "characterized", "mapped"
- Self-check: setiap claim trace ke "what mapping shows", bukan "what evidence proves"

**6. Token cowork hampir habis di L10**
- L10 paling intensive (compile semua sections)
- Tip: jalankan L10.1-L10.5 dalam sesi terpisah jika perlu
- Atau: skip audit otomatis (L10.1) jika peserta sudah self-audit manual
