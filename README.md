# Data Quality Dashboard (DQD) Results

This repository hosts the interactive **Data Quality Dashboard (DQD)** results for OMOP CDM data based on synthetic data.  
The dashboard provides a web-based interface for exploring data quality checks, including conformance, completeness, and plausibility.

## View the Dashboard
The dashboard is published on GitHub Pages and can be accessed here:  
[View DQD Results](https://glu-wi.github.io/DQD-results/)

> No R or Shiny is required. Simply open the link in your browser.

## Repository Contents
- `index.html` – Entry point for the dashboard viewer  
- `results.json` – Data Quality Dashboard results (generated from DQD in R)  
- `js/`, `css/`, and other static assets – Supporting files for the viewer  

## How to Update Results
1. Run DQD in R and export results to a JSON file:
   ```r
   DataQualityDashboard::executeDqChecks(
     connectionDetails = connDetails,
     cdmDatabaseSchema = "cdm_schema",
     resultsDatabaseSchema = "results_schema",
     cdmSourceName = "MyCDM",
     outputFile = "results.json"
   )

2. Replace the existing `results.json` in this repo with the new file.

3. Commit and push the change:
   ```bash
   git add results.json
   git commit -m "Update DQD results"
   git push
   ```

4. GitHub Pages will automatically redeploy with the updated results.

## Notes

-   This repository is for demo and sharing results only.

-   To rerun DQD checks or customize them, use the R package.