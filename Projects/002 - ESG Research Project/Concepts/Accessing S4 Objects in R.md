---
tags: stackoverflow, R
---
Link: [Stackoverflow](https://stackoverflow.com/questions/37905556/access-transition-matrix-from-markovchainfit-object)

The estimate object is from a formal S4 class (see e.g. Advanced R by Hadley Wickham for a description of the object systems used in R), which is why in order to access its items you have to use the @ operator instead of the standard $ used for the more common S3 objects.