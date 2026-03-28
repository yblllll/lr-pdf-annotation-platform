# Academic Dashboard — LR PDF Annotation Platform

Interactive Academic Dashboard for literature review management, PDF annotation, journal rankings, research pipeline tracking, and paper editing.

## Quick Start

```bash
cd /path/to/this/repo
python3 run.py
```

This starts a local HTTP server and opens the dashboard at `http://localhost:8765/literature_viewer.html`.

**Alternative** (manual):
```bash
python3 -m http.server 8765
# Then open http://localhost:8765/literature_viewer.html
```

## Features — 10 Interactive Tabs

| Tab | Description |
|-----|-------------|
| **Overview** | Summary statistics: paper count, year range, theme distribution |
| **Matrix Table** | Sortable/filterable table of all papers with methods, findings, citations, IF |
| **Citation Graph** | D3 force-directed network visualization, colored by research theme |
| **Citation Chain** | How papers build on each other — from foundational to your contribution |
| **Paper Cards** | Expandable cards with 4-color aspect badges (Method/Conclusion/Innovation/Limitation) |
| **Knowledge Gaps** | Theme coverage analysis and identified research gaps |
| **PDF Reader** | Full-text PDF viewer with 4-color annotation sidebar and page navigation |
| **Research Pipeline** | 9-stage research workflow tracker (LR, Data, Estimate, Map, Explain, Network, Paper, Review) |
| **Journal Rankings** | 32 transport/climate journals with IF, tier, relevance filters, and target marking |
| **Paper** | LaTeX editor with live preview, margin notes for placeholders, and AI writing assistant |

## PDF Annotation System

### 4-Color Coding
| Color | Category | Typical Source Section |
|-------|----------|----------------------|
| Blue | **Method** | Methodology section (pages 5-15) |
| Green | **Conclusion** | Results/Discussion section |
| Orange | **Innovation** | Introduction (novelty claims) |
| Red | **Limitation** | Limitations/Discussion section |

### Annotation Files
- `annotation_data_final.json` — Annotation data for 21+ papers
- `Literature_Review/` — Directory containing original and annotated PDFs
- `critic_becker2026.json` — AI agent team audit data

## File Structure

```
literature_viewer.html      # Main Academic Dashboard (all 10 tabs)
literature_reader.html      # Standalone PDF Reader (embedded via iframe)
annotation_data_final.json  # Paper annotation data
d3.v7.min.js               # D3.js for citation graph visualization
run.py                     # One-command launcher
annotate_pdfs.py           # Generate color-highlighted annotated PDFs
auto_extract_all.py        # Auto-extract annotations from PDFs
literature_matrix.csv      # Literature matrix data
literature_analysis.md     # Literature analysis report
skill/                     # Claude Code skill definition
  SKILL.md                 # Skill metadata and rules
  agents/                  # QA agent definitions
figures/                   # Generated figures
Literature_Review/         # PDF directory (add your PDFs here)
  Paper_Name.pdf           # Original PDFs
  Paper_Name_annotated.pdf # Color-highlighted PDFs
```

## Journal Rankings

32 journals across transport, climate, and resilience research:

- **Target journals** marked with a star: Transportation Research Part D (IF 8.62) and Journal of Transport Geography (IF 6.3)
- Filter by **tier** (Top/High/Good/Emerging), **relevance** (High/Medium/Low), or **search**
- Data sourced from JCR 2024, ABS 2021, ABDC 2022

## Paper Editor

Integrated LaTeX editing environment:

- **Left panel (45%)**: Monospace LaTeX editor with syntax tools (bold, italic, cite, ref)
- **Middle panel (40%)**: Live preview rendering LaTeX as formatted HTML
- **Right panel (15%)**: Margin notes showing what placeholders need to be filled
- **AI Writing Assistant**: Select text, get academic improvement suggestions with Accept/Ignore buttons
- Load any `.tex` file or use the embedded draft

## AI Agent Team QA

Uses oh-my-claudecode agent teams for quality assurance:
- **Critic agent** — Reviews annotation accuracy and coverage
- **Verifier agent** — Validates dashboard functionality and data integrity
- **Close reading agent** — Deep analysis of paper content for precise annotations
- **Precision verifier** — Ensures annotation phrases match exact PDF text

## Requirements

- Python 3.7+ (for the local HTTP server)
- Modern browser (Chrome, Firefox, Safari, Edge)
- Optional: `pymupdf` (`pip install pymupdf`) for PDF annotation generation

## License

Part of the DARe project, University of Cambridge, Department of Land Economy.
