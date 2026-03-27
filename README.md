# LR PDF Annotation Platform

Interactive Literature Review platform with 4-color coded PDF annotations and navigable sidebar.

## Features

- **4-color annotation system**: Method (blue), Conclusion (green), Innovation (orange), Limitation (red)
- **PDF Reader** with continuous scroll, zoom, retina DPI support
- **Right sidebar** with clickable annotations that navigate to exact pages
- **Literature Dashboard** with matrix table, citation graph, paper cards, knowledge gaps
- **Auto-extraction** script using PyMuPDF for section-by-section annotation
- **18-agent QA pipeline** for annotation quality assurance

## Architecture

```
literature_viewer.html    — Dashboard (Overview, Matrix, Citation Graph, Paper Cards, Gaps)
literature_reader.html    — PDF Reader (left sidebar, PDF viewer, right annotation panel)
annotation_data_final.json — Annotation data (21 papers, 4 categories each)
auto_extract_all.py       — Auto-extract annotations from PDFs using PyMuPDF
annotate_pdfs.py          — Generate color-highlighted annotated PDFs
```

## Color Legend

| Color | Category | Section Source |
|-------|----------|--------------|
| Blue | Method | Methodology section |
| Green | Conclusion | Results/Discussion |
| Orange | Innovation | Introduction (novelty claims) |
| Red | Limitation | Limitations section |

## Usage

```bash
# Start local server
cd /path/to/this/repo
python3 -m http.server 8765

# Open in browser
open http://localhost:8765/literature_reader.html   # PDF Reader
open http://localhost:8765/literature_viewer.html    # Dashboard
```

## Auto-Extract Annotations

```bash
# Place PDFs in Literature_Review/ directory
python3 auto_extract_all.py

# Generate color-highlighted PDFs
python3 annotate_pdfs.py
```

## QA Pipeline (18 agents)

Part of the `deep-research` skill with 4 QA agents:
1. **close_reading_agent** — Section-by-section full-text reading
2. **classification_verifier_agent** — Checks category correctness
3. **coverage_auditor_agent** — Checks for missed content
4. **precision_verifier_agent** — Verifies phrase existence in PDFs
5. **quality_gate_agent** — Final pass/fail decision

## Related

- DARe Flex Fund Project — Road Climate Resilience
- Gamma GLM rainfall-speed modelling on UK Strategic Road Network
