# FMC Tools
This is built upon a fork from [rnwolfe/fmc-tools](https://github.com/rnwolfe/fmc-tools) with some of my own changes to the function **export-acp-to-csv.py** and called it **export-acp-acp-to-csv2.py**. I also changed **fireREST.py** because it is throwing errors.

## Requirements
Install the following at C:\Python3InstallDirectory\Lib\site-packages:

### From this repository:
- extract_values.py
- fireREST.py
- schema.py

### Modules
- urllib3
- requests
- typing

## Table of Contents
1. export-acp-to-csv2.py

## export-acp-to-csv2.py
### Why
This script export all of the rules in a specific access policy to a CSV spreadsheet. 
The difference between this and the original ([rnwolfe/fmc-tools/export-acp-to-csv.py](https://github.com/rnwolfe/fmc-tools/blob/master/export-acp-to-csv.py)) is that it gives you flexibility in picking up the fields you want extracted by editing the configuration file **fields_to_extract.json** - change the desired fields to "yes" (initial settings are "no"). When run the very first time (or when **fields_to_extract.json** is deleted), this configuration file will be automatically created with all field values set to "no". The user then had to edit this text file and change the fields to "yes" for those values that are to be extracted. Another file named **sample_data.json** is created as a reference so that the user will see sample values of what are contained on these fields.

If the field names are changed by the vendor in any way, this version would allow you to make it work by deleting **fields_to_extract.json** so that it is rebuilt from scratch using the new field names.

If you want to add/delete fields to be extracted, all you need to do is edit **fields_to_extract.json** accordingly before running the script. You might not remember what the configuration file name is, hence, the script gives you the chance to edit this file (and supplying you with the configuration file name) after being run.

Another difference between this one and the original is the csv file heading names. This version supplies the keys and indeces that allows you to get that value. It is also dynamic following whatever is in the configuration.

