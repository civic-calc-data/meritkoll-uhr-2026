# Meritkoll Swedish Admissions & Gy25 Open Data (2026)

Open CSV datasets covering Swedish university admission cutoffs from Universitets- och högskolerådet (UHR) for Autumn 2026 (`HT2026`, Selection Round 2 / *Urval 2*) alongside a deterministic simulation of Sweden's upper-secondary subject-grade reform (*Gy25* vs. *Gy11*) across four university-preparatory programs.

Full interactive calculators, methodology notes, and Swedish-language reports live at [meritkoll.se/rapporter/](https://meritkoll.se/rapporter/).

## Svensk sammanfattning

Det här arkivet samlar två öppna CSV-filer från [Meritkoll.se](https://meritkoll.se/) baserade på UHR:s antagningsstatistik för HT 2026 (Urval 2) samt Skolverkets och Antagning.se:s föreskrifter för Gy25:

- **Högsta gränser HT 2026 (`antagningspoang-topp.csv`, 28 program):** KTH Civilingenjör teknisk fysik toppar direktgruppen BI på `22,40` (HP `1,80`), medan Karolinska institutets läkarprogram har urvalets högsta BII-gräns på `22,46` (BI `22,29`).
- **Största lyften i urvalet från HT 2025:** Socionomprogrammet steg med `+0,99` i BI vid Stockholms universitet (`17,66` till `18,65`), `+0,83` i Uppsala (`19,48` till `20,31`) och `+0,79` i Lund (`19,11` till `19,90`).
- **BI mot BII går åt två håll:** På samtliga sju läkarprogram och fem psykologprogram i filen låg BII högre än BI. På samtliga fyra socionomprogram och på juristprogrammen i Uppsala, Stockholm och Lund låg BII i stället lägre än BI.
- **Gy25 svänger upp till +3,08 eller -1,98 poäng (`gy25-vs-gy11-scenarier.csv`, 16 scenarier):** På Naturvetenskapsprogrammet (NA), där `1 850` av `2 400` examenspoäng ligger i flernivåämnen, lyfter en stark uppryckning (`D -> C -> A`) meritvärdet från `18,85` i Gy11 till `21,93` i Gy25 (`+3,08`), medan en nedgång (`A -> B -> C`) sänker det från `20,05` till `18,07` (`-1,98`).

Använd de öppna verktygen på [meritkoll.se](https://meritkoll.se/), [Högskoleprovet normering](https://meritkoll.se/hogskoleprovet-normering/) samt gratis inbäddningsbar gymnasieräknare på [meritkoll.se/embed/gymnasiet/](https://meritkoll.se/embed/gymnasiet/).

---

## Datasets in this repository

| File | Coverage | Live report (Swedish) |
|---|---|---|
| [`data/antagningspoang-topp.csv`](data/antagningspoang-topp.csv) | 28 competitive full-time campus programs across 9 Swedish universities: BI, BII, HP, and admitted counts for HT 2026 Urval 2 vs. HT 2025 | [Antagningspoäng HT 2026](https://meritkoll.se/rapporter/antagningspoang-sverige/) |
| [`data/gy25-vs-gy11-scenarier.csv`](data/gy25-vs-gy11-scenarier.csv) | 16 deterministic Gy25 vs. Gy11 scenarios across NA, SA, EK, and TE (2,400 exam credits excluding *gymnasiearbetet*) | [Gy25 vs Gy11: Effekt på meritvärde](https://meritkoll.se/rapporter/gy25-och-meritvarde/) |

---

## 1. Competitive Swedish University Cutoffs: HT 2026 Urval 2 (UHR)

Selected highlights from [`data/antagningspoang-topp.csv`](data/antagningspoang-topp.csv) (top 15 rows by BI cutoff; all 28 rows are in the CSV):

| Program | University | Code | BI HT26 | BII HT26 | HP HT26 | Admitted | BI HT25 | HP HT25 |
|---|---|---|---:|---:|---:|---:|---:|---:|
| Civilingenjör teknisk fysik | Kungl. Tekniska högskolan | `KTH-32114` | 22.40 | 22.19 | 1.80 | 143 | 22.40 | 1.75 |
| Läkarprogrammet | Karolinska institutet | `KI-41006` | 22.29 | 22.46 | 1.75 | 228 | 22.19 | 1.70 |
| Civilingenjör teknisk matematik | Kungl. Tekniska högskolan | `KTH-32116` | 22.29 | 22.31 | 1.80 | 75 | 22.31 | 1.70 |
| Läkarprogrammet | Lunds universitet | `LU-80510` | 22.26 | 22.29 | 1.80 | 154 | 22.29 | 1.75 |
| Läkarprogrammet | Uppsala universitet | `UU-P3200` | 22.19 | 22.20 | 1.75 | 135 | 22.08 | 1.75 |
| Psykologprogrammet | Lunds universitet | `LU-80438` | 21.98 | 22.01 | 1.70 | 50 | 21.88 | 1.65 |
| Läkarprogrammet | Göteborgs universitet | `GU-01001` | 21.88 | 22.01 | 1.70 | 190 | 21.70 | 1.65 |
| Juristprogrammet | Lunds universitet | `LU-80300` | 21.82 | 21.80 | 1.60 | 190 | 21.77 | 1.55 |
| Civilingenjör industriell ekonomi | Kungl. Tekniska högskolan | `KTH-32106` | 21.82 | 21.98 | 1.80 | 190 | 21.67 | 1.70 |
| Psykologprogrammet | Uppsala universitet | `UU-P2550` | 21.77 | 22.19 | 1.65 | 50 | 21.72 | 1.60 |
| Läkarprogrammet | Linköpings universitet | `LIU-50313` | 21.56 | 21.88 | 1.65 | 185 | 21.51 | 1.60 |
| Juristprogrammet | Uppsala universitet | `UU-P2800` | 21.56 | 21.30 | 1.50 | 192 | 21.56 | 1.50 |
| Psykologprogrammet | Göteborgs universitet | `GU-74031` | 21.56 | 21.77 | 1.60 | 60 | 21.48 | 1.65 |
| Läkarprogrammet | Örebro universitet | `ORU-89600` | 21.51 | 21.82 | 1.65 | 105 | 21.46 | 1.60 |
| Läkarprogrammet | Umeå universitet | `UMU-P1308` | 21.30 | 21.71 | 1.60 | 185 | 21.30 | 1.55 |

Key patterns across all 28 rows:
- **Seat volume drives cutoffs between cities:** Karolinska institutet admitted 150 psychology students (`BI 20.90`), while Lund and Uppsala admitted 50 each (`BI 21.98` and `21.77`). In law (*Juristprogrammet*), Stockholm admitted 360 (`BI 20.68`) versus Lund's 190 (`BI 21.82`).
- **Medical school spread is narrow (`0.99` points):** All seven Swedish medical programs fall between `21.30` (Umeå) and `22.29` (KI) in BI, and between `1.60` and `1.80` on Högskoleprovet.
- **Divergent BI vs. BII (Komvux) behavior:** BII was strictly higher than BI on all seven medical programs and all five psychology programs (up to `+0.42` at Uppsala psychology and `+0.41` at Umeå medicine). On all four social work (*Socionomprogrammet*) rows in the file, BII was lower than BI (by `0.23` to `0.56` points).

---

## 2. Gy25 Subject Grades vs. Gy11 Course Grades (`gy25-vs-gy11-scenarier.csv`)

From 1 July 2025, Sweden replaced course grades (Gy11) with subject grades (Gy25). A passing grade (`A` to `E`) on the highest completed level in a multi-level subject replaces all earlier levels in that subject for its entire credit weight. Each template models 2,400 graded credits (excluding the 100-credit *gymnasiearbetet*), holding single-level subjects constant at `B` (`17.50`).

| Code | Program | Multi-level credits | Scenario | Gy11 GPA | Gy25 GPA | Diff | Merit pts | Gy11 total | Gy25 total |
|---|---|---:|---|---:|---:|---:|---:|---:|---:|
| `NA` | Naturvetenskapsprogrammet | 1,850 | Stigande form (`C -> B -> A`) | 17.45 | 19.43 | +1.98 | 2.50 | 19.95 | 21.93 |
| `NA` | Naturvetenskapsprogrammet | 1,850 | Stark uppryckning (`D -> C -> A`) | 16.35 | 19.43 | +3.08 | 2.50 | 18.85 | 21.93 |
| `NA` | Naturvetenskapsprogrammet | 1,850 | Jämn prestationsnivå (`B -> B`) | 17.50 | 17.50 | 0.00 | 2.50 | 20.00 | 20.00 |
| `NA` | Naturvetenskapsprogrammet | 1,850 | Svagare slutnivå (`A -> B -> C`) | 17.55 | 15.57 | -1.98 | 2.50 | 20.05 | 18.07 |
| `SA` | Samhällsvetenskapsprogrammet | 1,700 | Stigande form (`C -> B -> A`) | 17.50 | 19.27 | +1.77 | 2.50 | 20.00 | 21.77 |
| `SA` | Samhällsvetenskapsprogrammet | 1,700 | Stark uppryckning (`D -> C -> A`) | 16.46 | 19.27 | +2.81 | 2.50 | 18.96 | 21.77 |
| `SA` | Samhällsvetenskapsprogrammet | 1,700 | Jämn prestationsnivå (`B -> B`) | 17.50 | 17.50 | 0.00 | 2.50 | 20.00 | 20.00 |
| `SA` | Samhällsvetenskapsprogrammet | 1,700 | Svagare slutnivå (`A -> B -> C`) | 17.50 | 15.73 | -1.77 | 2.50 | 20.00 | 18.23 |
| `EK` | Ekonomiprogrammet | 1,500 | Stigande form (`C -> B -> A`) | 17.50 | 19.06 | +1.56 | 2.50 | 20.00 | 21.56 |
| `EK` | Ekonomiprogrammet | 1,500 | Stark uppryckning (`D -> C -> A`) | 16.67 | 19.06 | +2.39 | 2.50 | 19.17 | 21.56 |
| `EK` | Ekonomiprogrammet | 1,500 | Jämn prestationsnivå (`B -> B`) | 17.50 | 17.50 | 0.00 | 2.50 | 20.00 | 20.00 |
| `EK` | Ekonomiprogrammet | 1,500 | Svagare slutnivå (`A -> B -> C`) | 17.50 | 15.94 | -1.56 | 2.50 | 20.00 | 18.44 |
| `TE` | Teknikprogrammet | 1,700 | Stigande form (`C -> B -> A`) | 17.40 | 19.27 | +1.87 | 2.00 | 19.40 | 21.27 |
| `TE` | Teknikprogrammet | 1,700 | Stark uppryckning (`D -> C -> A`) | 16.35 | 19.27 | +2.92 | 2.00 | 18.35 | 21.27 |
| `TE` | Teknikprogrammet | 1,700 | Jämn prestationsnivå (`B -> B`) | 17.50 | 17.50 | 0.00 | 2.00 | 19.50 | 19.50 |
| `TE` | Teknikprogrammet | 1,700 | Svagare slutnivå (`A -> B -> C`) | 17.60 | 15.73 | -1.87 | 2.00 | 19.60 | 17.73 |

Note: Under Antagning.se rules, *Matematik*, *Matematik - fortsättning*, and *Matematik - fördjupning* count as three separate subjects. A failing `F` on the highest level retains the last passing grade on earlier levels.

---

## Column Dictionary

### `data/antagningspoang-topp.csv`
- `program`: Official Swedish degree program name.
- `larosate`: Admitting Swedish university or university college (*lärosäte*).
- `anmalningskod`: Official Antagning.se / UHR application code.
- `ort`: Campus city.
- `termin`: Admission semester (`HT2026`).
- `urval`: Selection round (`Urval 2`).
- `bi_ht26`: Lowest admitted merit score in direct upper-secondary group `BI` (scale up to `22.50`), HT 2026.
- `bii_ht26`: Lowest admitted merit score in supplemented/Komvux group `BII`, HT 2026.
- `hp_ht26`: Lowest admitted Högskoleprovet score (`0.00` to `2.00`), HT 2026.
- `antagna_ht26`: Total number of admitted applicants in Urval 2, HT 2026.
- `bi_ht25`: Reference `BI` cutoff from HT 2025 Urval 2.
- `hp_ht25`: Reference `HP` cutoff from HT 2025 Urval 2.
- `kalla`: Primary statistical source (`UHR antagningsstatistik`).

### `data/gy25-vs-gy11-scenarier.csv`
- `program_kod`: National upper-secondary program code (`NA`, `SA`, `EK`, `TE`).
- `program`: Program name in Swedish.
- `scenario`: Grade trajectory applied across multi-level subjects.
- `poang_totalt`: Total graded exam credits included in the GPA calculation (`2400`, excluding *gymnasiearbetet*).
- `poang_flerniva`: Credits belonging to multi-level subjects (`1850` on NA, `1700` on SA/TE, `1500` on EK).
- `gy11_jamforelsetal`: Weighted course-grade average under Gy11 (`0.00` to `20.00`).
- `gy25_jamforelsetal`: Weighted subject-grade average under Gy25 (`0.00` to `20.00`).
- `skillnad_jamforelsetal`: Difference `gy25_jamforelsetal - gy11_jamforelsetal`.
- `meritpoang`: Extra merit points added (`2.50` for NA/SA/EK; `2.00` for TE without modern languages).
- `gy11_meritvarde`: Final admissions merit score (`gy11_jamforelsetal + meritpoang`).
- `gy25_meritvarde`: Final admissions merit score (`gy25_jamforelsetal + meritpoang`).

---

## Primary Official Sources and Interactive Tools

Official sources:
- Universitets- och högskolerådet (UHR): [Antagningsstatistik](https://www.uhr.se/studier-och-antagning/antagningsstatistik/) and [Urvalsgrupper BI/BII/HP](https://www.uhr.se/studier-och-antagning/antagningsstatistik/urval-och-urvalsgrupper/)
- Skolverket: [Gy25: ämnesbetyg på gymnasial nivå](https://www.skolverket.se/styrning-och-ansvar/en-skola-i-forandring/tidigare-forandringar/gy25----amnesbetyg-pa-gymnasial-niva)
- Antagning.se: [Räkna ut ditt meritvärde i Gy25](https://www.antagning.se/sv/betyg-och-behorighet/amnesbetyg-pa-gymnasieniva-gy25/rakna-ut-ditt-meritvarde-i-gy25/) and [Meritpoäng i Gy25](https://www.antagning.se/sv/betyg-och-behorighet/amnesbetyg-pa-gymnasieniva-gy25/meritpoang-i-gy25/)

Interactive tools and reports on Meritkoll.se:
- Reports hub: https://meritkoll.se/rapporter/
- UHR HT 2026 cutoffs report: https://meritkoll.se/rapporter/antagningspoang-sverige/
- Gy25 vs. Gy11 report: https://meritkoll.se/rapporter/gy25-och-meritvarde/
- Högskoleprovet normering tables and converter: https://meritkoll.se/hogskoleprovet-normering/
- Lightweight upper-secondary merit calculator embed (iframe for schools and SYV, no login): https://meritkoll.se/embed/gymnasiet/

## License and Citation

All CSV files and documentation are released under [Creative Commons Attribution 4.0 International (CC-BY-4.0)](LICENSE).

You may republish, chart, or adapt these files with attribution to the respective Swedish public agency and **Meritkoll.se** (`https://meritkoll.se/rapporter/`). Machine-readable citation metadata is provided in [`CITATION.cff`](CITATION.cff).

```text
Meritkoll.se (2026). Meritkoll Swedish University Admissions & Gy25 Data (2026): UHR HT 2026 Urval 2 Cutoffs and Gy25 vs. Gy11 Meritvärde Scenarios [Dataset]. https://meritkoll.se/rapporter/ (CC-BY-4.0).
```
