# Platform Statistics

## Purpose
This repository consists of files of metadata that summarise statistics for sequence data pertaining to specific organisms from the COVID-19 Data Portal (https://www.covid19dataportal.org/) and the Pathogens Portal (https://www.pathogensportal.org/). The data produced here has been powered by the European Nucleotide Archive (ENA), which underpins the sequence data in both portals - https://www.ebi.ac.uk/ena/browser/home.

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
Ensure TAX_ID is the appropriate number, e.g. using Ontology Lookup Service - https://www.ebi.ac.uk/ols4/ontologies/ncbitaxon at EMBL-EBI.

The metadata provided on the whole has been filtered and also cleaned of poor or missing metadata.

## Notes
Contributors: Carla Cummins, Colman O'Cathail

![alt text](https://github.com/nadimm-rahman/platform-statistics/blob/main/ENA_logo.png?raw=true)