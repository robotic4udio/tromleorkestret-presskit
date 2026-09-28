# Tromleorkestret — Press Kit

Hand-editable XeLaTeX press/booking documents for Tromleorkestret.

## Files

- `booking_sheet.tex` — the booking sheet source (2-page A4)
- `rider.tex` — the technical rider source (2-page A4)
- `img/` — photo assets used by both documents (see `img/README.md` for how each crop was made)
- `Tromleorkestret - Booking Sheet.pdf` — the current compiled booking sheet PDF
- `Tromleorkestret - Technical Rider.pdf` — the current compiled technical rider PDF

## Building

Requires XeLaTeX with system fonts Lora, Bitstream Charter (or macOS "Charter"), and DejaVu Sans Condensed.

```bash
xelatex -interaction=nonstopmode booking_sheet.tex
xelatex -interaction=nonstopmode booking_sheet.tex   # run twice for cross-references

xelatex -interaction=nonstopmode rider.tex
xelatex -interaction=nonstopmode rider.tex   # run twice for cross-references
```
