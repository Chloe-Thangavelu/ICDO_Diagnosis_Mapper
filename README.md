# ICD-O Diagnosis Group Mapper
A specialized tool for mapping ICD-O diagnosis codes (4-digits) and terms to diagnostic groups(3-digit).

# Overview
This tool automates the classification of oncology diagnoses into their broader diagnostic categories. It is designed to accept user-provided data, validate the format, and return a standardized mapping report.

# Usage Instructions
### File Preparation:
Place your data file containing your diagnoses identifiers (codes or terms) in the input/ directory (CSV, TSV, or Excel formats supported). The tool will automatically process any supported spreadsheet format.

An example inpt file is available in the data/ directory of the project.

### Data Placement:

The tool identifies mapping keys based on the first column of the provided file.

If your file contains multiple columns, only the first column will be used for group identification; all other columns will be preserved in the output.

###  Data Requirements:

Single-Type Columns: Each column must contain only one type of data (either all codes or all terms). Mixed data types within a single column are not supported.

Code Formatting: Diagnosis codes must follow the standard ICD-O format: ####/# (e.g., 9380/3).

Term Matching: Diagnosis terms must match standardized ICD-O terminology exactly, including specific punctuation, capitalization, and spacing (e.g., Glioma, malignant).

### Mapping Logic
Code Mapping: The tool extracts the 3-digit prefix from the code to determine the parent diagnostic group.

Term Mapping: The tool performs an exact string match against the master ICD-O glossary (including synonyms) to retrieve the corresponding group.

Validation: Entries that do not meet formatting standards or lack a match in the glossary will be flagged in a "Comments" column in the final output.
