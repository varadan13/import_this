---
title: ""
tags: ""
---

# Instance and class variable

## Instance Variable

-   Instance variables are owned by instances of the class.   
-   This means that for each object or instance of a class, the instance variables are different.   
-   Unlike class variables, instance variables are defined within methods. 


        class Potterhead(object):
          def __init__(self,movie):
            self.movie = movie #instance variable

## Class Variable

-   Class variables are defined within the class construction.  
-   Because they are owned by the class itself, class variables are shared by all instances of the class.   


        class PotterHead(object):
          hero="Dumbeldore"  # class variable
          
          

## Different ways to access Instance Variable in Python

There are two ways to access the instance variable of class:   

-   Within the class by using self and object reference.
-   Using getattr() method
