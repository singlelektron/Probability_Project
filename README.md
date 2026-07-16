# MAT107 Probability Theory Group Project

This repository contains the completed analysis for Group 3 of the MAT107 Probability Theory project. The project compares drawing 20 balls from an urn with and without replacement, using 500 simulated experiments for each model.

## Group and project parameters

| Student | Student ID |
|---|---|
| Zhang Yang | MAT2509036 |
| Zhu Xinbo | MAT2509040 |
| Chen Yanfu | MAT2509003 |
| Zhang Qixuan | MAT2509034 |

- Group number: **3**
- White balls: \(m=117\)
- Black balls: \(n=191\)
- Total balls: \(N=308\)
- Probability of white on the first draw: \(p=117/308\approx0.379870\)

The contribution allocation is intentionally left undetermined. Complete the contribution section in the LaTeX source before submission.

## Completed deliverables

The two files required by the project instructions are:

- `outputs/019f5a64-406e-7bc1-a09a-31f20172f71a/Group_3_MAT107_Project_202604.xlsx`
- `output/pdf/Group_3_MAT107_Project_202604.pdf`

The editable report source is:

- `report/Group_3_MAT107_Project_202604.tex`

The original blank workbook is preserved as `Group_X_MAT107_Project_Worksheet.xlsx`.

## What was completed in the workbook

The final workbook contains five sheets:

1. `Team_Info` records the group members and the values of \(m\), \(n\), \(N\), and \(p\).
2. `Problem1_Data_Generation` contains volatile `RAND()` formulas for sampling with replacement.
3. `Problem1_Computations` contains a fixed 500-by-20 snapshot, row-level calculations, a binomial probability table, empirical frequencies, and the required approximation results.
4. `Problem2_Data_Generation` updates the probability of white after every draw to simulate sampling without replacement.
5. `Problem2_Computations` contains the fixed second snapshot, the hypergeometric probability table, empirical frequencies, and comparisons with Problem 1.

The computation sheets contain fixed `W`/`B` values. Recalculating Excel can change the data-generation sheets, but it does not change the submitted results or the values quoted in the report.

## Main results

### With replacement

- Theoretical white proportion: `0.379870`
- Simulated white proportion from 10,000 draws: `0.378400`
- Theoretical mean white count: `7.597403`
- Simulated mean white count: `7.568000`
- Probability of no white among the first three: `0.238478`; simulation: `0.228000`
- Probability of four whites before five blacks: `0.359647`; simulation: `0.372000`
- Exact \(P(X<6)\): `0.167366`; simulation: `0.168000`
- Poisson approximation: `0.230956`
- Continuity-corrected normal approximation: `0.166949`
- Standard-normal-table approximation using \(z=-0.97\): `0.166000`

### Without replacement

- Theoretical mean white count: `7.597403`
- Simulated mean white count: `7.606000`
- Probability of no white among the first three: `0.237049`
- Simulated frequency of no white among the first three: `0.246000`

The report explains the probability models, approximation errors, finite-population correction, and differences between the two sampling procedures. It also includes an indicator-variable proof of the expected value for sampling without replacement.

## Reading and using the workbook

Open the completed `.xlsx` file in Microsoft Excel or another compatible application.

- Start with `Team_Info` to confirm the group parameters.
- Use the orange and blue summary blocks on the computation sheets for the report-ready results.
- Scroll left on each computation sheet to inspect the 500 frozen experiments.
- Formula cells calculate counts, relative frequencies, probability mass functions, deviations, and relative errors.
- Do not replace the frozen computation data unless the group intends to regenerate every result and update the report.

If new random data are required, allow a data-generation sheet to recalculate, copy `B2:U501`, and paste **values only** into the matching computation sheet. The report must then be updated to match the new summary values.

## Editing and compiling the report

Edit:

```text
report/Group_3_MAT107_Project_202604.tex
```

The most important remaining edit is the final `Contribution` section. Replace each placeholder with an accurate summary agreed by the group.

Compile from the `report/` directory:

```bash
cd report
latexmk -pdf -interaction=nonstopmode -halt-on-error \
  -outdir=../output/pdf Group_3_MAT107_Project_202604.tex
```

The command writes the final PDF to:

```text
output/pdf/Group_3_MAT107_Project_202604.pdf
```

The verified PDF has twelve physical pages: one cover page, ten pages between the cover and contribution section, and one contribution page. This satisfies the required 6--10 page main-report range.

## Submission checklist

- [ ] Confirm all names and student IDs.
- [ ] Replace all contribution placeholders with the group’s actual contributions.
- [ ] Recompile the LaTeX report after the final edit.
- [ ] Open the PDF and check every page, table, equation, header, and footer.
- [ ] Open the final Excel file and confirm both computation summaries are visible.
- [ ] Confirm the PDF and Excel file are both named `Group_3_MAT107_Project_202604`.
- [ ] Submit the PDF and Excel workbook before **Friday, 17 July 2026, 23:59**.

## Repository map

```text
.
├── Group_X_MAT107_Project_Worksheet.xlsx     # original blank template
├── outputs/019f5a64-406e-7bc1-a09a-31f20172f71a/
│   └── Group_3_MAT107_Project_202604.xlsx    # completed workbook
├── output/pdf/
│   └── Group_3_MAT107_Project_202604.pdf     # final compiled report
├── report/
│   ├── Group_3_MAT107_Project_202604.tex     # editable report source
│   └── xmumlogo.png
├── ProjectInstructions/
│   └── MAT107_Project_202604.tex             # official instructions
└── README.md
```

## Git workflow for team members

Before editing:

```bash
git pull
git status
```

After editing:

```bash
git status
git add <files-you-changed>
git commit -m "Describe the MAT107 project update"
git push
```

The Excel workbook is a binary file and cannot be merged reliably. Only one person should edit it at a time. Tell the group before changing the workbook and push the completed edit before another person begins.
