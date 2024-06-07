# Lineage tracing of Shh+ floor plate cells and dynamics of dorsal-ventral gene expression in the regenerating axolotl spinal cord

This project involves the analysis, modeling and visualization of gene expression data from multiple genes, conditions and replicas using a piecewise constant fitting approach.

## Prerequisites

The following Python packages are required:
- pandas
- numpy
- scipy
- matplotlib
- seaborn

You can install these packages using pip:
```bash
pip install pandas numpy scipy matplotlib seaborn
```

## Data preprocessing

### Loading data
The data is loaded from an Excel file (`quantifications_all-n.xlsx`). Each sheet in the Excel file contains distance and expression data for various genes, conditions and replicas.

### Normalizing and binning data
Distances are normalized to a range of 0 to 100 and binned into specified intervals. The average expression within each bin is calculated.

### Categorizing data by gene and condition
Data is organized into dictionaries based on genes and conditions, and statistical metrics are computed.

### Visualizing data
- **Expression profiles**: plots of gene expression profiles along the distance axis for each gene and condition.
- **Piecewise constant fitting**: fitting the data using two-step and three-step piecewise constant functions to identify changes in expression levels.

## Piecewise constant fitting

### Two-step piecewise constant fitting
The two-step piecewise constant function fits the data with one switchpoint for most of the genes. The best fit is determined by evaluating the SSE for all potential switchpoints.

### Three-step piecewise constant fitting
The three-step piecewise constant function is used to fit the data with two switchpoints for Pax6. The function evaluates different pairs of switchpoints to minimize the sum of squared errors (SSE).

### Visualizing fitting results
- **SSE plots**: scatter plots showing the SSE values for different switchpoints.
- **Expression plots**: scatter plots of the data with the fitted piecewise constant function overlaid.

## Statistical comparison
- **Intensity and size comparison**: box plots comparing the corrected HCR signal intensity and domain size between conditions for each gene.

### Statistical annotations
Statistical tests (Mann-Whitney and t-test) are performed to compare the differences between conditions, and the results are annotated on the plots.

## Summary statistics
Summary statistics for gene expression data, including mean, median and std of intensity and size, are calculated and saved to a CSV file (`summary_stats.csv`).

## Running the analysis
To run the analysis, execute the script in a Python notebooks with the necessary packages installed. The script will generate visualizations and save the results to the specified output files.

## Contact
For questions or further information, please contact [ecuracosta@gmail.com](mailto:ecuracosta@gmail.com).
