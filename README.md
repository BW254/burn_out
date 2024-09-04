# Background
Burnout rate is defined as an occupational phenomenon arising from unmanaged, chronic workplace stress (WHO, 2019). Burnout (with regards to an employee) is characterized by exhaustion, downturn in professional efficacy, and increasingly negative feelings toward their job.  
## Problem
There are a number of factors that are believed to cause burnout. Burnout has negative effects on employees and firms that they work in. Burnout can lead to depression, poor health and strains in marriages or family. Burnout can also lead to reduced employee productivity at work, high worker turnover rate, absenteeism, etc. As such, it is important to identify factors that accelerate burnout rate at work in order to mitigate these vices.
## Purpose
Some of the potential predictors for burnout rate include gender, company type, work-from-home availability, designation, resource allocation, and mental fatigue. The purpose of this study is to identify the true predictors of burnout rate with the aim of developing a model that can predict the burnout rate given some values of the predictor variables.
# Data Preprocessing
install required packages-
``` R
install.packages("pdp")
install.packages("vip")
install.packages("gbm")
install.packages("glmnet")
install.packages("caret")
install.packages("psych")
install.packages("corrplot")
install.packages("randomForest")
install.packages("ROCR")
install.packages("Metrics")
library(Metrics)
library(psych)
library(tidyverse)
library(rpart)
library(rpart.plot)
library(dplyr)
library(gbm)
library(vip)
library(pdp)
library(mice)
library(magrittr)
library(caret)
library(glmnet)
library(corrplot)
library(randomForest)
library(ROCR)
```
Import the dataset and observe the descriptives-
```
setwd("C:/Users/ADMN/Desktop/random forest")
burnout<-read.csv("dataset.csv",header = TRUE,sep = ",")
psych::describe(burnout)
md.pattern(burnout)
```
## Descriptives and missing values
![Descriptives](https://github.com/user-attachments/assets/edbb0926-648b-4da5-9c40-a90528d755e0)

The first 6 variables (columns) are complete considering that n = 22750, while the last 3 variables have missing records.

![Missing values](https://github.com/user-attachments/assets/006218ea-8c1b-4087-a2f8-4bf41d4c9274)

### Interpretation
Missing values are from the last three columns (variables). The last column, Burn.Rate, has 2117 missing values, followed by Mental.Fatigue.Score with 1381, and Resource.Allocation with 1124 missing values. Based on the plot, there are 15 instances where each of these variables missed 3 records, 88 instances where  Mental.Fatigue.Score and Resource.Allocation missed 2 records, etc. 






















