---
Aliases: library(rvest) example
tags: complete, R
---
Link : [CRAN Vignette](https://cran.r-project.org/web/packages/rvest/vignettes/selectorgadget.html)

```R
# Cast names
length(cast)
cast[1:2]
html_text(cast, trim = TRUE)

# Cast attributes
cast_attrs <- html_attrs(cast)
length(cast_attrs)
cast_attrs[1:2]

# Cast relative url
cast_rel_urls <- html_attr(cast, "href")
length(cast_rel_urls)
cast_rel_urls[1:2]

# Cast absolute url
cast_abs_urls <- html_attr(cast, "href") %>% 
  url_absolute(lego_url)
cast_abs_urls[1:2]
```
