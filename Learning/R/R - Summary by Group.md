library(purrr)

df %>% split(.$group) %>% map(summary)