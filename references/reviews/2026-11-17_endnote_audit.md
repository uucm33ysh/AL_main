# EndNote/Word audit — 2026-11-17

Files inspected: user-uploaded AL.enl and AL_1115.docx, both preserved unchanged. Native EndNote application open/update not tested.

AL.enl is a valid ZIP container with refs.MYD (9432 bytes) and refs.frm (10968 bytes); archive integrity check passed. EndNote-like internal reference records readable. This alone does not certify a complete portable/native library; use EndNote Compressed Library .enlx export for reliable transfer when needed.

Raw records confirm matching Park COLRAR and Zhao TDT titles/year and author strings.
- Park: authors/year/title present; raw record excerpt contains publisher LWW and ISSN but journal/volume/issue/pages/DOI not identifiable. Native record inspection needed; correct reference is Ann Surg2023;278(1):31–38,DOI10.1097/SLA.0000000000005788.
- Zhao: title/year/volume156/issue12/pages1151–1158 present. Author string ends at Liu,Jian (10 authors), with '%J JAMA surgery' appended. Uploaded original PDF has18 authors; check imported-field mapping and restore remaining8. DOI10.1001/jamasurg.2021.4568 not found literally in database.
- Title-normalized matching locates current manuscript references1–10,13,14. Riley2024 part2 (ref11) and Collins2024 TRIPOD+AI (ref12) not found by title or Riley/Collins/TRIPOD strings in refs.MYD. Treat as missing from this supplied file until checked in native EndNote.
- Word document has0 instrText,0 fldChar,0 fldSimple; no detectable EndNote CWYW fields. customXml bibliography source list empty and style APA, not evidence of active EndNote output style. Bibliography is plain14-item text; Park/Zhao not added to reference list and new Intro sentence not linked to them.
- Manually struck old Intro sentence remains intended deletion; do not treat old/new overlap as accidental duplication before inspecting strike format. Selected target sentence requires actual Insert Citation.

Recommended order: back up native library; correct/reimport2records (verified_Park_Zhao.ris); avoid retaining duplicates; add missing11/12; inspect complete metadata of existing14 (raw author strings elsewhere also show %J markers, suggesting broader import formatting issue). Insert citations into copied Word via EndNote Cite While You Write, then rebuild bibliography with selected journal style. Do not duplicate old plain-text bibliography. Current .docx is not automatically synchronized. Use .enlx with attachments if exporting a complete library.

Verified RIS contains two records only, from uploaded original PDFs; does not modify library. Inspect after import and replace/merge faulty duplicates before citing. Author lists include all10Park and18Zhao authors.
