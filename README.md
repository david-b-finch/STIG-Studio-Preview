# STIG Studio v0.7.1 — Experimental Public Preview

> **EXPERIMENTAL. NOT FOR OPERATIONAL ASSESSMENTS OR PRODUCTION REPORTING.**
>
> Use only synthetic or fully sanitized checklists. Do not submit classified, CUI,
> personally identifying, or real system assessment information to public Issues.

This public repository publishes **one frozen experimental snapshot** of STIG Studio
v0.7.1 for controlled testing and community feedback. It is independent of the
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

## Known or suspected issues under evaluation

- Filtered exports may retain old `stig.size` metadata.
- Comparison matching may match rules across different STIGs incorrectly.
- CKL XML -> CKLB JSON conversion may omit unknown XML metadata.
- Asset combining may omit data from older inputs or create inconsistent `stig_uuid` links.
- Archive output and filename collisions have not been fully validated.

These are preliminary source-review findings, not a list of reproduced failures.
Do not rely on this build for production or authoritative compliance data.

## Source preservation

`stig-studio-v0.7.1.html` is preserved **byte-for-byte** from the imported
v0.7.1 development snapshot. SHA-256:

```text
33a71b46c0c990d4d3a65e6267cd27a91c9fc5d5b5d085a398c7bc09cd9c7eb6
```

All explanatory and warning content lives separately in `index.html` and
supporting documents. Changes made to the development repository do not
automatically publish here.

## Licensing and feedback

This is **not an open-source release**. See [LICENSE](LICENSE) for limited
preview evaluation permission. Your rights to use other versions or source
repositories may differ. Do not assume source visibility grants general rights
to redistribute or integrate the code elsewhere.

Issue reports are public. Please provide browser/version, reproduction steps,
expected and actual outcomes, and synthetic files if needed.
