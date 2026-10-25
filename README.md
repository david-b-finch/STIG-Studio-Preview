# STIG Studio v0.7.4 — Experimental Public Preview

> **EXPERIMENTAL. NOT FOR OPERATIONAL ASSESSMENTS OR PRODUCTION REPORTING.**
>
> Use only synthetic or fully sanitized checklists. Do not submit classified, CUI,
> personally identifying, or real system assessment information to public Issues.

This public repository publishes **the current experimental snapshot** of STIG Studio
v0.7.4 for controlled testing and community feedback. It is independent of the
main `STIG-Tools` development repository. It is **not** an official DISA, DoD,
or U.S. Government product or endorsement.

## Open the preview

After GitHub Pages deployment, visit:

https://david-b-finch.github.io/STIG-Studio-Preview/

The landing page explains the experimental limitations and links to the app.
The application runs in a browser and has no build process or server-side logic.
Hosting is provided by GitHub Pages; ordinary access logs may apply.

## Recommended first test

1. Read [TESTING.md](TESTING.md).
2. Download [`fixtures/synthetic-preview.cklb`](fixtures/synthetic-preview.cklb).
3. Launch the preview and select **Open Checklist**.
4. Change a sample rule's assessment and save CKLB.
5. Reopen the saved CKLB; compare the original and edited content.
6. Repeat with [`fixtures/synthetic-preview-reference.cklb`](fixtures/synthetic-preview-reference.cklb) for comparison behavior.
7. Report unexpected behavior using a GitHub Issue with **synthetic data only**.

## New in v0.7.4

- Select rules individually, with Shift ranges, or with Ctrl/Command-click;
  bulk-edit Status, Comments, and Finding Details after reviewing the change count.
- Append, replace, or explicitly clear assessment text. Selected rules hidden by
  filters are excluded; all-filtered scope includes matching collapsed STIGs.
- Undo the most recent effective bulk edit per open checklist, keeping later
  manual edits, reference copies, and assessment imports. Undo applies to the
  original operation regardless of current filters and requires a CKLB save.
- Selection help explains range selection, filters, and undo scope.
- Export all, filtered, or selected rules as CSV or standalone printable HTML
  through **Save / Export**. Reports include asset and reference information;
  exporting a report does not mark CKLB changes saved.
- CSV quotes multiline/Unicode text and prefixes formula-like cells with an
  apostrophe. HTML escapes imported text and uses print styles without scripts
  or external resources. Severity override editing was not added.
- 101 Firefox offline integration tests passed. Additional Firefox checks printed
  a complete synthetic 13-page PDF and verified screenshot/clean shutdown.
  Chrome/Edge, Excel/LibreOffice behavior, and Viewer acceptance of generated
  CKLB remain untested in the development workspace.

## Earlier assessment workflow (v0.7.3)

- **Import Assessment** overlays selected status, findings, comments, and optional
  overrides from CKL/CKLB/JSON onto the current checklist after a preview.
  Reference content and asset data remain intact. Exact STIG/full rule-ID matching
  skips ambiguous matches and known version/release differences; this does not
  migrate assessments between STIG versions.
- **Next Not Reviewed** respects active filters, wraps around, and expands the
  destination STIG without changing assessment data.
- Full and filtered CKLB exports recalculate rule-count metadata.
- Description prose retains literal entity examples, and DPMS reference metadata
  is populated only from explicit, consistent source references.
- 85 Firefox offline integration tests passed, including save/reopen checks for
  12 local checklist files and a 286-rule ASD field audit against Viewer 3 exports.
  Opening Studio-generated output in Viewer 3 and Chromium execution remain unverified.

For a synthetic assessment-import test, open
[`fixtures/synthetic-preview.cklb`](fixtures/synthetic-preview.cklb), then choose
**Import Assessment** and select
[`fixtures/synthetic-preview-reference.cklb`](fixtures/synthetic-preview-reference.cklb).
Review the proposed changes before applying, save CKLB, and reopen it.

## Reference archive import (introduced in v0.7.2)

Use **Import STIG Reference Archives** to open a DISA reference ZIP or extracted
XCCDF XML. A single STIG opens directly as an unsaved assessment with every rule
Not Reviewed. Files containing multiple STIGs present a selection dialog. Enter
asset details separately through **Asset Info**.

Try [`fixtures/synthetic-reference.zip`](fixtures/synthetic-reference.zip) or
[`fixtures/synthetic-reference.xml`](fixtures/synthetic-reference.xml); both
contain one synthetic rule. No DISA packages or real assessment data are included.

Reference archives are processed locally. Stored and DEFLATE ZIP entries are
supported using native browser decompression. Unsupported archive features,
unsafe paths, oversized input, and DTD/entity declarations are rejected.
Profiles that tailor rule selection, inheritance, automated/complex checks, and
SCAP data-stream wrappers are not supported. Older browsers without native raw
DEFLATE support can import XML extracted locally instead.

Firefox offline integration tests cover synthetic inputs plus local OneDrive
and ASD reference packages. Chromium and STIG Viewer 3 interoperability have
not been validated; successful Studio reimport is not interoperability certification.

## Known or suspected issues under evaluation

- Comparison matching may match rules across different STIGs incorrectly.
- CKL XML -> CKLB JSON conversion may omit unknown XML metadata.
- Asset combining may omit data from older inputs or create inconsistent `stig_uuid` links.
- Archive output and filename collisions have not been fully validated.

These are preliminary source-review findings, not a list of reproduced failures.
Do not rely on this build for production or authoritative compliance data.

## Source preservation

`stig-studio-v0.7.4.html` is preserved **byte-for-byte** from the
v0.7.4 development snapshot. SHA-256:

```text
ff25b1e90c84b787d8ea55f73fbd6585f33a5541de7b4b74e64f3801cbf416c2
```

All explanatory and warning content lives separately in `index.html` and
supporting documents. Changes made to the development repository do not
automatically publish here. The earlier 0.7.1, 0.7.2, and 0.7.3 HTML snapshots remain unchanged for reference.

## Licensing and feedback

This is **not an open-source release**. See [LICENSE](LICENSE) for limited
preview evaluation permission. Your rights to use other versions or source
repositories may differ. Do not assume source visibility grants general rights
to redistribute or integrate the code elsewhere.

Issue reports are public. Please provide browser/version, reproduction steps,
expected and actual outcomes, and synthetic files if needed.
