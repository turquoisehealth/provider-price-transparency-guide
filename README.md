# Provider Price Transparency - Suggested Machine-Readable Data File Format

The CMS Hospital Price Transparency Regulation ([45 CFR §180.50](https://www.federalregister.gov/d/2019-24931/p-1010))
requires hospitals in the United States to disclose a public list of all standard charges for all items and services 
online and requires that this data must be a single digital file that is in a machine-readable format. This repository offers 
a suggested file format for the required machine-readable file that follows best-practices. 

The file format format suggested here is based on the official payer price transparency file schemas maintained by CMS
here: https://github.com/CMSgov/price-transparency-guide

However, CMS does not yet provide a required file format or file schema for healthcare provider data. This repository is 
meant to expand on the official file formats maintained by CMS by extending them to cover the disclosure needs of healthcare 
providers. 

Please note that Turquoise Health has created this file format as a suggestion and is not affiliated with CMS or any
other governmental agency. We welcome the fantastic work that CMS is doing in the area and are posting this to 
provide feedback on where the rules may be enahanced in the future.

## Overview

This repository contains a set of schemas describing a data format (example implementation is encoded as JSON) for the 
Transparency in Coverage final rule. All machine-readable files must conform to a non-proprietary, open standards format 
that is platform independent and made available to the public without restrictions that would impede the re-use of 
that information.

## Background

Starting January 1, 2021, hospitals in the United States are required to disclose a public list of all standard charges 
for all items and services in a single machine-readable file. This requirement extends to insurance plans and issuers 
on January 1, 2022.

However while CMS requires a specific file format for insurance plan rate disclosure, no such required file format
was in place for the hospital rule. This repository offers a suggested file format to fill that gap.

## Keeping Up To Date

Github allows for people to track and keep up-to-date with any changes for any repository. If you wish to follow and track the changes that happen on this repo, please leverage the "Watch" feature found at the top of the repository and select "All activity". This will email the user that has "watched" the specific repository.

# Developer Documentation

## Transport mechanism - HTTPS

All machine-readable files must be made available via HTTPS.

## Content type - Non-Proprietary, Open Format

We suggeest the following format to meet the needs for Transparency in Coverage:

* [JSON](https://www.json.org/)

However, equivalent data in a machine-convertable format would be acceptable:

* [XML](http://www.xml.org/)
* [YAML](https://yaml.org/)

Examples of proprietary formats that do *not* meet the requirements:
* [PDF](https://en.wikipedia.org/wiki/PDF)
* [XLS/XLSX](https://en.wikipedia.org/wiki/Microsoft_Excel#File_formats) 

## Public Discoverability

These machine-readable files must be made available to the public without restrictions that would impede the re-use of that information.

The location of the these URLs *must* be provided over HTTPS to ensure the integrity of the data.

## Robots.txt

To allow for search engine discoverability, neither a `robots.txt` file nor `meta` tag on the page where the files are hosted will have rules such that give instructions to web crawlers to not index the page.

This is typically follows the format of `<meta name="robots" content="noindex, nofollow">` or for a `robots.txt` file using the `Disallow` directive.

## Special Data Types

Dates should be strings in [ISO 8601 format](https://en.wikipedia.org/wiki/ISO_8601) (e.g. YYYY-MM-DD).

## Flat File

There is one flat file associated with hospital providers:

* Standard Charges

**Standard Charges**

Under the finalized rules, a hospital must disclose a public list of all standard charges for all items and services.
 

## File Naming Convention  

The following is the required naming standard for each file: `<ein>_<hospitalname>_standardcharges.<file extension>`
For hospital names that have spaces, those spaces would be replaced with dashes `-`

* `<ein>`: Your Hospital’s Employer Identification Number
* `<hospital-name>`: Name of Your Hospital
* `<standardcharges>`: The text `standardcharges`
* `<file extension>`: Your chosen file format, preferably `json`,

## Schema
* [Standard Charges](https://github.com/turquoise-health/provider-price-transparency-guide/tree/master/schemas/standardcharges)

Examples
========
* [Implementation Examples](https://github.com/turquoise-health/provider-price-transparency-guide/tree/master/examples)
