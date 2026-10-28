# Additional Viewer 3 multi-checklist fixture

[`multi-checklist-from-stigviewer3.cklb`](multi-checklist-from-stigviewer3.cklb)
is the user-supplied Viewer 3 multi-checklist export. It contains **15 STIG
entries and 164 rule records** corresponding to the ten generated demo CKLBs.

Before publication, every STIG and rule field was compared with the generated
demo fixtures: all match known synthetic/reference values. Asset fields are
blank/default, and the title is `multi-checklist`. Nonempty assessment text is
explicitly marked DEMO ONLY. The supplied file is preserved without changes.

This is an additional open/save fidelity fixture, supplied separately from the
ZIP of ten core demos. It includes repeated STIG identities and different
releases. Use the numbered pairs for ordinary comparison and assessment-overlay
walkthroughs, whose exact outcomes are listed in [the demo guide](README.md).

The filename records its user-supplied origin. These checks do not independently
certify the full Viewer graphical workflow or interoperability with every version.

SHA-256 of the supplied file:

```text
b615ba44397e3656f1da4a04b63706661fde7620426086b15a6d70b2082c68b2
```
