# 🎓 Master's Thesis LaTeX Template – TH Nürnberg

A professional, ready-to-use LaTeX template for writing your thesis at Technische Hochschule Nürnberg Georg Simon Ohm.
Includes automatic PDF building with GitHub Actions, pre-configured bibliography system, abbreviations glossary and comprehensive documentation.
Based on [Korbinian Riedhammer's thesis template](https://github.com/riedhammer/thesis-template), but optimized und formatted further.

---

## ✨ Features

- ✅ **Professional LaTeX Setup** - Pre-configured for German academic theses
- ✅ **10 Pre-Structured Chapters** - Introduction, literature review, background, methodology, results, contributions, discussion, conclusion, and appendices
- ✅ **Automatic PDF Builds** - GitHub Actions compiles PDF on every push
- ✅ **Bibliography System** - BibTeX pre-configured with TH Nürnberg style (wmaainf.bst)
- ✅ **Abbreviations/Glossary** - Built-in acronym management with auto-expansion
- ✅ **Code Highlighting** - Syntax highlighting for Go, JSON and generic code
- ✅ **Legal Documents** - Built-in handling for official declaration (Prüfungsrechtliche Erklärung)
- ✅ **Comprehensive Comments** - Inline documentation explaining every section
- ✅ **Easy Customization** - Single metadata section to update your information
- ✅ **Local & Cloud Builds** - Compile locally with VS Code or automatically on GitHub

---

## 🚀 Quick Start (4 Steps)

### 1. Fork This Repository

**Important:** You need your own copy to push changes and use GitHub Actions!

1. Click the **"Fork"** button in the top-right corner of this GitHub page
2. This creates your own copy: `github.com/yourusername/thesis-template`

### 2. Clone Your Fork

```bash
git clone https://github.com/yourusername/th-nuernberg-thesis-template
cd th-nuernberg-thesis-template
```

Replace `yourusername` with your actual GitHub username.

### 3. Update Your Information

Edit `thesis.tex` lines 20-45 with your details:

```latex
\newcommand{\titel}{Prototypischer Entwurf einer LaTeX-Vorlage für Abschlussarbeiten}  % Your thesis title
\newcommand{\artderarbeit}{Masterarbeit}  % Type: Bachelorarbeit or Masterarbeit
\newcommand{\autor}{Max Mustermann}  % Your full name
\newcommand{\studiengang}{Wirtschaftsinformatik}  % Your study program (e.g., Informatik, Wirtschaftsinformatik, Medieninformatik)
\newcommand{\matrikelnr}{12345678}  % Your matriculation number (8 digits)
\newcommand{\bearbeitungsbeginn}{12.34.5678}  % Start date (DD.MM.YYYY format)
\newcommand{\bearbeitungsende}{12.34.5678}  % End date (DD.MM.YYYY format)
\newcommand{\erstgutachter}{Prof.\,Dr.~Max Mustermann}  % First examiner (primary supervisor)
\newcommand{\zweitgutachter}{Prof.\,Dr.~Max Mustermann}  % Second examiner (secondary supervisor)
\newcommand{\betreuer}{Max Mustermann}  % Advisor/Tutor from company (if thesis is company-based, otherwise remove this line)
\newcommand{\unternehmen}{Muster GmbH}  % Company name (if thesis is company-based, otherwise remove this line)
\newcommand{\logo}{official_documents/Ohm_Logo.png}  % Path to university logo image file
\newcommand{\keywords}{Schlagwort 1, Schlagwort 2, Schlagwort 3, Schlagwort 4, Schlagwort 5}  % 5-7 keywords separated by commas
```

### 4. Start Writing

Edit chapter files in `content/`:
- `0A_abstract.tex` - Write your abstract
- `1_introduction.tex` - Your introduction
- `2_related_work.tex` - Literature review
- ...and so on

Push to GitHub and your PDF builds automatically! 🎉

---

## 🛠️ Prerequisites & Setup

### Option A: Local Development (Recommended)

#### Installation (Windows/Mac/Linux)

1. **Install [MiKTeX](https://miktex.org/)**
   - Download from https://miktex.org/
   - Provides LaTeX compiler and `latexmk`
   - Follow installer instructions

2. **Install [Perl](https://strawberryperl.com/)**
   - Download from https://strawberryperl.com/
   - Required by `latexmk` for multi-pass compilation
   - Follow installer instructions

3. **Install [VS Code](https://code.visualstudio.com/)**
   - Download from https://code.visualstudio.com/
   - Free code editor from Microsoft

4. **Install LaTeX Workshop Extension**
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X)
   - Search for "LaTeX Workshop"
   - Click Install
   - [GitHub](https://github.com/James-Yu/LaTeX-Workshop)

#### Verify Installation

```bash
latexmk --version      # Should show version info
perl --version         # Should show Perl version
```

#### Compile Your First PDF

```bash
cd your-thesis-folder
latexmk -pdf thesis.tex
```

Or in VS Code:
- Open `thesis.tex`
- Click "Build LaTeX project" button (or press Ctrl+Alt+B)
- View PDF in side panel

### Option B: GitHub Actions (Cloud Build)

No local installation needed! Every push/commit to GitHub automatically:
- Compiles your LaTeX
- Generates PDF
- Creates GitHub Release with PDF attached
- Download the latest PDF from [GitHub Releases](../../releases)
---

## 📁 Directory Structure

```
thesis-template/
│
├── 📄 Core LaTeX Files
│   ├── thesis.tex                 ← MAIN FILE - Metadata & configuration
│   ├── cover.tex                  ← Cover/title page
│   ├── abbreviations.tex          ← Define your acronyms here
│   ├── refs.bib                   ← Bibliography entries (BibTeX)
│   └── wmaainf.bst                ← Bibliography style (TH Nürnberg)
│
├── 📚 content/                    ← Your thesis chapters
│   ├── 0A_abstract.tex            ← Abstract/Summary
│   ├── 0B_acknowledgements.tex    ← Acknowledgements (optional)
│   ├── 1_introduction.tex         ← Chapter 1
│   ├── 2_related_work.tex         ← Chapter 2
│   ├── 3_theoretical_background.tex ← Chapter 3
│   ├── 4_methodology.tex          ← Chapter 4
│   ├── 5_results.tex              ← Chapter 5
│   ├── 6_contributions.tex        ← Chapter 6
│   ├── 7_discussion.tex           ← Chapter 7
│   ├── 8_conclusion.tex           ← Chapter 8
│   └── 9_appendix.tex             ← Additional appendix content
│
├── 🖼️ figures/                    ← Your images and diagrams
│   └── (add your figures here)
│
├── 💻 listings/                   ← Code examples and technical excerpts
│   └── (add your code files here)
│
├── 📋 listingstyles/              ← Syntax highlighting for code
│   ├── listings-command.sty       ← Generic code highlighting
│   ├── listings-golang.sty        ← Go/Golang syntax
│   └── listings-json.sty          ← JSON syntax
│
├── 📖 literature/                 ← Research materials, notes
│   └── (add reference materials here)
│
├── 📎 official_documents/         ← REQUIRED: Legal declarations & logo
│   ├── cover_ohm_logo.png         ← University logo (from cover.tex)
│   └── Appendix_Pruefungsrechtliche_Erklaerung_Printversion.pdf
│
├── 📝 appendices/                 ← Supplementary material (optional)
│   └── (add additional appendices here)
│
├── 🗂️ clipboard/                  ← Working drafts (won't be synced)
│   └── (use for notes and drafts)
│
├── 🤖 .github/
│   └── workflows/
│       └── latex.yml              ← GitHub Actions configuration
│
├── 📚 Documentation
│   ├── README.md                  ← This file
│   ├── LICENSE.md                 ← MIT License
│   └── CONTRIBUTING.md            ← How to contribute
│
└── ⚙️ Configuration
    └── .gitignore                 ← Excludes build files from Git
```

---

## ✏️ Customization Guide

### 1. Update Your Metadata

Edit `thesis.tex` lines 20-45 to personalize your thesis:

| Command | What It Does | Example |
|---------|-------------|---------|
| `\titel` | Your thesis title | "Machine Learning in Cloud Computing" |
| `\artderarbeit` | Thesis type | "Masterarbeit" or "Bachelorarbeit" |
| `\autor` | Your full name | "Max Mustermann" |
| `\studiengang` | Study program | "Informatik" or "Wirtschaftsinformatik" |
| `\matrikelnr` | Student ID | "12345678" (8 digits) |
| `\bearbeitungsbeginn` | Start date | "01.01.2024" (DD.MM.YYYY) |
| `\bearbeitungsende` | End date | "30.06.2024" (DD.MM.YYYY) |
| `\erstgutachter` | Primary supervisor | "Prof.\,Dr.~John Doe" |
| `\zweitgutachter` | Secondary supervisor | "Prof.\,Dr.~Jane Smith" |
| `\betreuer` | Company advisor (optional) | "Supervisor Name" |
| `\unternehmen` | Company name (optional) | "Acme Corporation" |
| `\keywords` | Search keywords (5-7) | "keyword1, keyword2, ..." |

### 2. Update Your Logo

Replace `figures/cover_ohm_logo.png` with your university/company logo.

The logo path is set in `thesis.tex`:
```latex
\newcommand{\logo}{official_documents/cover_ohm_logo.png}
```

### 3. Add Abbreviations

Edit `abbreviations.tex` to add your domain-specific acronyms:

```latex
\newacronym{ml}{ML}{Machine Learning}
\newacronym{ai}{AI}{Artificial Intelligence}
\newacronym{nlp}{NLP}{Natural Language Processing}
```

Use in your text:
```latex
The field of \gls{ml} is rapidly evolving, with \gls{ai} applications everywhere.
```

First use expands: "Machine Learning (ML)"  
Later uses: "ML"

### 4. Customize Faculty/University

In `cover.tex` line 7, change:
```latex
\large{Fakultät Informatik}\\[1cm]
```

To your faculty:
```latex
\large{Fakultät Wirtschaft und Medien}\\[1cm]
```

### 5. Add or Remove Chapters

In `thesis.tex`, modify the main matter section (around line 357):

```latex
\mainmatter
\include{content/1_introduction}
\include{content/2_related_work}
\include{content/3_theoretical_background}
% Add or remove chapters as needed
```

---

## 📝 Writing Your Content

### Chapter Structure

Each chapter file (e.g., `1_introduction.tex`) should follow this structure:

```latex
\chapter{Introduction}
\label{ch:introduction}

\section{Background}
Write your first section here. You can reference figures, tables, and citations.

\subsection{Subsection}
More detailed content...

\section{Another Section}
Continue your chapter...
```

### Essential LaTeX Commands

#### Text Formatting
```latex
\textbf{bold text}              % Bold
\emph{emphasized}               % Italic
\texttt{code or monospace}      % Monospace
```

#### Sections
```latex
\chapter{Chapter Title}          % Chapter (top level)
\section{Section}                % Section
\subsection{Subsection}          % Subsection
\subsubsection{Subsubsection}   % Subsubsection (deep nesting)
```

#### Lists
```latex
\begin{itemize}
    \item First point
    \item Second point
\end{itemize}

\begin{enumerate}
    \item First
    \item Second
\end{enumerate}
```

#### Citations & References
```latex
\cite{smith2023}                         % Simple citation
\cite[S. 42]{smith2023}                 % Citation with page number (German)
\cite[pp. 42--45]{smith2023}            % Citation with page range (English)

\ref{fig:myimage}                       % Reference to label
\label{fig:myimage}                     % Create a label
```

#### Figures
```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/myimage.png}
    \caption{This is the figure caption}
    \label{fig:myimage}
\end{figure}
```

#### Tables
```latex
\begin{table}[H]
    \centering
    \caption{Table caption}
    \begin{tabular}{|l|c|r|}
        \hline
        Left & Center & Right \\
        \hline
        A & 1 & X \\
        B & 2 & Y \\
        \hline
    \end{tabular}
    \label{tab:mytable}
\end{table}
```

#### Code Listings
```latex
\begin{lstlisting}[language=Python, caption={My Python Script}]
def hello():
    print("Hello, World!")
\end{lstlisting}
```

---

## 📚 Bibliography & Citations

### Adding References

Edit `refs.bib` and add BibTeX entries:

**Journal Article:**
```bibtex
@article{smith2023,
    author = {Smith, John and Doe, Jane},
    title = {An Important Research Paper},
    journal = {Journal of Computer Science},
    year = {2023},
    volume = {45},
    number = {3},
    pages = {234--250}
}
```

**Book:**
```bibtex
@book{author2024,
    author = {Author, First},
    title = {Book Title},
    publisher = {Publisher Name},
    year = {2024},
    edition = {2nd}
}
```

**Website:**
```bibtex
@misc{example2024,
    author = {{Organization Name}},
    title = {Web Page Title},
    howpublished = {\url{https://example.com}},
    year = {2024},
    note = {Accessed: 2024-01-15}
}
```

### Using Citations

In your text:
```latex
According to \cite{smith2023}, this research shows...

Some research \cite[S. 123]{smith2023} indicates...

Multiple sources \cite{smith2023, author2024} suggest...
```

---

## 🏆 Building Your Thesis

### Build Locally (with MiKTeX + Perl)

```bash
# Single command (recommended)
latexmk -pdf thesis.tex

# Or with VS Code
# - Open thesis.tex
# - Press Ctrl+Alt+B (or click "Build" button)
# - View PDF in preview panel
```

### Build on GitHub (Automatic)

1. Push your changes:
```bash
git add .
git commit -m "Update chapter content"
git push origin main
```

2. GitHub automatically:
   - ✅ Compiles your LaTeX
   - ✅ Generates PDF
   - ✅ Creates a Release
   - ✅ Uploads PDF

3. Download from [Releases](../../releases)

---

## 📋 Legal Documents

### Official Declaration (Prüfungsrechtliche Erklärung)

This template includes handling for the required official declaration. Choose ONE of two options:

#### Option 1: Print Version (For Printing & Hand Signing)

1. Download form: https://www.th-nuernberg.de/fileadmin/global/Public_Docs/SB/SB_0009_FO_Pruefungsrechtliche_Erklaerung_und_Erklaerung_zur_Veroeffentlichung_der_Abschlussarbeit_public.pdf
2. Print the PDF
3. Sign by hand
4. Scan the signed document
5. Save to: `official_documents/Appendix_Pruefungsrechtliche_Erklaerung_Printversion.pdf`
6. In `thesis.tex` line 296, uncomment the print version line

#### Option 2: Digital Version (Pre-Scanned with Original Signature)

1. Download form (link above)
2. Print (do NOT sign yet)
3. Sign by hand
4. Scan with original signature
5. Save to: `official_documents/Appendix_Pruefungsrechtliche_Erklaerung_Digitalversion.pdf`
6. In `thesis.tex` line 298, uncomment the digital version line (default)

---

## 🐛 Troubleshooting

### "Undefined references" Warning

**Problem:** LaTeX warns "Reference `ch:xxx' undefined"

**Cause:** LaTeX requires multiple passes to resolve cross-references

**Solution:**
```bash
latexmk -pdf thesis.tex  # Runs 2-3 passes automatically
```

Or in VS Code: Just click "Build" - it handles this automatically.

### "File not found" Error

**Problem:** `! LaTeX Error: File 'figures/myimage.png' not found`

**Solution:**
- Check filename spelling exactly
- Use relative paths (not absolute): `figures/myimage.png`
- Ensure file exists in the folder
- Try `figures/my_image.png` (no spaces)

### Bibliography Not Showing

**Problem:** Citations don't appear in PDF

**Solution:**
- Check `refs.bib` syntax (mismatched braces)
- Verify key matches in `\cite{}` command
- Rebuild: `latexmk -pdf -g thesis.tex` (force rebuild)

### "Undefined control sequence"

**Problem:** `! Undefined control sequence \mycommand`

**Solution:**
- Check spelling: `\chapter` not `\Chapter`
- Check package is loaded: `\usepackage{package}`
- Check for missing braces: `{like this}`

### PDF Build Fails on GitHub

**Problem:** Actions show failure in build

**Solution:**
1. Check Actions tab → View logs
2. Look for LaTeX error messages
3. Common issues:
   - Missing closing braces `}`
   - Invalid path in `\input{}` or `\include{}`
   - Syntax error in `refs.bib`
   - Special characters not properly escaped

---

## 💡 Best Practices

### Writing

✅ **DO:**
- Commit often: `git commit` frequently
- Use meaningful commit messages: "Add methodology chapter"
- Write incrementally (don't wait until the end)
- Use labels for easy referencing: `\label{sec:background}`
- Keep chapters manageable (20-50 pages each)
- Spell-check regularly

❌ **DON'T:**
- Use absolute file paths
- Store large PDF files in the repo
- Mix figures and code in same folder
- Leave chapters over 100 pages
- Commit build artifacts (*.pdf, *.aux)
- Use special characters in file names

### Organization

✅ **DO:**
- Organize figures by chapter: `figures/ch1_*, figures/ch2_*`
- Use consistent file naming: `chapter_name_description.png`
- Add descriptive captions to all figures
- Comment your LaTeX code for clarity
- Update bibliography as you read papers

❌ **DON'T:**
- Mix content from different chapters in one file
- Use generic names: `image1.png`, `figure.pdf`
- Leave figures without captions
- Store working drafts in main folders

---

## 🔗 Useful Resources

- **Overleaf LaTeX Tutorial:** https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes
- **BibTeX Guide:** https://www.ctan.org/pkg/bibtex
- **TeX Stack Exchange:** https://tex.stackexchange.com/
- **LaTeX Workshop Docs:** https://github.com/James-Yu/LaTeX-Workshop
- **MiKTeX Manual:** https://miktex.org/manual/

---

## 📄 License

This template is based on a LaTeX template originally created for academic use and is provided under the **MIT License**.

See [LICENSE.md](./LICENSE.md) for details.

---

## 🤝 Contributing

Found a bug? Have an improvement? Contributions welcome!

See [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

---

## 📞 Support

- Report Issues: Open an issue on GitHub
- Questions: Check existing issues or start a discussion

---

##🎓 Happy thesis writing!

Remember: Your thesis is a marathon, not a sprint. Take your time, write clearly and ask for feedback early and often.
