# Climate adaptation measures for Switzerland

A small website for browsing the table of measures from NCCS-Impacts, project P5: Climate costs. It shows adaptation measures by climate risk and by actor, together with their effectiveness, costs and assessment criteria.

## What the site offers

- **Start:** choose one or more climate risks and, optionally, who implements the measure.
- **Measures:** cards or a table, with search, filters, sorting and a CSV download of the current selection.
- **Measure page:** everything recorded for one measure, with the meaning of each rating shown next to it and links to the sources.
- **Indicators:** what each indicator means and what the values (for example low, medium, high) stand for.
- **References:** the sources behind the measures, each with the number of measures that cite it.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole website, including the data. This is the only file the site needs. |
| `update_data.py` | Rebuilds the data inside `index.html` from the Excel workbook. |
| `NCCS_Impact_P5_ClimateCosts_MeasuresTable_EN.xlsx` | The source workbook (optional to publish, needed to update the data). |

## View it on your computer

Download `index.html` and double-click it. It opens in a browser; no installation or server is needed.

## Publish it with GitHub Pages

1. Upload `index.html` to this repository (the repository must be public on a free GitHub account).
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select the `main` branch and the `/ (root)` folder, then save.
4. **Live site:** [Open the Adaptation Database](https://veruskamuccione.github.io/AdaptationDatabaseSwitzerland/)

Every later change to `index.html` in the repository is published automatically.

## Update the data

When the Excel workbook changes:

1. Put the new workbook in the same folder as `index.html` and `update_data.py`.
2. Install the one required package (only the first time): `pip install openpyxl`
3. Run: `python update_data.py`
   (or name the file: `python update_data.py MyWorkbook.xlsx`)
4. Upload the new `index.html` to GitHub.

The script reads these sheets: `Introduction`, `Definitions_Measures_Costs`, `Lists_Measures_Costs`, `Measures` and `References`. The script expects the workbook to keep its current layout: the same sheet names, the same order of columns in `Measures`, and the header rows in the same place.

## Adjusting the presentation

A few settings sit near the top of the script block in `index.html` and can be edited with any text editor:

- `HAZARDS` and `RISKS`: the hazard groups, the short names of the risks and their icons.
- `NORMALISE`: spellings in the `Measures` sheet that are merged into the value used in the `Lists` sheet.
- `REF_ALIAS`: source names in the `Measures` sheet that are written differently in the `References` sheet.

## Data source

Decision-making bases for dealing with climate change in Switzerland: information on cross-sectoral topics («NCCS-Impacts»), P5: Climate costs, table of measures.

## Licence and contact
