## Clarifying instructions: https://github.com/DanieleP/PA2-clarifying_instructions
## https://github.com/lgreski/datasciencectacontent/blob/master/markdown/rprog-breakingDownMakeVector.md


# 1. MakeVector is a function that stores a list of functions. I had no idea it was
# possible. Here is an easier example of a function that stores functions:
  

##function plusFunctions stores two functions
# plustwo() : sums 2 to the given value
# plusthree() : sums 3 to the given value

plusFunctions <- function (){
  
    plustwo <- function(y) { 
      x <- y + 2 
      return(x) 
    } 
    
    plusthree <- function(y) {
      x <- y + 3 
      return(x) 
    } 
  #the following line stores the two functions: list(plustwo = plustwo, plusthree = plusthree) }
}

a <- plusFunctions()

a$plustwo(5) #  [1] 7 
a$plusthree(5) #[1] 8


# 2. To use the functions stored in the main function, you need to subset the main
# function. To do this, you need the name of the main function + "$" + the name
# of the second function + (arguments)

install.packages("pryr")

# a <- plusFunctions() a$plustwo(5) [1] 7 a$plusthree(5) [1] 8


makeVector <- function(x = numeric()) {
    m <- NULL
    set <- function(y) {
          x <<- y
          m <<- NULL
  }
    get <- function() x
    setmean <- function(mean) m <<- mean
    getmean <- function() m
    list(set = set, get = get,
       setmean = setmean,
       getmean = getmean)
}

cachemean <- function(x, ...) {
  m <- x$getmean()
  if(!is.null(m)) {
    message("getting cached data")
    return(m)
  }
  data <- x$get()
  m <- mean(data, ...)
  x$setmean(m)
  m
}

a <- makeVector(c(5,1,3))
a$get()
a$getmean()
cachemean(a)


a <- makeVector(c(1,2,3,4))
cachemean(a)

