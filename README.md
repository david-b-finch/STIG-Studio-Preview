# STIG Studio v0.7.8 — Experimental Public Preview

> **EXPERIMENTAL. NOT FOR OPERATIONAL ASSESSMENTS OR PRODUCTION REPORTING.**
>
> Use only synthetic or fully sanitized checklists. Do not submit classified, CUI,
> personally identifying, or real system assessment information to public Issues.

This public repository publishes **the current experimental snapshot** of STIG Studio
v0.7.8 for controlled testing and community feedback. It is independent of the
main `STIG-Tools` development repository. It is **not** an official DISA, DoD,
or U.S. Government product or endorsement.

## Open the preview

After GitHub Pages deployment, visit:

https://david-b-finch.github.io/STIG-Studio-Preview/

The landing page offers adjacent **Open** and **Download** buttons for both
v0.7.8 and the previous v0.7.7. Download the standalone HTML and open it directly
in a current browser to test offline. No installation or server is needed.
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

## New in v0.7.8

- **STIG Explorer:** a fixed tab with STIG Navigator, Rule Navigator and Rule
  Information. File contains Load DISA ZIP/XML and Open/Merge/Export Library.
  Browse all rules through search and bounded pages, with Tabs or Sections.
- Check the main STIG box for latest, or expand the right-hand + and check any
  exact version/release. One release per STIG is retained. Older selections
  survive collapsing, searches, importing newer references and Select Matching.
- Create complete unreviewed single/multi-STIG checklists with blank answers and
  asset information, fresh internal UUIDs and preserved source IDs/metadata.
  Clicking selected Explorer again, or an assessment tab, returns to assessments.
- **New Checklist** distinguishes creation from Open Checklist. **Save CKLB As**
  and Ctrl/Command+Shift+S name a full CKLB download. Recovery reports a local
  browser copy; it does not rewrite CKLB files. File also offers workspace backup
  and Save All. Project follows Help; branding sits at the far right.
- Quick filters toggle include/clear. Explicit exclusions, field-specific text
  filters and comparison filters share Advanced Filters. Bulk Edit shows counted
  selected-visible/all-filtered scopes and only displays needed text editors.
- Dark styling, fixed assessment navigator width and vertically stacked Finding
  Details/Comments remain. Editor accessible names distinguish Working/Reference.
- **210 integration checks per browser**, three packaging checks, and eight
  native offline Explorer workflow groups per browser passed. Tests include
  latest-default and older-release CKLB creation/download/reimport. See
  [validation scope](VALIDATION.md) and the [transition exercise](TRANSITION-0.7.8.md).

## Earlier comparison improvements (v0.7.7)

- **Advanced Filters** opens the existing drawer directly above the rule list,
  including when Quick Filters is collapsed.
- During comparison, **Bulk Edit** Comments and Finding Details offer **Copy
  from Reference (blank working fields only)** and an explicit replacement
  option. Use the existing selected/filtered scopes and No Comments / No Finding
  Details filters, preview, cancellation and Undo Bulk Edit.
- Empty source fields are skipped; the blank-only choice protects current notes.
  Reference statuses are never copied by these actions. Leave Status at Keep
  current status to preserve the current assessment decision.
- Matching uses unambiguous STIG-scoped rule identifiers. Title-only, duplicate
  and one-to-many mappings are skipped. Review old rationale against current
  instructions before relying on it.
- 185 integration checks passed in each of Chrome and Firefox, plus three
  packaging checks and three focused offline UI checks per browser. See
  [validation scope](VALIDATION.md) for executed checks and limitations.

## Earlier stabilization (v0.7.6)

- Focused source refactoring, with one standalone offline HTML for users.
- Asset-combiner rules link to their actual containing STIG UUID; legacy
  missing UUIDs are stable, and combined filenames avoid case collisions.
- Comparison navigator filters stay inside the existing 320-pixel sidebar.
  Oversized filter text/counts switch to a keyboard-accessible Quick Filters
  disclosure. Filter state/counts remain available; colors/editors are unchanged.
- 175 integration checks passed in each of Firefox and Chrome. Packaging,
  native filter screenshots/keyboard, earlier report/ZIP/PDF, browser recovery
  and actual 0.7.5-to-0.7.6 recovery checks passed. Viewer 3.8.1's actual file
  handlers accepted the tested synthetic outputs; full GUI acceptance remains
  separate. See [validation scope](VALIDATION.md).

## Downloadable test data

- [Demo guide and downloads](demo-checklists/index.html): ten clearly fictional
  partial CKLBs (11–34 rules), [ZIP bundle](demo-checklists/stig-studio-demo-checklists.zip),
  comparison pairs and expected outcomes. Firefox 01/02 differ in three rules;
  Apache 06/09 differ in four. Assets use reserved demo names/addresses.
- [Additional Viewer 3 multi-checklist](demo-checklists/multi-checklist-from-stigviewer3.cklb):
  15 STIG entries/164 synthetic rule records matching the core demos, with
  blank/default asset fields. This is a separate fidelity fixture with repeated
  STIG families/releases, not an ordinary single-asset comparison pair.
- [Reference archives](reference-archives/index.html): six original DISA ZIP/XML
  inputs for Firefox, RHEL 8 and Apache Site/Server across older/newer releases.
  Files are byte-for-byte copies of the supplied `Test-Docs-20261017` folder;
  [source hashes](reference-archives/manifest.json) record their provenance.

Only fictional completed assessments are published. Reference packages are
third-party materials with their original notices; the application evaluation
terms do not grant new rights in them. No generator or installation is needed
to use these downloads. The demo manifest records the application used at
fixture creation; its hash can differ from the latest application snapshot.

## Earlier workflows and library (v0.7.5)

- A file-based **STIG Library** screen opens/merges/exports `.library.json`
  catalogs, imports reference ZIP/XML, previews releases, and creates unreviewed
  single/multi-STIG checklists. Export Library saves catalog changes explicitly.
- **Browser Autosave & Recovery** checkpoints working assessments locally when
  storage is available, restores after reload, and offers stored sessions after
  restart. It excludes the library collection and does not mark CKLB files saved.
  **Clear All Browser Recovery** removes Studio recovery data and pauses writers,
  retaining open work, the current library, and downloaded files.
- Grouped menus, prominent Asset Info, Check-first Tabs/Sections, vertically
  stacked bounded editors, aligned comparison fields, and focused-rule hotkeys
  1/N, 2/O, 3/X, and 4/R. The rule-list width and dark palette remain unchanged.
- STIG revision migration previews, XCCDF scan-result import, complete-STIG
  building, portable workspaces, Save All ZIP, assessment-import selection/text
  options, Viewer CSV exchange, and mapped legacy CKL export.
- 156 offline integration checks passed in each of Firefox 140.17.0 and Chrome
  156.0.8078.47. Native checks covered input-driven autosave, reload/renamed HTML,
  browser restart/recovery, and clearing; Chrome also covered freeze/resume and
  independent tabs. Short-window UI, CSV/ZIP/PDF, LibreOffice, and Viewer 3.8.1's
  native file handlers were checked. Full Viewer graphical acceptance, natural
  Memory Saver timing, and power loss remain untested. These are development
  checks, not interoperability certification or a security audit.

Browser storage is specific to a browser profile/origin. The hosted preview and
downloaded HTML do not share recovery data. Other browsers, moved folders,
private mode, and enterprise policies may behave differently. Keep explicit
CKLB/Workspace backups; unexported library edits are transient.

## Earlier bulk editing and reports (v0.7.4)

Coverage statements in earlier-version sections describe those snapshots.

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
contain one synthetic rule. Original DISA packages are also available under `reference-archives`; completed assessment samples remain fictional.

Reference archives are processed locally. Stored and DEFLATE ZIP entries are
supported using native browser decompression. Unsupported archive features,
unsafe paths, oversized input, and DTD/entity declarations are rejected.
Profiles that tailor rule selection, inheritance, automated/complex checks, and
SCAP data-stream wrappers are not supported. Older browsers without native raw
DEFLATE support can import XML extracted locally instead.

Firefox/Chrome offline checks cover synthetic and locally supplied inputs. Actual Viewer 3 file handlers were checked; successful Studio reimport or handler acceptance is not full GUI interoperability certification.

## Remaining acceptance work

- Full Viewer graphical open/edit/save/re-export workflows and Edge on managed
  workstations remain manual checks. The additional Viewer-supplied fixture
  establishes known synthetic input provenance, not general certification.
- Natural Memory Saver timing, power loss and private/enterprise storage policy
  behavior remain unverified. Keep CKLB/Workspace backups.
- CKL/CSV are mapped interchange formats and cannot retain every CKLB field.
- Real scanner outputs and additional complex XCCDF/package variations require
  their own implementation and tests. Applicability planning and severity override
  editing are intentionally excluded.

## Source preservation

`stig-studio-v0.7.8.html` is preserved **byte-for-byte** from the
v0.7.8 development snapshot. SHA-256:

```text
94acbb0cc74224822601d954858c37824ccd235f8676c8da97531e884ad4d732
```

All explanatory and warning content lives separately in `index.html` and
supporting documents. Changes made to the development repository do not
automatically publish here. The earlier 0.7.1, 0.7.2, 0.7.3, 0.7.4, 0.7.5, 0.7.6, and 0.7.7 HTML snapshots remain unchanged for reference.

## Licensing and feedback

This is **not an open-source release**. See [LICENSE](LICENSE) for limited
preview evaluation permission. Your rights to use other versions or source
repositories may differ. Do not assume source visibility grants general rights
to redistribute or integrate the code elsewhere.

Issue reports are public. Please provide browser/version, reproduction steps,
expected and actual outcomes, and synthetic files if needed.
