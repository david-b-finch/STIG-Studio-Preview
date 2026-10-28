# STIG Studio demo checklists

**DEMO ONLY: fictional assessments, assets, reviewers, and evidence.**
These are deliberately incomplete rule subsets, not completed operational assessments.
Real rule identifiers, titles, instructions, release metadata, and references come from the supplied DISA reference files.
No checks were executed. No severity overrides are set.

Start with `01-firefox-v6r4-assessed-sample.cklb` using Studio’s **Open** button.
Keep these originals; save edited copies under different names.

| File | STIGs | Rules | Open / NAF / NA / NR |
| --- | ---: | ---: | --- |
| [01-firefox-v6r4-assessed-sample.cklb](01-firefox-v6r4-assessed-sample.cklb) | 1 | 12 | 3 / 3 / 3 / 3 |
| [02-firefox-v6r4-comparison-sample.cklb](02-firefox-v6r4-comparison-sample.cklb) | 1 | 12 | 2 / 4 / 3 / 3 |
| [03-firefox-v6r9-unreviewed-sample.cklb](03-firefox-v6r9-unreviewed-sample.cklb) | 1 | 11 | 0 / 0 / 0 / 11 |
| [04-rhel8-v2r4-assessed-sample.cklb](04-rhel8-v2r4-assessed-sample.cklb) | 1 | 14 | 4 / 4 / 3 / 3 |
| [05-rhel8-v2r8-unreviewed-sample.cklb](05-rhel8-v2r8-unreviewed-sample.cklb) | 1 | 14 | 0 / 0 / 0 / 14 |
| [06-apache-2025-site-and-server-assessed-sample.cklb](06-apache-2025-site-and-server-assessed-sample.cklb) | 2 | 20 | 6 / 6 / 4 / 4 |
| [07-apache-2026-site-and-server-unreviewed-sample.cklb](07-apache-2026-site-and-server-unreviewed-sample.cklb) | 2 | 16 | 0 / 0 / 0 / 16 |
| [08-web-host-combined-sample.cklb](08-web-host-combined-sample.cklb) | 3 | 34 | 10 / 10 / 7 / 7 |
| [09-apache-2025-second-pass-sample.cklb](09-apache-2025-second-pass-sample.cklb) | 2 | 20 | 4 / 8 / 4 / 4 |
| [10-firefox-v6r9-migrated-sample.cklb](10-firefox-v6r9-migrated-sample.cklb) | 1 | 11 | 3 / 3 / 2 / 3 |

## Suggested demonstrations

1. **Everyday assessment:** open 01. Try status keys 1/N, 2/O, 3/X, 4/R, Next Not Reviewed, Tabs/Sections, severity/status filters, and stacked Findings/Comments. Unicode and multiline text are intentional.
2. **Comparison:** compare 01 with 02: exactly three rules differ. Compare Apache 06 with 09: exactly four rules differ across Site and Server. The remaining rules match.
3. **Import Assessment:** open 01, import 02, preview, cancel once, then select rows/fields and apply. Exactly three rules have assessment changes before changing options. Save and reopen.
4. **Bulk edits and undo:** select several rules in 01 or 04, preview an edit, apply, manually edit one affected field, then Undo Bulk Edit. The later manual change stays.
5. **Assessment gaps:** 04 intentionally includes one Open rule without Finding Details. Use the assessment-gap filter to find it.
6. **Newer releases:** 03, 05, and 07 have only Not Reviewed rules and empty assessment text. Compare their real reference content with the older samples. Their fictional asset data is already populated.
7. **Reference updates:** open 01 and use Update STIG Reference with the supplied Firefox V6R9 XML. That full-reference update adds rules outside this small sample. File 10 instead demonstrates Studio’s migration using the coordinated compact V6R9 subset; it retains unchanged answers and leaves changed/new rules Not Reviewed.
8. **Apache multi-STIG:** 06/07/09 each contain both Site and Server. Expand each STIG and inspect the distinct release versions and rule counts.
9. **Combine the web host:** add 04 and 06 to Asset Combiner. Their fictional asset identity is the same, yielding three STIGs. File 08 is that prebuilt result. Add 09 to exercise same-release rule conflicts; newer filesystem modification time wins unless Drop is selected. Local files and ZIP entries have staged demo timestamps so 09 is later than 06; browsers or extractors may reset timestamps, so check the displayed source times.
10. **Saving/recovery/reports:** edit a copy, wait for browser Autosave, reload, restore, and explicitly Save CKLB. Try full/filtered exports, CSV/HTML reports, Save All, and Workspace. Use Clear All Browser Recovery only after saving wanted test output.

## Sources and sampling

Inputs were read from `Test-Docs-20261017/` without modification. The filename date is preserved.
Old/new rules were selected together using Studio’s migration matching, favoring real changed/added/removed examples, unchanged matches, and severity coverage. Excluded sample rules are not presented as removed reference rules.
Full raw benchmark XML was omitted to keep the CKLBs small. Other retained reference fields, nested group metadata, exact rule IDs, and source versions/releases were checked against the originals. Each STIG records its full and sampled counts in `studio_demo`.

| STIG | Original old → new | Sample old → new |
| --- | --- | --- |
| MOZ_Firefox_STIG | 34 → 33 | 12 → 11 |
| RHEL_8_STIG | 369 → 369 | 14 → 14 |
| Apache_Server_2-4_UNIX_Server_STIG | 47 → 45 | 10 → 8 |
| Apache_Server_2-4_UNIX_Site_STIG | 27 → 16 | 10 → 8 |

## Expected compact-reference update counts

| STIG | Unchanged | Changed | Added | Removed |
| --- | ---: | ---: | ---: | ---: |
| MOZ_Firefox_STIG | 9 | 2 | 0 | 1 |
| RHEL_8_STIG | 9 | 3 | 2 | 2 |
| Apache_Server_2-4_UNIX_Server_STIG | 6 | 2 | 0 | 2 |
| Apache_Server_2-4_UNIX_Site_STIG | 6 | 2 | 0 | 2 |

## Verification

Generated with stig-studio-v0.7.6.html on 2026-10-27.

- Chrome/156.0.8078.47: all 10 CKLBs reopened exactly under `file://`; reference fields, counts, UUID links, synthetic assets, comparison, assessment overlay, and Firefox migration expectations passed. Firefox/Apache demo files also opened through the real UI import path, and Apache’s Save CKLB output matched the fixture.
- Firefox/140.17.0: all 10 CKLBs reopened exactly under `file://`; reference fields, counts, UUID links, synthetic assets, comparison, assessment overlay, and Firefox migration expectations passed. Firefox/Apache demo files also opened through the real UI import path, and Apache’s Save CKLB output matched the fixture.
- This verifies Studio behavior. Full STIG Viewer graphical interoperability is not claimed.
- `demo-manifest.json` contains source/output SHA-256 hashes, selected IDs, inventories, and expected workflow counts.

To regenerate or verify with installed browsers, from the development repository:

```sh
python3 tools/create_demo_checklists.py --browser chrome
python3 tools/create_demo_checklists.py --verify-only --browser firefox
```

Generation refuses to overwrite existing outputs unless `--force` is supplied. Add `--record-verification` to a verification run to update this generated guide, manifest, and ZIP bundle.
No libraries, CDNs, servers, or packages are installed. All browser profiles are temporary. Source references and application HTML are unchanged.
