---
aliases:
tags: wip, R, package
---
Link: [Reference](https://lubridate.tidyverse.org/reference/index.html), [Vignette](https://cran.r-project.org/web/packages/lubridate/vignettes/lubridate.html)

# Lubridate Package

### Date/time parsing
| Function                                                                                                                   | Details                                                                                                  |
| :------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| ymd() ydm() mdy() myd() dmy() dym() yq()                                                                                   | Parse dates with **y**ear, **m**onth, and **d**ay components                                             |
| ymd_hms() ymd_hm() ymd_h() <br> dmy_hms() dmy_hm() dmy_h() <br> mdy_hms() mdy_hm() mdy_h() <br> ydm_hms() ydm_hm() ydm_h() | Parse date-times with **y**ear, **m**onth, and **d**ay, **h**our, **m**inute, and **s**econd components. |
| ms() hm() hms()                                                                                                            | Parse periods with **h**our, **m**inute, and **s**econd components                                       |
| parse_date_time() parse_date_time2() fast_strptime()                                                                       | User friendly date-time parsing functions                                                                |
| guess_formats()                                                                                                            | Guess possible date-times formats from a character vector                                                |

### Setting, getting, and rounding
| Function                                                                                     | Detail                                             |
|:-------------------------------------------------------------------------------------------- |:-------------------------------------------------- |
| year() `year<-`() isoyear() epiyear()                                                        | Get/set years component of a date-time             |
| quarter() semester()                                                                         | Get the fiscal quarter and semester of a date-time |
| month() `month<-`()                                                                          | Get/set months component of a date-time            |
| week() `week<-`() isoweek() epiweek()                                                        | Get/set weeks component of a date-time             |
| day() mday() wday() qday() yday() <br> `day<-`() `mday<-`() `qday<-`() `wday<-`() `yday<-`() | Get/set days component of a date-time              |
| hour() `hour<-`()                                                                            | Get/set hours component of a date-time             |
| minute() `minute<-`()                                                                        | Get/set minutes component of a date-time           |
| second() `second<-`()                                                                        | Get/set seconds component of a date-time           |
| tz() `tz<-`()                                                                                | Get/set time zone component of a date-time         |

### Date-time helpers

### Durations

### Periods

### Intervals

### Timespans

### Formatters

### Other modification functions

### Other date-time components

