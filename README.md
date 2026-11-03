# AI Governance Census of US Colleges and Universities

A stratified census of the documents through which US colleges and universities govern artificial intelligence: policies, honor code clauses, syllabus requirements, teaching and student guidance, IT and data rules, procurement and licensing announcements, committee reports, and strategic initiatives. The sample of 334 institutions is drawn from the 2025 Carnegie Classifications.

Status: version 0.4 (2 November 2026) releases the inventory for 70 institutions, the ten pilot institutions and the first sixty R1 institutions in alphabetical order (906 document rows). Of these, 607 rows were verified against the live document or a downloaded copy, 110 record a body or policy announced without a published document, and each remaining row states why it was not verified. The full census is in progress and releases in batches. Version 1.0 will add specification-scale scores from the coding pass.

## Contents

| Path | What it holds |
| --- | --- |
| `data/sample_drawn_institutions.csv` | The 334 drawn institutions, with stratum, draw rule, UNITID, and Carnegie attributes |
| `data/inventory.csv` | One row per document for every institution searched so far, all fields of the per-document record, with a Batch column (Pilot, R1 batch 1, R1 batch 2, R1 batch 3) |
| `data/institution_log.csv` | One row per institution searched: search date, result, document count, recorded absences |
| `data/pilot_inventory.csv`, `data/pilot_institution_log.csv` | The October 2026 pilot subset, kept as released |
| `data/pilot_protocol_findings.csv` | Changes to the protocol the pilot produced, with their status |
| `scripts/build_frame.py` | Builds the sampling frame and reproduces every random draw from the 2025 Carnegie Public Data File |
| `docs/` | Protocol and codebook (in preparation) |

## Design in brief

The frame holds 1,446 public and private nonprofit institutions in the 50 states, DC, and Puerto Rico. It excludes private for-profit institutions, associate-focus institutions, R1 and R2 medical schools and health science centers, other Special Focus categories, and territories other than Puerto Rico. Random draws use seed 20261023.

| Stratum | Population | Drawn | Draw rule |
| --- | --- | --- | --- |
| 1 R1 | 177 | 177 | Census |
| 2 R2 | 120 | 40 | Random, proportional to control |
| 3 Doctoral focus, no R1 or R2 designation | 219 | 25 | Random, proportional to control |
| 4 Master's focus | 336 | 40 | Random, proportional to control |
| 5 Baccalaureate focus | 564 | 30 | Random, proportional to control |
| 6 Puerto Rico | 30 | 10 | Both R2 institutions plus a random 8 |
| 7 Primarily online, Large or Very Large | 7 | 7 | Purposive, all |
| 8 Existing corpus, in frame, not drawn | 3 | 3 | Purposive carry-over, reported separately |

A document enters the inventory when it passes four tests: institutional authorship, a governance function, AI as its object (the use of AI tools by students, faculty, or staff, whatever term the document uses), and public availability. Each document is coded Standalone or Embedded. Institution-level results are reported as three nested counts, always named: institutions with any qualifying document, institutions with at least one standalone document, and institutions with a formal policy that names AI, with system-only cases reported separately.

Only rows with the status Verified enter reported figures. Other statuses (Found, Flag, Located behind login, Not reachable, Dead link on recheck) remain visible in the data so a reuser sees what has and has not been read.

## Reproducing the frame

```
pip install openpyxl
python scripts/build_frame.py 2025-Public-Data-File.xlsx frame.xlsx
```

The Carnegie Public Data File is published by the American Council on Education and is not redistributed here.

## Citation

Cite the archived release through its Zenodo DOI. The concept DOI https://doi.org/10.5281/zenodo.23887259 always resolves to the latest version; version 0.3 is https://doi.org/10.5281/zenodo.23893601. `CITATION.cff` carries the current citation, and each later version receives its own DOI.

## License

Data, documentation, and code are released under the Creative Commons Attribution 4.0 International License (CC BY 4.0). Quoted passages in the Key Framing Language field remain the work of their issuing institutions and are reproduced in short excerpt for the purposes of research and criticism.
