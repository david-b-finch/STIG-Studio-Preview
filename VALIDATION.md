# 0.7.8 validation scope

Validation date: 2026-10-28.

- **210 offline integration checks passed in Chrome 156.0.8078.47 and Firefox
  140.17.0** using the standalone HTML through `file://`. They cover imports,
  assessment preservation, comparison, filters, bulk/undo, exports, library,
  recovery, migration, scans and combiner behavior, plus 0.7.8 usability/Explorer.
- Three build/packaging checks passed. The public HTML is copied byte-for-byte
  from development; README.md records SHA-256. The app has one inline script,
  no fetched modules/dependencies, and retains dark colors, fixed assessment
  navigator width and bounded stacked editors.
- Eight native offline Explorer workflow groups passed per browser. Supplied
  Firefox V6R9 XML, Apache Site/Server ZIP and a locally available ASD ZIP formed
  four STIGs/380 rules. Actual library and CKLB downloads reopened, metadata/IDs
  and new UUID links survived, and the original assessment stayed unchanged.
  The private/local ASD input is not part of these public downloads.
- Actual Firefox V6R4/V6R9 references verified right-hand disclosures, trusted
  keyboard checkboxes, latest-default V6R9 creation, explicit V6R4 selection,
  preservation through collapse/bulk selection, and exact save/reopen of all 34
  unreviewed V6R4 rules. Short-window checks requested 1024×600 and 1280×720;
  Firefox content height excludes browser chrome. Screenshots were inspected.
- Earlier Viewer handler outputs were reused in three integration checks.
  Full Viewer graphical interoperability was not rerun or established for this
  snapshot. Natural tab discard/power loss, managed Edge, browser zoom and full
  assistive-technology/human usability acceptance remain separate checks.

Preview packaging checks cover landing-page layout at 1280/600 pixels, local
links, adjacent Open/Download controls for 0.7.8 and 0.7.7, byte-identical app
and demo/reference downloads, and downloaded offline `file://` startup/Explorer.
The new snapshot is published separately; historical HTML and test data remain
unchanged. These development checks are not interoperability certification.

0.7.8-1 will contain the next selected-STIG summary/naming and validation work.
Those proposed additions are not part of this 0.7.8 snapshot.

## Earlier 0.7.7 validation scope

Validation date: 2026-10-27.

- 185 offline integration checks passed in both Chrome 156.0.8078.47 and
  Firefox 140.17.0 using the standalone HTML through `file://`. They include ten
  new reference-text/shortcut cases and existing import, export, comparison,
  filter, bulk/undo, library, recovery, migration, scan and combiner coverage.
- Copy cases cover each text field independently, blank-only/replacement modes,
  empty-source skipping, unchanged current decisions, exact text preservation,
  selected/filtered and assessment-gap scopes, ambiguity, cancellation, stale
  previews, undo, and CKLB save/reimport. The Firefox demo pair exercises copying
  across releases. Advanced Filters access and focus are checked in inline and
  compact quick-filter layouts.
- All three assembly/packaging checks passed. The downloadable HTML matches the
  development artifact byte-for-byte; README.md records its SHA-256.
- Three focused native UI checks passed per browser: navigator/dialog/footer
  containment at 1024×600 and 1280×720 requested window sizes, cancel without
  mutation, and UI apply/undo preserving current notes, status and source data.
  Firefox content viewports were 1024×514 and 1280×634; Chrome content viewports
  matched the requested dimensions. Screenshots were inspected.
- Previous native Viewer outputs were reused by three integration cases; Viewer
  itself was not rerun for 0.7.7. No fresh native restart/discard recovery test,
  Edge test, or manual assessor acceptance was performed for this version.

Preview packaging passed in Chrome using a loopback-only static server:
landing-page layout at 1280/600 pixels, all local links, adjacent Open/Download
controls for 0.7.7 and 0.7.6, both HTML downloads matching source bytes, all 22
linked demo/reference downloads, and downloaded 0.7.7 startup/Library access via
`file://` with networking offline. Earlier snapshots and data downloads remain
unchanged. This validates the prepared site; deployment is a separate GitHub
Pages operation after the preview commit is pushed.

The existing autosave, CKLB serialization and one-step Bulk Edit undo paths are
reused. No new file format, external library or network dependency was added.
Copied rationale/evidence still needs review against current instructions.

## Earlier 0.7.6 validation scope

- 175 offline integration checks passed in both Chrome 156.0.8078.47 and
  Firefox 140.17.0, including reference/checklist imports, saves, comparison,
  filters, library, recovery, migration, scan results and combiner cases.
- Three assembly/packaging checks passed. The downloadable HTML is identical
  to the development artifact; the checksum is in README.md.
- Native filter checks passed at 1024×600/1280×720, including enlarged-text
  collapse/expansion, trusted Enter, active counts and include/clear behavior.
- The stabilization pass also checked native Firefox reports/PDF/ZIP, browser
  recovery/restart/multiple tabs/clear, and actual 0.7.5-to-0.7.6 recovery.
- Actual Viewer 3.8.1 file handlers accepted tested synthetic CKLB/CKL/CSV and
  repaired combined output. Full Viewer graphical acceptance is not claimed.
- Ten compact CKLB fixtures were verified in offline Chrome and Firefox against
  all six source files/eight benchmarks. Exact reference fields, counts, UUID
  links, comparisons/imports and migration expectations passed. The separately
  supplied Viewer file has 15 STIG entries/164 records matching those demos.

Public preview checks verify landing-page layout, local links, both application
downloads, linked demo/reference download bytes, and downloaded offline startup.
Full Viewer GUI, Edge, Excel, natural tab discard timing, power loss and managed
storage policies remain manual acceptance items. Passing these checks is not
security certification or permission for operational assessment use.
