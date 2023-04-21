# Using-R

#install.packages("tidyverse")
library(tidyverse)
#Import data
Data<-read_csv("../applications.csv")

#Exercise 1: Use `ggplot2::` to create a figure showing the relation between department and gender; set all colors to blue. Which departments are relatively popular among male applicants in comparison to female applicants?
Data %>%
group_by(admit)%>%
count(admit)%>%
ungroup()%>%
mutate(perc = n /sum(n))
