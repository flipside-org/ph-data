# Penny Harvest data wrangling

This repository contains the scripts that handle the data wrangling for the [Penny Harvest Organization Finder](https://github.com/flipside-org/penny-harvest). The data is provided in Excel format and transformed into individual markdown files, ready to be used by Jekyll.

## 1. ph-xls2csv.sh
This script takes care of the first clean-up of the Excel data, its transformation to CSV and calls ```geocode.py``` that takes care of the geocoding.  
Even though the Organization Finder only requires data about the organizations, this first script processes the data on schools and grants as well.

### Usage

```$ bash ph-xls2csv.sh -i [file-name]```

For example: ```bash ph-processor.sh -i Map_data.xls```

### Dependencies

- csvkit 
- python
- wget
- unzip
- sed

## 2. ph-org-csv2md.py
This python script generates Penny Harvest organization profiles in Markdown format from the CSV file prepared by ```ph-xls2csv.sh```.

### Usage

```python ph-xls2csv.py [folder_out] [file_in]```

For example: ```python ph-xls2csv.py markdown ORGS.csv```

## 3. ph-grants-org.py
Processes the grant information per organization and stores it in separate CSV files in the folder: ```csv-data/orgs```

### Usage

```python ph-grants-org-py [file_in]```

For example: ```python ph-grants-org-py GRANTS.csv```

## Team

Daniel da Silva - [Github](https://github.com/danielfdsilva)  
Ricardo Mestre - [Github](https://github.com/ricardomestre)  
Olaf Veerman - [Github](https://github.com/olafveerman)