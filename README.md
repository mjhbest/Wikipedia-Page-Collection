# Wiki_COVID-disp Data Collection Code
IBS KAIST DSLAB WikiCOVID Data Collection Code
---
## Wikimedia Dump

This collection code is based on wikimedia dump files which released by [Wikimedia Foundation Dumps](https://dumps.wikimedia.org/backup-index.html).

This is a way to collect COVID-related wikipedia article data by running code after downloading wikidata and wikipedia dump files.  
Code is not a method using SPARQL wrapper.  
Collection Timestamp is November 20th, 2020. We used following Wikipedia dumps  

## Used Dumps
#### Since Wikipedia article data is enormous to use, three types of wikimedia dump files are used to utilize code effectively.
* Wikidata pagelink.sql
* Wikidata page.sql
* Wikipedia_page_prop.sql
### 1. Wikidata pagelink.sql
Pagelinks dump is used to get the 'COVID related pages'. Wikidata pageids of seed related pages are collected. 
### 2. Wikidata page.sql
Wikidata QIDs of COVID related pages are retrieved from wikidata pageids which collected in previous step by using page.sql file.
### 3. Wikipedia_page_prop.sql -(Each 11 languages)
Page_prop dump file for each language is a good way to get wikipedia pageid from wikidata QID. We used 11 languages' page_prop sql file is used to collect pageid.

## Details
### Seed Items
Three seeds for retrieving COVID related articles are "[COVID-19](https://www.wikidata.org/wiki/Q84263196)" (Q84263196), "[COVID-19 pandemic](https://www.wikidata.org/wiki/Q81068910)" (Q81068910), "[SARS-CoV-2](https://www.wikidata.org/wiki/Q82069695)" (Q82069695).
### Category
We Selected each articles category based on wikidata "instance of" label. Details are written in code.
### Instances
The output collected page csv file includes below instances.
- QID
- PageId
- Page Title
- Language
- Category
