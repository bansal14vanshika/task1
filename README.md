# task1
grip internship project task 1

The code used in my project for prediction using supervised machine learning


#Importing the data file and reading it from the source

data=read.csv(file.choose(),header=TRUE)
View(data)
print(data)

#Input data visualization

scatter.smooth(x=data$hours,y=data$scores,main="hours~scores")

#Computation and modal training
cov(data$hours,data$scores)
cor(data$hours,data$scores)
x=data$hours
y=data$scores
model=lm(y~x)
model
summary(model)
attributes(model)


#plotting the line of regression that is the line of best fit 
plot(x,y,main="best fit line",xlab="number of study hours",ylab="scores in test")
abline(a=2.484,b=9.776,lty=1,lwd=2,col="blue")

#finding the fitted values of the regressed variable
model$fitted.values

#making prediction
new.hours=data.frame(x=9.25)
predict(model,new.hours)

#thankyou
