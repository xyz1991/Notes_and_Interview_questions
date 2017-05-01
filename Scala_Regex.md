# Scala  
  
## Libraries  
import scala.util.matching.Regex
  
## Matching  
```scala
"ab12".matches("[a-zA-Z0-9]{4}")  
```
  
## Splitting  
```scala
"hello world, this is Al".split("\\s+")  
```  
## Replacement  
```scala
"milk, tea, muck" replaceAll ("m[^ ]+k", "coffee")  
"milk, tea, muck" replaceFirst ("m[^ ]+k", "coffee")  
```  
## Grouping & Extracting  
```scala
val numPattern = "[0-9]+".r  
val address = "123 Main Street Suite 101"  
val match1 = numPattern.findFirstIn(address)  
val matches = numPattern.findAllIn(address)  
matches.foreach(println)  
val matches = numPattern.findAllIn(address).toArray  
```
