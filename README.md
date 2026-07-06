# MAT107 Probability Theory Group Project

This repository is for our MAT107 Probability Theory group project. It keeps the project instructions, Excel worksheet, LaTeX references, and our report source files in one shared place so everyone can work from the same materials.

## Repository Contents

```text
.
├── Group_X_MAT107_Project_Worksheet.xlsx
├── InstructionsOnLatex/
│   └── lshort.pdf
├── ProjectInstructions/
│   ├── MAT107_Project_202604.pdf
│   ├── MAT107_Project_202604.tex
│   └── xmumlogo.png
├── report/
│   └── report.tex
├── .gitignore
└── README.md
```

### Important Files

- `ProjectInstructions/MAT107_Project_202604.pdf`: official project instructions. Read this first.
- `ProjectInstructions/MAT107_Project_202604.tex`: LaTeX source for the official instructions. This can be used as a style reference.
- `ProjectInstructions/xmumlogo.png`: logo image used by the instruction LaTeX file.
- `Group_X_MAT107_Project_Worksheet.xlsx`: Excel worksheet for data generation and computations.
- `InstructionsOnLatex/lshort.pdf`: LaTeX reference guide.
- `report/report.tex`: our group report source file. Write and edit the report here.

## Project Requirements

According to the instruction file, the group must submit:

1. The final report PDF.
2. The completed Excel file.

Both final files should be named:

```text
Group_X_MAT107_Project_202604
```

Replace `X` with our assigned group number.

The report must be written in LaTeX and should use a report/textbook style, not a simple problem-and-solution format. The instruction file also says that each member's contribution must be summarized in the final section.

## Suggested Workflow

1. Read `ProjectInstructions/MAT107_Project_202604.pdf`.
2. Use `Group_X_MAT107_Project_Worksheet.xlsx` to generate and compute the required data.
3. Write the report in `report/report.tex`.
4. Compile `report/report.tex` into a PDF.
5. Before submission, rename the final PDF and Excel file using the required group file name.

## Working With the Excel File

The instruction file says the Excel worksheet contains random data generation. Because random values can change when Excel recalculates, copy generated data from the data generation sheet to the computation sheet using **Paste Values**.

Before editing the Excel file:

1. Pull the latest version from Git.
2. Tell the group you are editing it.
3. Commit and push your changes when you finish.

Excel files are binary files, so Git cannot merge two people's edits easily. Avoid having multiple people edit the worksheet at the same time.

## Working With LaTeX

Edit the report in:

```text
report/report.tex
```

If you use a local LaTeX installation, a common command is:

```bash
pdflatex report.tex
```

Run this command from inside the `report/` folder:

```bash
cd report
pdflatex report.tex
```

If references, citations, or table numbers do not update correctly, run `pdflatex` more than once.

## Git Basics

Git tracks changes to the project. GitHub or another remote repository stores the shared copy online.

### Check the Current Status

```bash
git status
```

Use this before and after making changes. It shows which files were changed, added, or deleted.

### Get the Latest Version

Before starting work, run:

```bash
git pull
```

This downloads the latest changes from the shared repository.

### Add Your Changes

After editing files, choose what to include in your commit:

```bash
git add README.md
git add report/report.tex
```

To add all changed files:

```bash
git add .
```

Use `git add .` carefully, because it adds every changed file in the repository.

### Commit Your Changes

A commit saves a snapshot of your work locally:

```bash
git commit -m "Write introduction section"
```

Good commit messages are short and specific, for example:

```text
Add binomial distribution explanation
Update Excel results for Problem 1
Fix formatting in contribution section
```

### Push Your Changes

After committing, upload your changes:

```bash
git push
```

### Recommended Daily Workflow

```bash
git pull
git status
# edit files
git status
git add <files>
git commit -m "Describe what changed"
git push
```

## Avoiding Conflicts

- Always run `git pull` before editing.
- Tell the group before editing the Excel file.
- Do not edit the same report section at the same time as another member.
- Commit small, clear changes instead of one very large commit.
- If Git reports a conflict, do not panic. Open the conflicted file, discuss with the group if needed, fix the marked sections, then commit the resolved file.

## Files Not to Commit

The `.gitignore` file should be used for generated or temporary files, such as LaTeX build files. In general, avoid committing:

- `.aux`
- `.log`
- `.out`
- `.toc`
- temporary Excel lock files like `~$filename.xlsx`
- system files such as `.DS_Store`

The final PDF may be committed if the group decides to keep compiled outputs in the repository. If not, keep only the LaTeX source and Excel worksheet under version control.

## Team Notes

Please keep the report clear and readable:

- Write in full sentences.
- Explain calculations, not only final answers.
- Use tables for probability values and relative frequencies.
- Include comparisons between theoretical values and simulated results.
- Record each member's contribution in the final contribution section.
