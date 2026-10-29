# Viewer 2 user transition exercise — Studio 0.7.8

Use only the supplied fictional demo answers. This exercise checks whether a
person can find familiar tasks without coaching; automated walkthrough results
are recorded separately. The application remains one offline HTML.

Open `stig-studio-v0.7.8.html` directly in Firefox or Chromium. Record browser,
OS, window size/zoom, elapsed time, mistakes and any point requiring help. Repeat
at a short desktop window. Keep the navigator width and dark appearance unchanged.

## Tasks

1. Find **New Checklist**. Import
   `reference-archives/U_MOZ_Firefox_STIG_V6R9_Manual-xccdf.xml` through the reference
   choice. Expect 33 rules, all Not Reviewed, blank answers and blank asset data.
2. Locate V-251545. Read Check, Discussion and Fix using Tabs or Sections.
   Set Not a Finding and enter fictional multiline Finding Details. Leave Comments
   blank. Navigate away and back; the answer must remain.
3. Filter Not Reviewed. Expect 32 rules. Click the same quick filter again; all
   33 rules return. Use Advanced Filters' separate Exclude button and verify the
   visible condition summary. Clear that exclusion.
4. In the same drawer, add a Title text filter for `installed version`. Expect
   V-251545. Remove it, or Clear all filters; all rules return. Use List Settings
   to inspect identifiers/sorting, then cancel/close without changing data.
5. Compare with `demo-checklists/01-firefox-v6r4-assessed-sample.cklb`. Keep the new
   Firefox assessment as **Working**. Open Bulk Edit; choose all filtered rules
   and Copy from Reference (blank working fields only) for Comments. Keep current
   Status and Finding Details. Preview, cancel once, repeat and apply. The first
   rule keeps the current Not a Finding decision and fictional evidence.
6. Explain selected-visible versus all-filtered scope using the displayed counts.
   Try an assessment-gap filter; copied rules may disappear once no longer blank.
   Clear filters to see them again. Undo Bulk Edit is available until another
   effective bulk edit replaces it or the checklist closes; later individual
   field edits are protected.
7. Use **File → Save CKLB As** or Ctrl/Command+Shift+S and name the downloaded
   copy. Verify it appears in browser downloads, then use **Open Checklist** to
   reopen it. All 33 rules, reference metadata, statuses and text must match.
8. Explain the difference between **Recovery: Saved locally** and a CKLB download.
   Recovery does not rewrite CKLB files. Library edits need Export Library;
   Workspace downloads are explicit backups through File.
9. Open the fixed **STIG Explorer** tab, or New Checklist → Choose from STIG Explorer. Import a reference into the
   library with File → Load DISA ZIP / XML or Open Library File if needed. Use
   the left STIG Navigator; expand the right-hand + for multiple releases and
   click a release to browse. Check the main STIG box to default to newest, or
   check a specific release underneath to choose that exact version.
   Search the middle Rule Navigator and read Check/Discussion/
   Fix/References/Details in Tabs or Sections. Browsing must show no assessment
   editors or status controls. Return by clicking the selected Explorer tab again
   or an existing assessment tab; its
   answers and reader/filter preferences must remain unchanged.
10. In Explorer, select one or more complete STIGs and create a second unreviewed checklist.
   Existing assessment answers must remain unchanged. Export Library to retain
   changes to the catalog file. Rule searches must not remove rules from the new
   checklist. The main checkbox must default to latest; child checkboxes must
   permit an older release and replace any previously chosen release of that
   STIG. Confirm default Firefox creates V6R9 and explicitly checked V6R4 creates
   V6R4, including after collapsing/searching or using Select Matching. Save and
   reopen both. For ASD, page or search beyond the first 100 rules.

## Record the result

For each task record success without help, success with help, or failure, along
with confusing labels, extra clicks, lost focus and unexpected results. Check
keyboard-only navigation and editor names with assistive technology where
available. Do not count a scripted browser pass as human usability acceptance.

Remaining separate acceptance work includes native Viewer GUI round trips,
managed Edge, high browser zoom, real assessor sessions, and natural tab discard.
