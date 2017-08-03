
![Redivis](https://github.com/redivis/meta/raw/master/logo.png)

#### Copyright Redivis Inc. 2017

develop: [![CircleCI](https://circleci.com/gh/redivis/app/tree/develop.svg?style=shield&circle-token=2c9a6d7cb926d464f11be61469a3074290ae6338)](https://circleci.com/gh/redivis/app/tree/develop)  
production: [![CircleCI](https://circleci.com/gh/redivis/app/tree/production.svg?style=shield&circle-token=2c9a6d7cb926d464f11be61469a3074290ae6338)](https://circleci.com/gh/redivis/app/tree/production)

## Overview  
This repository is for tracking feature requests and reporting issues in [Redivis](https://redivis.com).

## Features / Bugs  
To create a new issue, click on the issues tab, and then click [new](https://github.com/redivis/meta/issues/new) .Please reference and follow the issue template when creating a new issue.

## Releases
Our release history can be found [here](https://github.com/redivis/meta/releases). This will be regularly updated with new features and bug fixes.

## Help  
### Running queries in the project tool  
All queries are run against a BigQuery service, and BigQuery StandardSQL syntax and functions are generally supported (note that BigQuery LegacySQL is not supported). All data types except for Array, Struct, and Timestamp are supported. We recommend consulting the [BigQuery documentation](https://cloud.google.com/bigquery/docs/reference/standard-sql/) for further reference.

There are two notable differences in executing SQL code through the Redivis project tool: 
1) All variables that are referenced from a previous table must be prefixed by `$`. 
2) The name of the table that you are selecting _from_ is auto-populated by Redivis; a Transform may only select against its previous table. This table is represented as two backticks (``` `` ```)    
    
e.g.,   
```sql
SELECT $var1, $var2, $var3 as newVar3 FROM `` WHERE $var4='hello world'
```