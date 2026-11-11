# LaTeX and PDF notes

> **Status:** Needs review
> **Applies to:** The original notes referred to MiKTeX; versions are unknown
> **Last verified:** Not tested

These are historical troubleshooting clues, not guaranteed fixes. Back up project files and consult the current distribution documentation before changing a TeX installation.

## MiKTeX map and file database

The old note suggested rebuilding font maps and updating the filename database with `initexmf --mkmaps` and `initexmf --update-fndb`. These commands may not apply to current MiKTeX releases or every missing-PDF problem.

## XeLaTeX output

The old note suggested trying `xelatex --no-pdf` and inspecting an XDV file, then adding `fontspec` and an OpenType extension setting. Confirm that the actual error concerns font discovery or PDF generation before using these hints; unnecessary font settings can change document output.

## Nomenclature build order

An older recipe used XeLaTeX, BibTeX, MakeIndex with `nomencl.ist`, then XeLaTeX twice. The required sequence depends on the document and build tool. Prefer the project README or current LaTeX package guidance.

## PDF reader color preference

An old preference used black text on a light gray page. This is a reader preference rather than a repair procedure; configure it in the chosen application's accessibility or page-display settings.
