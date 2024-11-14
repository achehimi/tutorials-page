# tutorials-page
# R Resources for Working with Dates

This page provides resources and tutorials for working with dates in R.

### Working with Dates in R
- [R for Data Science: Dates and Times](https://r4ds.had.co.nz/dates-and-times.html) - A comprehensive guide to working with dates using `lubridate`.
- [Lubridate Cheatsheet](https://evoldyn.gitlab.io/evomics-2018/ref-sheets/R_lubridate.pdf) - A quick reference for common `lubridate` functions.

### Example Code for Date Operations
```{r}
# Sample code for parsing dates with lubridate
library(lubridate)
date1 <- ymd("2023-01-01")
date2 <- mdy("01-31-2023")
```

### Exercise inspired by the *R for Data Science* book by Hadley Wickham and Garrett Grolemund and covers common date operations in R using the lubridate package. 

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = F, message = F, warning = F)
```

```{r}
library(lubridate)

# Parsing dates from different formats
date1 <- ymd("2023-01-01")        # "2023-01-01" -> YYYY-MM-DD
date2 <- mdy("01-31-2023")        # "01-31-2023" -> MM-DD-YYYY
date3 <- dmy("31-12-2023")        # "31-12-2023" -> DD-MM-YYYY

# Display parsed dates
date1; date2; date3
```

```{r}
# Extracting date components
year(date1)           # Extracts year -> 2023
month(date1)          # Extracts month -> 1 (January)
day(date1)            # Extracts day -> 1
```

```{r}
# Date arithmetic
next_week <- date1 + weeks(1)     # Adds one week to date1
prev_month <- date2 - months(1)   # Subtracts one month from date2

# Rounding dates
rounded_down <- floor_date(date1, unit = "month")   # Floors to start of the month
rounded_nearest <- round_date(date1, unit = "month") # Rounds to the nearest month
rounded_up <- ceiling_date(date1, unit = "month")    # Ceils to start of next month

# Adjusted dates
next_week; prev_month; rounded_down; rounded_nearest; rounded_up
```


Reference: 

Wickham, Hadley, and Garrett Grolemund. *R for Data Science: Import, Tidy, Transform, Visualize, and Model Data.* O'Reilly Media, 2017. Available online at [https://r4ds.had.co.nz/dates-and-times.html](https://r4ds.had.co.nz/dates-and-times.html). 


