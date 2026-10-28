# 0.7.6 validation scope

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
