# ARADURU File Format Test Corpus
**Live corpus:** https://teamaraduru-hub.github.io/araduru-file-format-test-corpus/
A small public corpus of **synthetic files** for testing file-format detection, structural validation, upload troubleshooting, and QA workflows.

No sample contains personal data, credentials, production documents, or user-uploaded content.

## What is included

| Format | Healthy sample | Broken sample | Broken sample demonstrates |
|---|---|---|---|
| XLSX | `healthy-basic.xlsx` | `broken-missing-workbook.xlsx` | Required `xl/workbook.xml` part removed |
| DOCX | `healthy-basic.docx` | `broken-missing-document-xml.docx` | Required `word/document.xml` part removed |
| PPTX | `healthy-basic.pptx` | `broken-missing-presentation-xml.pptx` | Required `ppt/presentation.xml` part removed |
| ZIP | `healthy-basic.zip` | `broken-truncated-central-directory.zip` | ZIP end / central-directory tail truncated |
| PDF | `healthy-basic.pdf` | `broken-truncated.pdf` | PDF trailer / end section truncated |

## Why this corpus exists

File-upload and file-open failures are often hard to reproduce. These samples give developers, QA teams, technical writers, and support engineers small deterministic files that can be used to test file inspection workflows without sharing real user documents.

## ARADURU tools

- [File Check](https://araduru.com/file-check/) — inspect a file before deciding what to fix.
- [Upload Check](https://araduru.com/upload-check/) — check file-side upload problems before retrying.
- [Upload Problems](https://araduru.com/upload-problems/) — troubleshoot common upload failures.
- [All Tools](https://araduru.com/tools/) — browse ARADURU file troubleshooting tools.

## Safety and provenance

All files in this repository were generated specifically for this public corpus.

They are **not copied from user uploads or private production data**.

Broken files were created by deterministic structural changes such as removing a required OOXML part or truncating the end of a container.

See [`manifest.json`](manifest.json) for SHA-256 hashes and the expected structural condition of every sample.

## License

The sample files and metadata in this repository are released under [CC0 1.0 Universal](LICENSE).

ARADURU website and product code are not included in this repository.
