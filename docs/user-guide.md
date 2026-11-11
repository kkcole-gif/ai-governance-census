# User Guide: AI Governance Census of US Colleges and Universities

Revised November 11, 2026. This guide explains what the dataset records, how to read it, and how to cite or correct it. A separate methods page documents the sampling frame, the search protocol, and the coding procedure.

## 1. What the census records

The census records the documents through which US colleges and universities govern the use of artificial intelligence by students, faculty, and staff. The sample of 334 institutions comes from the 2025 Carnegie Classifications (seed 20261023). Every R1 institution is included, and the other strata are drawn at random (see the README for the stratum table).

The unit of record is the document, and documents nest within institutions. One institution carries anywhere from no documents to more than twenty, because AI rules at a single university sit in provost memos, honor codes, teaching center pages, IT standards, library guides, license announcements, and school policies, and these documents often disagree with one another. The dataset keeps every such document as a separate row so a reader sees where each rule lives, who issued it, and whom it addresses.

## 2. What counts as a document

A document enters the inventory when it passes all four tests.

1. Institutional authorship. A university office, committee, senate, school, library, teaching center, IT unit, student conduct office, student government, or system office issued it. An individual instructor's syllabus or blog does not qualify. The issuing office is read from the document itself, never from the hosting domain.
2. Governance function. The document tells readers what to do, what is permitted or required, or what the institution has decided. FAQs, syllabus statement templates, decision trees, and task force reports with recommendations qualify. Webinars and research publications do not. An institution's own news item enters the inventory as a boundary case, and is coded, where it carries quoted institutional language. A news item without such language is excluded.
3. AI as object. The document addresses the use of AI tools, whatever term it uses (generative AI, artificial intelligence, a named product). An integrity code with no mention of AI fails this test, and the institution log records it as an absence, because the absence is itself a finding.
4. Public availability. The document is reachable without a login. Documents identified behind a login are recorded with the status Located behind login and do not enter reported figures.

Each document is also coded Standalone (AI is its principal subject) or Embedded (an AI clause inside a general instrument such as an honor code, catalog policy, handbook, or acceptable use policy).

## 3. Status: what has and has not been read

Every row carries one status. Only rows marked Verified enter reported figures.

| Status | Meaning |
| --- | --- |
| Verified | Title, issuing office, date, and quoted passage confirmed against the source document. |
| Found | The document was located and read. It awaits verification. |
| Flag | The document was located, but one of the four tests or a field value is in doubt. The Notes field states the doubt. |
| Located behind login | The document exists, but reading it requires institutional credentials. |
| Not reachable | The document exists, but the site blocked reading it. |
| Dead link on recheck | The document was verified once and was unreachable on a later check. The quoted passage and coding stand as recorded. |
| Excluded (news) | A news item with no quoted institutional language. It stays visible and never enters counts. |
| Announced, no document | A body, policy, or guidance an institution announces or refers to without a public text: a committee named without a charge or report, a policy described as in development or forthcoming, norms promised and not published. Recorded as its own row so deferral is countable. It never enters document counts. |
| Excluded (presentation; fails governance test) | A document read in full and found to state no rule, kept for provenance. It never enters counts. |
| Excluded (merged into another row) | A document the institution has withdrawn or replaced, whose content is carried by the row its Notes name. It never enters counts and stays for provenance. |

Unverified rows stay in the data so a reader sees what has been searched and what remains open.

## 4. Institution-level counts

Institution figures are reported as three nested counts, always named:

1. Institutions with any qualifying document.
2. Institutions with at least one standalone document.
3. Institutions with a formal policy or regulation naming AI.

Institutions governed only by a system-office document (a state system policy with no campus instrument) are counted separately within the third count, because a system mandate and a campus policy are different institutional facts.

The institution log records, for every drawn institution, the search date, the result (Documents found, No AI governance document located, Announced with no document, or Located but not retrievable), and the absences checked. An institution with no qualifying document stays in the data with its log entry.

Each institution in the log also carries a heading line (the Profile field) and a summary (the Summary field), written for readers outside the field. The heading line lists, from the coded fields, the highest-order governing document, the status of the integrity code, the vendors the documents name, and the number of contradictions. In three to five sentences, the summary states what governs AI at the institution and which office issues it, whether the integrity code names AI, any contradiction, any body announced without a document, and what was not read. The full search record, which lists the pages searched, read, set aside, and not reached, appears behind the Full search record toggle on the Institutions tab and in the Absences and access notes field of the log.

## 5. Fields in the inventory

| Field | What it records |
| --- | --- |
| Batch | The release group holding the row: Pilot, R1 batch 1, R1 batch 2, and so on. R1 batches follow the alphabetical order of the R1 list. |
| UNITID | IPEDS identifier from the Carnegie file |
| Institution | Carnegie name of the institution |
| Stratum | Sampling stratum (1 R1 census through 8 existing corpus), as listed in the README |
| Control | Public or private nonprofit, from the Carnegie file |
| Research designation | R1, R2, or None, from the Carnegie file |
| State | State, District of Columbia, or Puerto Rico |
| Document title | Title as the document gives it. Where the document gives none, a descriptive title appears in parentheses. |
| Issuing office | The office named in the document as its author, from a controlled list, with Other (named) for an office outside the list. The hosting web domain never decides this field. |
| Document type | One of twelve types, from 1 Executive communication to 12 Strategic initiative |
| Boundary case | Yes where the document sits at the edge of one of the four tests in section 2, with the reason in Notes. A few cells state the reason in place of Yes. |
| Standalone or embedded | See section 2 |
| Date issued | The earliest date the document carries, written as year, year and month, or full date. Undated where the document carries no date. |
| Date basis | The source of Date issued. Stated means printed in the document. File path means a year or month in the web address or file name. Page metadata means the last-modified date of the web page. Inferred means reasoned from the content, with the reasoning in Notes. Undated means no source exists. A parenthesis adds detail, as in stated (effective). |
| Date last revised | The most recent revision or update date the document states. A blank cell means the document states no revision date. Not recorded means the field was left unfilled during the search and remains open. A few cells give a scheduled review date or a handbook edition, as worded. |
| Wave | Wave 1 for a document issued between spring and fall 2023, Wave 2 for a document issued or revised from 2024 onward, Both for a 2023 document revised later, and Undetermined where the dates do not settle the question |
| Post-July-2026 | Yes where the document was issued or revised after 31 July 2026, No where its dates fall earlier, blank where its dates do not settle the question. A parenthesis gives the basis where it differs from Date basis. |
| AI term used | The terms the document itself uses for AI (generative AI, artificial intelligence, a named product), recorded as written |
| Contradiction with another document | A conflict between this document and another at the same institution, with the other document named and the conflict stated |
| URL | Address of the document at retrieval |
| Format | HTML, PDF, DOCX, PPTX, Google Doc, and so on |
| Language | Language of the document |
| Key Framing Language | One sentence quoted word for word from the document, chosen as the sentence stating its governing position, in double quotation marks. An ellipsis marks omitted words. Where the row holds no quotation, the cell gives the reason. Not applicable (no text) marks an announced body or policy without a published document. Not applicable (not read) marks a document behind a login or blocked from reading. Not recorded (no quotation taken) marks a document read without a sentence quoted. |
| Quote source | How the quoted sentence was checked against its source, with the date of the check. Browser text, verified means matched against the live page in a web browser. PDF, Word, or slide text extracted in browser means matched against text drawn from the file. Page text from a manual download means matched against a copy downloaded locally where browser reading was blocked. Captured and verified means the row held no quotation, so one was taken from the page at verification. Original quotation superseded means the sentence first recorded was replaced by a sentence confirmed in the source, and Notes keeps the earlier wording. Fetch (verify) means the quotation was taken by automated page fetch and has not yet been checked. A blank cell means the row holds no quotation. |
| Named frameworks | Frameworks, laws, or standards the document cites |
| Vendor named | AI products or vendors the document names |
| Retrieval date | Date the document was first read. The date of verification appears in Quote source. |
| Status | See section 3 |
| Found by | The step of the search procedure locating the document. Step 2 is a web search with one of seven strings: 1 or a, generative AI policy. 2 or b, artificial intelligence guidance faculty. 3 or c, ChatGPT academic integrity. 4 or d, AI syllabus statement. 5 or e, acceptable use artificial intelligence. 6 or f, vendor license terms (ChatGPT Edu, Copilot, Gemini, Claude). g, the institution name with AI policy, unrestricted by domain. The pilot and R1 batch 1 number the strings and later batches letter them, with the same number and letter naming the same search. Step 3 names the office page fetched. Step 4 marks a search of a system office. Follow-up, Manual recheck, and similar entries mark a document added after the batch search, and Notes give the route. |
| Policy stance (open) | A one-line description, written for the census, of what the document permits, requires, prohibits, or delegates. It paraphrases the document and carries no interpretive coding, which runs as a separate pass. |
| Notes | Section locators for embedded clauses, the reason for a Flag or a boundary case, the basis of an inferred date, translation choices, and the verification history. A vertical bar separates entries, which run in the order written. |

The Contradiction field deserves particular attention. Universities often state different default rules for AI use across their own documents (a provost policy permitting use by default while a school catalog prohibits it, for example). The census records each such conflict at the row level so the conflicts are countable. Each contradiction line names the other document and states what each says. Where one document replaces or updates another at the same campus, the census records a version note in the full search record and counts no contradiction.

## 6. The specification scale

Verified documents are scored on three levels of AI literacy.

- Conceptual: how far the document describes the system itself (what AI is, how training and output relate, error properties).
- Structural: how far it specifies conditions in place before any user arrives (training data, ownership and vendor control, license terms, retention, whether user data trains the model, labor and environmental costs).
- Operative: how far it equips a reader to decide, in a situation, whether to act, withhold, or refuse, and to answer for the decision.

Each level receives one of three ratings.

- High: the document specifies the level's content in detail a reader is able to use.
- Medium: the document names the level or gestures at it.
- Low: the level is absent from the document.

On the operative level, High requires a pattern, meaning at least two rules about whether to use, withhold, or refuse AI, each with a reason stated in the document's own prose. A document telling its reader someone else decides (an instructor, an approval office) stays at Medium, as does a document whose reasons appear only inside sample syllabus statements. Each scored document also records its primary and secondary addressee (Students, Instructors, Staff, Administrators and units, or Institution-wide) and its grounds (Compliance, Learning, Accuracy or access, or Both). The [codebook](https://github.com/kkcole-gif/ai-governance-census/blob/main/docs/codebook.md) gives the full rules.

Scores are absent from the released data at this version. They enter the inventory in a later release, once scoring of the released batches is complete.

## 7. How to cite

Cite the version you used through its Zenodo DOI. Each release receives its own DOI, and the concept DOI 10.5281/zenodo.23887259 always resolves to the latest version. The CITATION.cff file gives the current citation in machine-readable form.

The CC BY 4.0 license covers the compilation, coding, and documentation. Quoted passages remain the work of their issuing institutions and appear in short excerpt for research and criticism.

## 8. Corrections and missing documents

Institutions revise their AI documents often. To report a correction, a newer version, a broken link, or a document the census missed, use the [reporting form](https://docs.google.com/forms/d/e/1FAIpQLSfK8B4oqRNt_kNkRTaDm8G2Kt-vkDXZmajS4jcLUX75kF_O6w/viewform). For other questions, write to kkcole2@ncsu.edu. Each report is checked against the source document before the data changes, and changes appear in the next release.
