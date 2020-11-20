# Amandeep-Saini-


# Entering the data
hours <- read.csv("https://raw.githubusercontent.com/AdiPersonalWorks/Random/master/student_scores%20-%20student_scores.csv")
hours

# Splitting the data into training and test data
set.seed(2)
library(caTools)

split <- sample.split(hours, SplitRatio = 0.6)
split
train <- subset(hours, split = "True")
test <- subset(hours, split = "False") 
train
test

# Create the model
Model <- lm(Scores ~. ,  data = train)
summary(Model)

# Prediction
pred <- predict(Model,test)
pred

# Score if he studies 9.25 hours
# y = mx + c
Score <- 9.7758*9.25 + 2.4837
Score
 # The score if a student studies 9.25 hours is 92.90985

#Finding accuracy
rmse <- sqrt(mean(pred-hours$Scores)^2)
rmse
