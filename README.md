# STIG Studio v0.7.2 — Experimental Public Preview

> **EXPERIMENTAL. NOT FOR OPERATIONAL ASSESSMENTS OR PRODUCTION REPORTING.**
>
> Use only synthetic or fully sanitized checklists. Do not submit classified, CUI,
> personally identifying, or real system assessment information to public Issues.

This public repository publishes **the current experimental snapshot** of STIG Studio
v0.7.2 for controlled testing and community feedback. It is independent of the
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

## New in v0.7.2

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

- Filtered exports may retain old `stig.size` metadata.
- Comparison matching may match rules across different STIGs incorrectly.
- CKL XML -> CKLB JSON conversion may omit unknown XML metadata.
- Asset combining may omit data from older inputs or create inconsistent `stig_uuid` links.
- Archive output and filename collisions have not been fully validated.

These are preliminary source-review findings, not a list of reproduced failures.
Do not rely on this build for production or authoritative compliance data.

## Source preservation

`stig-studio-v0.7.2.html` is preserved **byte-for-byte** from the imported
v0.7.2 development snapshot. SHA-256:

```text
f020ef28e85bfaa93d4334769755429ed0b4978db0199b501c912b5d89ecee6e
```

All explanatory and warning content lives separately in `index.html` and
supporting documents. Changes made to the development repository do not
automatically publish here. The earlier `stig-studio-v0.7.1.html` snapshot remains unchanged for reference.

## Licensing and feedback

This is **not an open-source release**. See [LICENSE](LICENSE) for limited
preview evaluation permission. Your rights to use other versions or source
repositories may differ. Do not assume source visibility grants general rights
to redistribute or integrate the code elsewhere.

Issue reports are public. Please provide browser/version, reproduction steps,
expected and actual outcomes, and synthetic files if needed.
