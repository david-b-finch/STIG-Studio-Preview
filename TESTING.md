# Experimental Preview — Testing Guide

**Build:** STIG Studio v0.7.2

**Status:** Experimental; not validated for operational use.

## Test data restrictions

Use only synthetic or fully sanitized CKL/CKLB data. Do not upload or attach
real assessment files, actual vulnerability results, infrastructure identifiers,
credentials, classified material, or controlled data to this public project.

## Quick smoke test

- [ ] Landing page loads and states experimental limitations.
- [ ] Application opens in Firefox or Chromium.
- [ ] Synthetic CKLB loads with two rules visible.
- [ ] Changing status, finding details, or comments marks the file as changed.
- [ ] Save Full CKLB downloads a file; reopening it shows edited data.
- [ ] Load the reference fixture and try Compare.
- [ ] Filtering produces the expected visible rules.
- [ ] Save Filtered CKLB and inspect the exported rule count and metadata.
- [ ] Combine synthetic inputs; compare result against expected rule inventory.
- [ ] For ZIP exports, extract externally and validate CRC/contents.

## Reference import smoke test

- [ ] Import `fixtures/synthetic-reference.zip` using **Import STIG Reference Archives**.
- [ ] One STIG opens directly with one rule marked Not Reviewed, without a selection dialog.
- [ ] Rule title reads "Example rule"; SRG ID is separate from the title.
- [ ] Enter a synthetic hostname using **Asset Info**.
- [ ] Save CKLB and reopen it; verify rule text, status, and asset information.
- [ ] Repeat with `fixtures/synthetic-reference.xml`.
- [ ] Import invalid ZIP/XML and verify a useful error without creating an assessment.

Stored/DEFLATE reference ZIPs and direct XCCDF 1.1/1.2 XML are supported within
resource limits. Tailored profiles, inheritance, automated/complex checks,
ZIP64/encrypted/multipart archives, and SCAP data-stream wrappers are unsupported.
No archive scripts, stylesheets, or supporting documents are executed.

## What to report

Provide:
1. Browser and version, operating system, and preview version.
2. What you attempted, starting from a new tab if possible.
3. Reproduction steps in order.
4. Expected behavior and observed behavior.
5. Whether the problem reproduces consistently.
6. A *synthetic* minimal sample file, if needed.

Do not submit screenshots containing real system names, findings, or identities.
GitHub Issues are public. Test files processed by this application are intended
to remain in the browser, but the preview has not been independently audited.

## High-priority investigations

1. Data preservation on CKLB import/edit/full save.
2. Lossy legacy CKL conversion and non-recalculated filtered export counts.
3. Incorrect comparison matches with duplicated rule identifiers in different STIGs.
4. Asset merge outcomes, conflict handling, metadata loss, and UUID relationships.
5. ZIP CRC, Unicode names, final filename uniqueness, and report consistency.

Do not characterize passing an informal smoke test as certification or security validation.
