library(tidyverse)
library(magrittr)

raw <- read.csv("data/raw/datadownload.csv")


raw %<>% select(c(4, 6, 7:14)) 

raw %<>% mutate(health = select(., c(4:6)) %>% rowSums(na.rm = TRUE))
  
# for some reason the following line of code did not work with mutate
raw$rec <-  raw %>% select(., c(8:9)) %>% rowSums(na.rm = TRUE) 

raw %<>% select(c(1:3, 7, 10:12))

names(raw) <- c("town", "pop", "police", "welfare", "housing", "health", "rec")

write.csv(raw, "data/processed/town_budget.csv")

