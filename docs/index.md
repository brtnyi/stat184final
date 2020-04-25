---
title: "Final project report"
author: "Siting Lin, Nitin Jenson, Brittnie Yi"
output: html_notebook
---

### Research Question:

How do external, geographic factors, and pre-existing medical conditions affect the number of cases and death rates from the Coronavirus infection?

### Primary data:

This dataset is taken from https://www.worldometers.info/coronavirus/
The .CSV file for this dataset is called worldomemtersData.csv in the Github Repo.

### Secondary data:

This dataset is taken from https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3551445/
The .CSV file for this dataset is called ICUnumbers.csv in the Github Repo.

This dataset is taken from https://www.kaggle.com/folaraz/world-countries-and-continents-details
The .CSV file for this dataset is called countries and continents.csv in the Github Repo.


```{r}
# Load all packages needed
library(tidyverse)
library(ggplot2)
library(DataComputing)
library(rworldmap)
library(mosaic)
library(readr)
```

```{r}
# This step loads the primary and secondary datasets. Since the primary data will be updated everday, we chose to use data from the day that we finished the preliminary EDA.

file_name <- file.choose() 
Worldmeters_data <- 
  data.table::fread(file_name)  
Worldmeters_data

file_name2 <- file.choose() 
ICUnumbers <- 
  data.table::fread(file_name2)  
ICUnumbers

file_name3 <- file.choose() 
Continents <- 
  data.table::fread(file_name3)  
Continents
```

```{r}
# Inspection of imported data before analysis
# Using the function str() helps us see the structure of each dataset, such as its variables and variable types. 

str(Worldmeters_data)
str(ICUnumbers)
str(Continents)
```