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
val result = numPattern.findFirstIn(address).getOrElse("no match")  
```
(OR)  
```scala
scala> val s = "Frank,123 Main,925-555-1943,95122"  
s: String = Frank,123 Main,925-555-1943,95122  
  
scala> val p = """.*,(\d{3})-(\d{3})-(\d{4}),.*""".r  
p: scala.util.matching.Regex = .*,(\d{3})-(\d{3})-(\d{4}),.*  
  
scala> val p(p1,p2,p3) = s  
p1: String = 925  
p2: String = 555  
p3: String = 1943    
```
