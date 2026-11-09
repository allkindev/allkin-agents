# Analyst

Makes tables speak. Give Analyst an export — sales, invoices, time sheets, survey answers, stock —
and a question, even a vague one. It checks what the file really contains, computes every figure
with scripts, and hands you a short note: what the numbers show, what they do not, and the table
and chart that prove it.

## Why its figures can be trusted

A language model that reads two hundred rows and announces their total is guessing. Analyst never
does: every total, average, count and percentage comes out of a script that reads the whole file
and computes exactly, to the cent. The model's part is to ask the right questions of the data and
to say what the answers mean.

## What it does

- **Reads** CSV, TSV and Excel (.xlsx) files; finds the delimiter, the decimal comma, the way the
  dates run.
- **Checks first**: empty cells, text among the numbers, duplicated rows, values written several
  ways, ambiguous dates — and tells you before computing.
- **Computes**: totals, averages and medians, counts, shares, by category, by customer, by month,
  quarter or week, with filters; differences and growth rates.
- **Draws** plain charts — bars, horizontal bars, lines — as SVG files.
- **Writes the note**: the answer first, three to five findings with their figures, what was left
  out, what cannot be concluded. On request, the results as an Excel file.

## What it needs

An imported agent arrives with no right beyond the defaults. On its Agent page:

| Setting | Why |
|---|---|
| **Competence: Data analysis** | Its method and its scripts. They run in a closed frame: Node alone, no network, reading and writing its own folder only. The first run shows you a card; you may approve this competence's scripts for the session or for good. |
| **Memory** (on by default) | To remember how your exports are built and your definitions — never your figures. |

It needs no system access, no web, no service.

## How to use it

1. **Attach the file** to your message (it must be in Analyst's folder for the scripts to read it)
   and ask your question: "Here are the 2026 invoices — who are our ten best customers and what
   share of revenue do they make?"
2. It tells you what the file is and what is doubtful, and asks once what it cannot know.
3. You get the note, with the paths of the result tables and charts.

## Limits

One table at a time: it does not join two large files, and it builds no statistical model. `.xls`
and OpenDocument files must be saved as `.xlsx` or `.csv` first. A formula in a workbook gives the
result the file kept when it was last saved.
