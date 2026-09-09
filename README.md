# ARADURU File Format Test Corpus

**Live corpus:** https://teamaraduru-hub.github.io/araduru-file-format-test-corpus/

A small public corpus of **synthetic files** for testing file-format detection, structural validation, upload troubleshooting, and QA workflows.

No sample contains personal data, credentials, production documents, or user-uploaded content.

## What is included

| Format | Healthy sample | Original broken sample | Original broken sample demonstrates |
|---|---|---|---|
| XLSX | `healthy-basic.xlsx` | `broken-missing-workbook.xlsx` | Required `xl/workbook.xml` part removed |
| DOCX | `healthy-basic.docx` | `broken-missing-document-xml.docx` | Required `word/document.xml` part removed |
| PPTX | `healthy-basic.pptx` | `broken-missing-presentation-xml.pptx` | Required `ppt/presentation.xml` part removed |
| ZIP | `healthy-basic.zip` | `broken-truncated-central-directory.zip` | ZIP end / central-directory tail truncated |
| PDF | `healthy-basic.pdf` | `broken-truncated.pdf` | PDF trailer / end section truncated |

## v1.1 additional fixtures

| Format | Fixture | State | Demonstrates |
|---|---|---|---|
| XLSX | `renamed-extension.xlsx` | broken | Valid PDF content saved with an `.xlsx` extension |
| XLSX | `truncated-xlsx.xlsx` | broken | Truncated OOXML ZIP container |
| DOCX | `renamed-extension.docx` | broken | Valid PDF content saved with a `.docx` extension |
| DOCX | `truncated-docx.docx` | broken | Truncated OOXML ZIP container |
| PPTX | `renamed-extension.pptx` | broken | Valid PDF content saved with a `.pptx` extension |
| PPTX | `truncated-pptx.pptx` | broken | Truncated OOXML ZIP container |
| ZIP | `empty-archive.zip` | edge | Valid ZIP archive with zero entries |
| ZIP | `invalid-signature.zip` | broken | `.zip` extension without a ZIP signature |
| PDF | `wrong-extension.pdf` | broken | Valid ZIP content saved with a `.pdf` extension |
| PDF | `missing-eof.pdf` | broken | PDF missing its final `%%EOF` marker |

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

Broken files were created by deterministic structural changes such as removing a required OOXML part, truncating a container, removing a final marker, or deliberately mismatching the extension and actual file signature.

See [`manifest.json`](manifest.json) for SHA-256 hashes and the expected structural condition of every sample.

## License

The sample files and metadata in this repository are released under [CC0 1.0 Universal](LICENSE).

ARADURU website and product code are not included in this repository.
