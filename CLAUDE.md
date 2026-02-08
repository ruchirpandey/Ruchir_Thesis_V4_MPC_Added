# CLAUDE.md - AI Assistant Guide for Ruchir_Thesis Repository

## Repository Overview

This repository contains a LaTeX-based doctoral/master's thesis for **National Institute of Technology, Uttarakhand (NIT-UK)**. The thesis focuses on advanced control strategies for hybrid renewable energy systems, specifically:

**Thesis Topic:** Twin-Delayed Deep Deterministic Policy Gradient (TD3) Algorithm for Enhanced Power Optimization in Solar PV-Integrated DFIG Wind Energy Systems

**Author:** Ruchir Pandey
**Institution:** National Institute of Technology, Uttarakhand
**Year:** 2025

---

## Repository Structure

```
Ruchir_Thesis/
├── main.tex                    # Main LaTeX document (compilation entry point)
├── additionalPages/            # Front matter and auxiliary pages
│   ├── abstract.tex           # Thesis abstract
│   ├── acknowledgement.tex    # Acknowledgements
│   ├── abbreviations.tex      # List of abbreviations
│   ├── certificate.tex        # Institutional certificate
│   ├── declaration.tex        # Author's declaration
│   ├── dedication.tex         # Dedication page
│   ├── nomenclature.tex       # Nomenclature and symbols
│   ├── resume.tex             # Author's resume
│   └── titlePage.tex          # Title page
├── chapters/                   # Main thesis chapters
│   ├── chapter1/              # Introduction and Overview
│   ├── chapter2/              # Literature Review
│   ├── chapter3/              # System Configuration
│   ├── chapter4/              # Control Strategies
│   ├── chapter5/              # Modelling and Simulation
│   ├── chapter6/              # Experimental Validation Framework
│   ├── chapter7/              # Performance Evaluation and Results
│   ├── chapter8/              # Critical Discussion
│   └── chapter9/              # Conclusion and Future Scope
├── coverpage/                  # Front cover material
│   └── front.tex
├── images/                     # Image assets
│   ├── logo.jpg               # NIT-UK logo (used in headers)
│   └── logo.png
├── references/                 # Bibliography files
│   └── references.bib         # BibTeX bibliography database
└── tables/                     # Table files (LaTeX format)
    ├── chapter5_control_parameters.tex
    ├── chapter5_system_parameters.tex
    ├── chapter6_performanceComparison.tex
    ├── chapter6_componentEfficiencyAnalysis.tex
    └── chapter6_powerFactorAnalysis.tex
```

---

## Key Technical Details

### Research Domain

**Primary Focus:** Hybrid renewable energy systems combining:
- **DFIG (Doubly-Fed Induction Generator)** wind turbines
- **Solar PV systems** integrated into DC link
- **Deep Reinforcement Learning** control strategies (TD3, DDPG)

**Control Objectives:**
- Power optimization and maximum power extraction
- Grid stability (frequency ± 0.2 Hz, voltage ± 5%)
- Power quality (THD < 5%)
- Fault ride-through capability

**Key Algorithms:**
- Twin-Delayed Deep Deterministic Policy Gradient (TD3)
- Deep Deterministic Policy Gradient (DDPG)
- Model Predictive Control (MPC) baselines
- Traditional PI/PID controllers for comparison

---

## LaTeX Document Configuration

### Document Class and Key Packages

**Document Class:** `report` (14pt font)
**Page Layout:** A4 paper, 1-inch margins

**Critical Packages Used:**
- `fontspec` - Font configuration (requires XeLaTeX or LuaLaTeX)
- `polyglossia` - Multi-language support (English and Hindi)
- `fancyhdr` - Custom headers and footers
- `graphicx` - Image handling
- `amsmath` - Mathematical typesetting
- `titlesec`, `titling` - Custom chapter/section formatting

### Font Configuration

**Primary Font:** Times New Roman (via `fontspec`)
**Special Fonts:**
- URW Bookman - Used for headings (`\bookmanfont`)
- Noto Sans Devanagari - Hindi text support (`\hindifont`)
- Liberation Sans - News Gothic BT alternative (`\newsgothicfont`)

**IMPORTANT:** This document **requires XeLaTeX or LuaLaTeX** for compilation (not pdfLaTeX) due to `fontspec` and custom font usage.

### Custom Commands and Styles

#### Chapter Formatting
- Custom command: `\customchapter{number}{title}` - Creates styled chapter headings
- Chapter numbering: `A.1`, `A.2`, etc.
- Section numbering: `A.1.1`, `A.2.3`, etc.

#### Page Styles
Each section has custom page styles defined in `main.tex`:
- `certificate` - Institutional header with logo and bilingual text
- `abstract`, `tocstyle`, `listoffigures`, `listoftables` - Front matter styles
- `chapterA1` through `chapterA9` - Chapter-specific headers

#### Color Definitions
```latex
saffron      RGB(255,153,51)
nitblue      RGB(0,0,255)
royalblue    RGB(0,51,204)
wordfade     RGB(128,128,128)  # Grayed text for page numbers/headers
```

### Page Numbering
- **Front Matter:** Roman numerals (i, ii, iii...)
- **Main Content:** Arabic numerals starting from 1

---

## Development Workflow

### Building the Document

**Compilation Requirements:**
1. **LaTeX Engine:** XeLaTeX or LuaLaTeX (NOT pdfLaTeX)
2. **Fonts Required:**
   - Times New Roman
   - URW Bookman
   - Noto Sans Devanagari
   - Liberation Sans

**Build Commands:**
```bash
# Single compilation
xelatex main.tex

# Full build with bibliography
xelatex main.tex
bibtex main
xelatex main.tex
xelatex main.tex
```

**Alternative (LuaLaTeX):**
```bash
lualatex main.tex
bibtex main
lualatex main.tex
lualatex main.tex
```

### File Organization Conventions

#### Chapter Files
- Each chapter is stored in `chapters/chapterN/`
- Main file named descriptively: `introduction.tex`, `literature_review.tex`, etc.
- Chapters are included using `\input{chapters/chapterN/filename}`

#### Table Files
- Stored in `tables/` directory
- Named with chapter prefix: `chapter5_control_parameters.tex`
- Tables are self-contained LaTeX fragments

#### Image Files
- Stored in `images/` directory
- Referenced in LaTeX: `\includegraphics{images/filename.jpg}`
- Formats: JPG, PNG primarily

#### Bibliography
- BibTeX format in `references/references.bib`
- Style: IEEEtran (IEEE Transactions format)
- Citations use standard BibTeX keys

---

## Content Guidelines for AI Assistants
## Do not push/commit any new or existing .md file in to repo

### When Editing LaTeX Content

1. **Preserve Formatting:**
   - Maintain existing indentation and spacing
   - Keep custom commands like `\customchapter{}` intact
   - Preserve page style assignments (`\thispagestyle{}`, `\pagestyle{}`)

2. **Mathematical Content:**
   - Use proper LaTeX math environments: `\( \)`, `\[ \]`, `equation`, `align`
   - Follow IEEE formatting for equations
   - Number important equations for reference

3. **Citations:**
   - Use `\cite{key}` for references
   - Add new entries to `references/references.bib` in BibTeX format
   - Follow IEEE citation style

4. **Technical Terminology:**
   - DFIG (Doubly-Fed Induction Generator)
   - TD3 (Twin-Delayed Deep Deterministic Policy Gradient)
   - DDPG (Deep Deterministic Policy Gradient)
   - MPPT (Maximum Power Point Tracking)
   - THD (Total Harmonic Distortion)
   - PV (Photovoltaic)

### Chapter-Specific Content

**Chapter 1:** Introduction - Background, motivation, renewable energy challenges
**Chapter 2:** Literature Review - State-of-the-art in hybrid systems and control
**Chapter 3:** System Configuration - DFIG-PV architecture and components
**Chapter 4:** Control Strategies - TD3, DDPG, and baseline control methods
**Chapter 5:** Modelling and Simulation - System models and simulation setup
**Chapter 6:** Experimental Validation - Hardware-in-loop or experimental setup
**Chapter 7:** Performance Evaluation - Results and comparative analysis
**Chapter 8:** Critical Discussion - Analysis, limitations, insights
**Chapter 9:** Conclusion and Future Scope - Summary and future directions

### Writing Style Guidelines

1. **Academic Tone:** Formal, objective, technically precise
2. **Citation Heavy:** Every claim should be supported by references
3. **Critical Analysis:** Don't just describe—analyze and evaluate
4. **Technical Depth:** Include mathematical formulations, equations, and detailed explanations
5. **IEEE Standards:** Follow IEEE style for figures, tables, and references

---

## Common Tasks and Patterns

### Adding a New Figure

```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{images/filename.png}
    \caption{Descriptive caption explaining the figure}
    \label{fig:descriptive_label}
\end{figure}
```

### Adding a New Table

```latex
\begin{table}[htbp]
    \centering
    \caption{Descriptive table caption}
    \label{tab:descriptive_label}
    \begin{tabular}{|l|c|c|}
        \hline
        \textbf{Parameter} & \textbf{Value} & \textbf{Unit} \\
        \hline
        Row 1 & Data 1 & Unit 1 \\
        Row 2 & Data 2 & Unit 2 \\
        \hline
    \end{tabular}
\end{table}
```

### Adding References

Add to `references/references.bib`:
```bibtex
@article{AuthorYear,
  author = {Last, First and Last2, First2},
  title = {Article Title},
  journal = {Journal Name},
  year = {2024},
  volume = {XX},
  number = {X},
  pages = {XX--XX}
}
```

Then cite in text: `\cite{AuthorYear}`

### Cross-Referencing

```latex
% Define label
\label{chap:introduction}
\label{sec:methodology}
\label{eq:power_equation}
\label{fig:system_diagram}
\label{tab:parameters}

% Reference
Chapter~\ref{chap:introduction}
Section~\ref{sec:methodology}
Equation~\ref{eq:power_equation}
Figure~\ref{fig:system_diagram}
Table~\ref{tab:parameters}
```

---

## Git Workflow

### Current Branch
- Working branch: `claude/claude-md-mi23we4y95qlis7s-01FJgpTJ48kE2Rjh9v8zAvkV`
- All development happens on Claude branches
- Push changes with: `git push -u origin <branch-name>`

### Commit Message Guidelines
- Use descriptive, concise messages
- Example: "Add TD3 algorithm description to Chapter 4"
- Example: "Update system parameters table in Chapter 5"
- Example: "Fix citation formatting in literature review"

### Files to Track
**Include in Git:**
- All `.tex` files
- `.bib` files
- Source images (JPG, PNG)
- Tables

**Exclude from Git (typical):**
- `.aux`, `.log`, `.toc`, `.lof`, `.lot` - LaTeX auxiliary files
- `.bbl`, `.blg` - BibTeX auxiliary files
- `.pdf` - Compiled output (unless explicitly tracked)
- `.synctex.gz` - SyncTeX files

---

## Quality Checklist for Edits

Before committing changes, verify:

- [ ] LaTeX syntax is correct (no compilation errors)
- [ ] All citations have corresponding BibTeX entries
- [ ] All figures/tables are referenced in text
- [ ] Cross-references use `\ref{}` not hard-coded numbers
- [ ] Mathematical notation is consistent
- [ ] Custom commands are used appropriately
- [ ] Page styles are assigned correctly for new sections
- [ ] Font commands are not mixed improperly
- [ ] Bilingual text (Hindi) uses `\hindifont` family
- [ ] Tables and figures have descriptive captions
- [ ] Equations are numbered if referenced later

---

## Special Considerations

### Bilingual Content
- Institution name appears in both Hindi and English on certificate page
- Hindi text requires Devanagari font support
- Use `{\hindifont text}` for Hindi content

### Custom Formatting Elements
- Chapter headings use custom `\customchapter{}` command
- Don't manually add "CHAPTER - X" text; the command handles it
- Maintain consistency with existing chapter formatting

### Bibliography Management
- Currently uses inline `thebibliography` environment in `main.tex`
- Also configured to use BibTeX with `references.bib`
- IEEE citation style is standard for this field
- Maintain IEEE abbreviations (e.g., "Proc." for Proceedings, "Trans." for Transactions)

### Images and Figures
- NIT-UK logo (`logo.jpg`) is used in header—do not modify
- All technical diagrams should be publication-quality
- Vector formats (PDF, SVG converted to PDF) preferred for diagrams
- Raster formats acceptable for photographs and screenshots

---

## Troubleshooting Common Issues

### Compilation Errors

**Error: "fontspec error: The fontspec package requires..."**
→ Solution: Use XeLaTeX or LuaLaTeX instead of pdfLaTeX

**Error: "Font 'Times New Roman' cannot be found"**
→ Solution: Install Times New Roman font on your system

**Error: "! Undefined control sequence. \hindifont"**
→ Solution: Ensure Noto Sans Devanagari font is installed

**Error: "Citation undefined"**
→ Solution: Run BibTeX and compile multiple times (see Build Commands)

### Content Issues

**Problem: Page numbers not appearing correctly**
→ Check page style assignments (`\pagestyle{}` commands)

**Problem: Chapter numbering is wrong**
→ Don't use `\chapter{}`—use `\customchapter{}` instead

**Problem: References not showing up**
→ Ensure entry exists in `references.bib` and cite key matches

---

## Research Context and Domain Knowledge

### Hybrid Renewable Energy Systems

This thesis addresses real-world challenges in modern power grids:

1. **Intermittency Problem:** Wind and solar are variable and unpredictable
2. **Grid Stability:** Renewables reduce system inertia, affecting frequency/voltage
3. **Power Quality:** Harmonics and transients from converters
4. **Economic Optimization:** Maximizing energy extraction while maintaining stability

### Control Hierarchy

1. **Primary Control:** Fast response (milliseconds) - voltage/frequency regulation
2. **Secondary Control:** Medium response (seconds) - power sharing coordination
3. **Tertiary Control:** Slow response (minutes) - economic optimization

### Why Deep Reinforcement Learning?

Traditional PI/PID controllers struggle with:
- Nonlinear, coupled dynamics of DFIG-PV systems
- Rapidly changing operating conditions
- Multi-objective optimization (power, stability, efficiency)

TD3 and DDPG offer:
- Model-free learning (no need for exact system model)
- Continuous action spaces (direct control signals)
- Adaptive behavior learned from experience
- Superior performance under uncertainty

---

## Publications Related to This Work

### Accepted/Under Review:
1. R. Pandey et al., "Twin-delayed deep deterministic policy gradient for enhanced power optimization in solar PV-integrated DFIG wind energy systems," *Scientific Reports*, 2025. (Accepted)

2. R. Pandey et al., "DDPG algorithm for power optimization and control of solar PV-integrated DFIG wind energy systems," 2025. (Under Review)

### Conference:
1. R. Pandey et al., "Deep reinforcement learning for hybrid renewable energy systems," *Proc. IEEE Power & Energy Society General Meeting*, 2024.

---

## AI Assistant Best Practices

### When Asked to Edit Content:

1. **Understand Context:** Read surrounding sections to maintain consistency
2. **Preserve Citations:** Keep all `\cite{}` references intact
3. **Match Style:** Follow existing writing style and technical depth
4. **Verify Technical Accuracy:** Ensure electrical/control engineering concepts are correct
5. **Check Cross-References:** Update related sections if making significant changes

### When Adding New Content:

1. **Research First:** Understand the topic in the context of power systems and control
2. **Cite Sources:** Add appropriate citations for claims
3. **Use Domain Vocabulary:** Employ correct technical terminology
4. **Follow Structure:** Match the organizational pattern of existing chapters
5. **Include Math:** Provide mathematical formulations where appropriate

### When Debugging:

1. **Test Compilation:** Always verify LaTeX compiles without errors
2. **Check References:** Ensure all `\ref{}` and `\cite{}` resolve correctly
3. **Validate Formatting:** Preview output to verify formatting matches expectations
4. **Review Logs:** Check `.log` files for warnings about missing references

---

## Additional Resources

### LaTeX Documentation
- Overleaf LaTeX documentation: https://www.overleaf.com/learn
- XeLaTeX guide: https://www.overleaf.com/learn/latex/XeLaTeX
- BibTeX guide: https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex

### Domain Resources
- IEEE Xplore (for reference papers): https://ieeexplore.ieee.org/
- Renewable energy journals: IEEE Trans. Sustainable Energy, Renewable Energy, etc.
- Control systems: IEEE Trans. Control Systems Technology

### Institutional Guidelines
- NIT Uttarakhand thesis format requirements (if available)
- IEEE citation style guide: https://ieee-dataport.org/sites/default/files/analysis/27/IEEE%20Citation%20Guidelines.pdf

---

## Version History

- **2025-11-16:** Initial CLAUDE.md creation - comprehensive repository documentation
- **2025-01-XX:** Initial Overleaf import (commit: 8e154ad)

---

## Contact and Contribution

**Repository Owner:** Ruchir Pandey
**Institution:** National Institute of Technology, Uttarakhand
**Email:** Available in thesis front matter

For questions about content, formatting, or technical details, refer to:
1. This CLAUDE.md file
2. LaTeX comments in `main.tex`
3. Institutional thesis guidelines
4. IEEE formatting standards

---

*Last Updated: November 16, 2025*
*Document Version: 1.0*
