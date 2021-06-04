# Peer-graded-Assignment
Peer-graded Assignment: Programming Assignment 2: Lexical Scoping
setwd('E:/Grip/Rpractice')
> ## here we have the set the input x as a matrix
> ##here s value is set to null
> makeCacheMatrix <- function(x = matrix(sample(1:100,9),3,3)) {
     s <- NULL
     set <- function(y) {
        x <<- y
        s <<- NULL
     }
     get <- function() x
  setsolve <- function(solve) s <<- solve
    getsolve <- function() s      list(set = set, get = get,
          setsolve = setsolve,
          getsolve = getsolve)
 }
> ##  changed "mean" to "solve" and "m" to "s"
> cacheSolve <- function(x, ...) {
     s <- x$getsolve()
    if(!is.null(s)) {
         message("getting inversed matrix")
         return(s)
     }
     data <- x$get()
     s <- solve(data, ...)
     x$setsolve(s)
     s
