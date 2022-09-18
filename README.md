# ANA-515-Assignment-2
Loading and describing of biopic dataset


---
title: "ANA 515 Assignment 2"
author: Mohammed Sohail Ameer
output: html_document
date: "2022-09-17"
---

The chosen dataset is describing the accident-prone drivers with various accident reasons are keeping inside the dataset in various states of US. Most of the information is collected from National Highway Traffic Safety Administration and National Association of Insurance Commissioners. The data could be live in a database for analytical purposes. From the data, we observed that 52 numbers of data rows are there which are belongs to 8 numbers of columns. 

```{r}
drivers_data <- read.csv("bad-drivers.csv")
drivers_data
```
```{r}
library("dplyr")
drivers_data <- rename(drivers_data, "num_driver_fatal" = "Number.of.drivers.involved.in.fatal.collisions.per.billion.miles")
drivers_data
```
```{r results = TRUE}

text_tbl <- data.frame( 
Names = c(drivers_data$num_driver_fatal, drivers_data$Percentage.Of.Drivers.Involved.In.Fatal.Collisions.Who.Were.Speeding, drivers_data$Percentage.Of.Drivers.Involved.In.Fatal.Collisions.Who.Were.Alcohol.Impaired), 
Description = c("This column describes the total number of incidents happened", "This column describes the total number of incidents happened for over-speeding", "This column describes the total number of incidents happened for alcohol impairedness")
) 
text_tbl 


```
```{r}

myvars <- c("num_driver_fatal", "Percentage.Of.Drivers.Involved.In.Fatal.Collisions.Who.Were.Alcohol.Impaired", "Percentage.Of.Drivers.Involved.In.Fatal.Collisions.Who.Were.Not.Distracted")
newdata <- drivers_data[myvars]

Summarytable <- summary(newdata)
Summarytable

```


