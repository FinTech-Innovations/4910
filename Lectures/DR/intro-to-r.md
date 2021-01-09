
# What is R?
* R is a dialect of the S language. S language was developed by John Chambers as an internal statistical environment.
* Created in 1991 by Ross Ihaka and Robert Gentlemen. Announced to the public in 1993.
* It is free! Very active and vibrant user community.
* Facilitates data manipulation, calculation, and graphics.
* Base system runs most fundamental functions
    + Need packages for other specific tasks
    + Packages are user contributed.
* More info: https://www.r-project.org/about.html

## Getting started
* Installing R
    + https://www.r-project.org/
  
* Installing R Studio
    + RStudio is a free, open source IDE (integrated development environment) for R
    + User friendly
    + https://www.rstudio.com/products/rstudio/download/
    + We are going to be using R studio to write code
        - script
        - console`
        - environment

* Beginner's guide: https://github.com/dratnadiwakara/fin4820/blob/master/r4beginners_v3.pdf
* Getting started with R: https://support.rstudio.com/hc/en-us/articles/201141096-Getting-Started-with-R
        
In this class we are going to use RStudio Cloud for in-class exercises and assignment. I have sent you an email invitation to join the course home page in RStudio Cloud. You can run everything we do in RStudio Cloud on your local computer.


# R Objects

## RAM and HDD
RAM and HDD, are both types of computer memory. RAM is used to store computer programs and data that CPU needs in real time. It is a working memory of the computer. RAM data is volatile and is erased once computer is switched off. HDD, hard disk has permanent storage and it is used to store user specific data.


## Types of objects
1. character: "LSU"
2. numeric: 5.5342
3. integer: 7
4. logical: TRUE, FALSE or T,F for short
5. factor: categorical variables, male or female



# Interactive Session

## Assignment operator
- `<-` symbol is the assignment operator
```{r}
x <- 1
y <- 2
x+y
text <- "hello"
print(text)
```

- `<-` vs `=`
The operators `<-` and `=` assign into the environment in which they are evaluated. The operator `<-` can be used anywhere, whereas the operator = is only allowed at the top level.<br/>
<br/>
More info:https://stackoverflow.com/questions/1741820/what-are-the-differences-between-and-assignment-operators-in-r

# Vector: a combination of same class
```{r}
a <-c("a","b","c")
print(a)
```

```{r}
b <- 1:10 # : operator is used to create integer sequence
print(b)
print(b[4:8])
```


# List: contains elements of different types
Unlike vectors, a list can contain other lists.

```{r}
block_genesis <-  list(index = 1,
                       timestamp = Sys.time(),
                       data = "Genesis Block",
                       previous_hash = "26cdc16a4560df5fa2fd521dbca22670",
                       new_hash = "2eef25bf0bc4ee81e8c7cd1dfda65855b4b",
                       proof = 1)
```



# R Scripts
* A script is a good way to keep track of what you’re doing
* If you have a long analysis, and you want to be able to recreate it later, a good idea is to type it into a script
* R scripts are saved as ‘.R’ files and can be opened later and rerun the analysis
* Any command that begins with character ‘#’ is ignored when scripts are executed. These are called comments
* To create an R Script use the following steps in RStudio
    - File > New File > R Script
    - Save the file
* To run the script press: Ctrl + Alt + R
* To run a particular line(s), click on the line(s) and press: Ctrl + Enter


## First R Script
```{r}
rm(list=ls()) # clears the memory

# creates a vector of 25 random numbers between 0 and 1
random_data <- runif(25, 0, 1)

# calculate mean
random_data_mean = mean(random_data)

# calculate standard deviation
random_data_sd = sd(random_data)

# print results
print(paste("Mean: ",random_data_mean,", SD: ",random_data_sd))
```


# Control Structures
Control structures allow programmer to control the structure of the program. We are going to talk about `if else`, `for`, `while`, etc. 


# if-else conditions
Suppose you want to assign a credit rating based on the probability of default. If the probability of default is less than 1% the credit rating would be 'A'. If the probability of default is greater than 1% but less than 5% we want to assign a credit rating of 'B'. 5% or greater probability of default would be assigned a rating of 'C'.

```{r}

pd <- 6
creaditrating <- NA

if( pd < 1) {
  creaditrating <- "A"
} else if( pd < 5) {
  creaditrating <- "B"
} else {
  creaditrating <- "C"
}


print(paste("Credit rating is:",creaditrating))
```



# for loop

Print each number in the following vector
```{r}

numbervec <- c(5,7,9)

for( val in numbervec ) {
  print(val*val)
}


```









# Functions
A function is a block of code that is used to perform a task. A function typically takes and input, executes the block of code, and returns a value. <br/>
<br/>
More: https://www.youtube.com/watch?v=Pi0Yf-jn7O8

## A function to add 2 numbers
```{r}
add2 <- function(a,b) {
  output = a+b
  return(output)
}
```


```{r}
add2(2,6)
```
