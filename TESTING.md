# Experimental Preview — Testing Guide

**Build:** STIG Studio v0.7.7; v0.7.6 remains available for comparison.

**Status:** Experimental; not validated for operational use.

## Test data restrictions

Use only synthetic or fully sanitized CKL/CKLB data. Do not upload or attach
real assessment files, actual vulnerability results, infrastructure identifiers,
credentials, classified material, or controlled data to this public project.

## Version comparison and offline testing

- [ ] Use **Open v0.7.7** and **Open previous v0.7.6** on the landing page.
- [ ] Use each adjacent **Download** button; verify it downloads the named HTML
      rather than navigating away from the landing page.
- [ ] Disconnect from the network and open the downloaded HTML directly.
- [ ] Open synthetic CKLB/reference inputs, edit, save, and reopen offline.
- [ ] Compare the same synthetic workflow in both versions; record the version.

## New in 0.7.7: carry previous notes forward

- [ ] Open demo **03 Firefox V6R9** as the working checklist and compare it with
      demo **01 Firefox V6R4** as Reference. Verify the current/new release stays
      on the working side.
- [ ] Open **Advanced Filters** directly above the rule list. Try **No Comments**
      or **No Finding Details**; close the drawer and verify the scope.
- [ ] Open **Bulk Edit**, choose **All rules matching current filters** (or select
      particular rules and choose **Selected rules matching current filters**).
- [ ] For Comments and/or Finding Details, choose **Copy from Reference (blank
      working fields only)**. Leave Status at **Keep current status**.
- [ ] Inspect the preview and cancel once; verify nothing changed.
- [ ] Apply; matched blank fields receive prior notes, current statuses remain
      Not Reviewed, and unmatched/ambiguous rules are skipped.
- [ ] Clear filters if the newly filled rules disappear. Save CKLB and reopen it.
- [ ] Test an already-filled current note: blank-only keeps it. The explicit
      replace-existing choice replaces it only with nonempty Reference text.
- [ ] Use **Undo Bulk Edit** before closing the checklist; original fields return,
      while subsequent manual edits to an affected field are kept.
- [ ] Try Advanced Filters while Quick Filters is collapsed. Both controls must
      remain accessible and inside the navigator.

Copy actions do not adopt old assessment statuses or update reference content.
A prior rationale may need revision for the current instructions. Empty source
text never clears current text through these copy modes.

## New demo and reference downloads

- [ ] Download the core demo ZIP or individual CKLBs from the landing page.
- [ ] Open Firefox 01, compare with 02: exactly three changed rules.
- [ ] Import 02 into 01; the initial all-fields preview proposes three changes.
- [ ] Compare Apache 06 with 09: exactly four changed rules across Site/Server.
- [ ] Open 08: three STIGs / 34 rules for the fictional combined web host.
- [ ] Use the RHEL 04 gap filter to find its intentionally blank Open finding.
- [ ] Open the separate Viewer multi-checklist fidelity fixture: 15 STIG entries
      and 164 synthetic rule records; repeated families/releases are expected.
- [ ] Download original ZIP/XML from reference-archives and import. Each Apache
      ZIP must offer both Site and Server. Check the older/newer source versions.
- [ ] Compare navigator filters stay inside the sidebar. If text/counts do not
      fit, expand Quick Filters with mouse or Enter; include/exclude/clear and
      active counts remain usable without changing assessment data.

The [demo guide](demo-checklists/index.html) records exact outcomes. Samples
are partial and fictional; full reference import/update adds omitted rules.

## Library and working-data recovery (introduced in v0.7.5)

- [ ] Open **STIG Library**, add the synthetic reference ZIP or XML, and inspect
      its STIG metadata and rule count.
- [ ] Export Library, reopen that `.library.json`, and create an unreviewed
      checklist. Verify blank findings/comments and separate asset information.
- [ ] Add the same reference again; verify duplicate handling.
- [ ] Change working assessment text and wait for **Autosave: Saved**. Reload
      and verify restored data still needs an explicit CKLB save.
- [ ] Restart the browser and select a stored session through Autosave if needed.
- [ ] Verify library changes require Export Library and the library collection
      is not restored by browser working-data recovery.
- [ ] Cancel Clear All once, then confirm **Clear All Browser Recovery**. Verify
      recovery copies are removed, open work/library remain, and autosave pauses.
- [ ] Re-enable autosave explicitly and verify a new recovery checkpoint.
- [ ] Try Tabs/Sections and status hotkeys on a focused rule; typing in editors
      must not trigger a status change. Compare vertically stacked fields.

Browser recovery is profile/origin-specific; hosted and downloaded copies have
separate storage. Memory-saving behavior and private/managed browser policies
need user testing. Pending edits may be newer than the last checkpoint. Keep
explicit file backups. Export Library saves the catalog, and Save CKLB saves an
assessment; browser autosave does not silently update either file.

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

## Bulk editing and report smoke test

- [ ] Open `fixtures/synthetic-preview.cklb` and expand **Selection help**.
- [ ] Select individual rules, a Shift range, and all filtered rules.
- [ ] Bulk-edit Status and append/replace Comments or Finding Details; inspect
      the preview and cancel once before applying.
- [ ] Hide a selected rule with a filter; verify selected edits/reports exclude it.
- [ ] Undo a bulk edit and verify its original fields are restored even if filters changed.
- [ ] Repeat, manually edit one affected field, then undo. The later edit stays.
- [ ] Save CKLB and reopen; verify assessment values and counts.
- [ ] Export all/filtered/selected scopes as CSV and printable HTML.
- [ ] Verify report exports do not clear the CKLB unsaved indicator.
- [ ] In Excel/LibreOffice, verify CSV columns, Unicode, quoted multiline text,
      and that formula-like values are treated as text.
- [ ] Open downloaded HTML offline and inspect Print Preview / Save as PDF:
      first/last rules, long findings, Unicode, wrapping, and margins.
- [ ] Open an edited CKLB in STIG Viewer 3, check values and rule inventory,
      re-export, and reopen in Studio. Record the Viewer version.

Undo has one step per open checklist and no redo. A new effective bulk edit
replaces it; no-op edits and cancellation retain it. Undo history and selection
are not saved in CKLB. Reports show base severity; no override editor was added.
The report CSV is a spreadsheet report. v0.7.5 additionally offers a separate Viewer CSV exchange format.

## Assessment workflow smoke test

- [ ] Open `fixtures/synthetic-preview.cklb`.
- [ ] Use **Next Not Reviewed** to navigate matching rules; verify it respects filters and does not change assessments.
- [ ] Use **Import Assessment** and select `fixtures/synthetic-preview-reference.cklb`.
- [ ] Verify the preview appears before any status, findings, or comments change.
- [ ] Cancel once and verify nothing changes; repeat and apply the import.
- [ ] Verify selected assessment fields change while current rule instructions and asset data remain intact.
- [ ] Verify Overrides is opt-in and Skip source rules marked Not Reviewed is optional.
- [ ] Save full and filtered CKLBs, reopen them, and verify edited fields and `stig.size` counts.

Assessment imports apply to all exact matches, including rules hidden by filters.
Blank selected source values overwrite destination values. Ambiguous matches and
known version/release differences are skipped. No rules or STIGs are added.

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
2. Legacy CKL conversion of metadata not represented by standard checklist fields.
3. Incorrect comparison matches with duplicated rule identifiers in different STIGs.
4. Asset merge outcomes, conflict handling, metadata loss, and UUID relationships.
5. ZIP CRC, Unicode names, final filename uniqueness, and report consistency.

Do not characterize passing an informal smoke test as certification or security validation.
