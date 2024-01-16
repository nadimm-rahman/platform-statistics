# Platform Statistics

## Purpose
This repository consists of files of metadata that summarise statistics for sequence data pertaining to specific organisms from the COVID-19 Data Portal and the Pathogens Portal.
For raw read data, the following metadata is available:
- Base count across countries
- Isolate count across countries
- Duration between collection date and first published dates across countries
- Sequencing instrument platform information across countries
- Center names across countries

For sequence data, the following metadata is available:
- Isolate count across countries
- Duration between collection date and first published dates across countries

## Background
The base queries used include the following:
`Sequences : curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'result=sequence&query=tax_tree(TAX_ID)&fields=isolate,country,collection_date,first_public&format=tsv&limit=0' "https://www.ebi.ac.uk/ena/portal/api/search"`
`Raw Reads : curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'result=read_experiment&query=tax_tree(TAX_ID)&fields=experiment_accession,base_count,collection_date,first_created,country,instrument_model,instrument_platform,center_name&limit=0&format=tsv' "https://www.ebi.ac.uk/ena/portal/api/search"`
Ensure TAX_ID is the appropriate number, NCBI taxonomy can be used to check this: https://www.ncbi.nlm.nih.gov/.

The metadata provided on the whole has been filtered and also cleaned of poor or missing metadata.

## Notes
Contributors: Carla Cummins, Colman O'Cathail
