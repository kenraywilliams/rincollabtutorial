#Programming in R - Exercises of basic concepts ============

##Libraries to load and packages to install-----------------

options(repos = c(CRAN = "http://cran.rstudio.com")) 

if (!require(parallel)) install.packages("parallel") 

if (!require(doParallel)) install.packages("doParallel") 

if (!require(foreach)) install.packages("foreach") 

library(parallel) 

library(doParallel) 

library(foreach)


###Exercise I------------------------------------------------

#(a) 
ex1a <- seq(10, 38); ex1a

#[1] 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38

#(b) 
ex1b <- seq(30, 1); ex1b

#[1] 30 29 28 27 26 25 24 23 22 21 20 19 18 17 16 15 14 13 12 11 10  9  8  7  6  5  4  3  2  1

#(c)
ex1c <- c(seq(1, 4), seq(3, 1)); ex1c

#[1] 1 2 3 4 3 2 1

#(d)
ex1d <- seq(2, 20, 2); ex1d

#[1]  2  4  6  8 10 12 14 16 18 20

#(e)
ex1e <- rep(c(1,2,3),10); ex1e

#[1] 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3

#(f)
ex1f <- ex1e[1:28]; ex1f

#[1] 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1 2 3 1

#(g)
ex1g <- paste("label", seq(1,30)); ex1g

#[1] "label 1"  "label 2"  "label 3"  "label 4"  "label 5"  "label 6"  "label 7"  "label 8"  "label 9" 
#[10] "label 10" "label 11" "label 12" "label 13" "label 14" "label 15" "label 16" "label 17" "label 18"
#[19] "label 19" "label 20" "label 21" "label 22" "label 23" "label 24" "label 25" "label 26" "label 27"
#[28] "label 28" "label 29" "label 30"

#(h)
ex1h <- paste("label", seq(1,30), sep="-"); ex1h

#[1] "label-1"  "label-2"  "label-3"  "label-4"  "label-5"  "label-6"  "label-7"  "label-8"  "label-9" 
#[10] "label-10" "label-11" "label-12" "label-13" "label-14" "label-15" "label-16" "label-17" "label-18"
#[19] "label-19" "label-20" "label-21" "label-22" "label-23" "label-24" "label-25" "label-26" "label-27"
#[28] "label-28" "label-29" "label-30"

#(i)
x <- seq(0.1, 1, 0.1)
ex1i <- x^2*exp(x); ex1i

#[1] 0.01105171 0.04885611 0.12148729 0.23869195 0.41218032 0.65596277 0.98673883 1.42434619 1.99227852
#[10] 2.71828183

###Exercise II------------------------------------------------

#first with loop
ans1 <- 0
for (j in 5:23) {
  ans1 <- ans1 + j^2 + 3*sqrt(j)
}; ans1

#[1] 4502.766

#second with loop
ans2 <- 0
for (i in 1:18){
  ans2 <- ans2 + (1.3^i)/i
}; ans2

#[1] 37.23156

#third with loop
ans3 <- 0
for(i in 1:10){
  for(j in 1:6){
    ans3 <- ans3 + (i^4)/(3+j)
  }
}; ans3

#[1] 25222.42

#first without loop
j <- seq(5,23)
sum(j^2 + 3*sqrt(j))

#[1] 4502.766

#second without loop
i <- seq(1,18)
sum((1.3^i)/i)

#[1] 37.23156

#third without loop
i <- seq(1,10)
j <- seq(1,6)
fun <- function(i,j) {(i^4)/(3 + j)}
sum(outer(i, j, fun))

#[1] 25222.42

###Exercise III-----------------------------------------------

#(a)
set.seed(75)
M = matrix(sample(1:10, size=60, replace=TRUE), nrow=6, ncol=10)
M # this creates a random number matrix of size 6x10 with integer values between
#1 and 10, there are 60 total values created.

#(b)


#(c)


###Exercise IV------------------------------------------------

#Write a function which takes a single argument which is a matrix.
#The function must return a matrix which is the same as the function argument but
#every odd number is doubled.





