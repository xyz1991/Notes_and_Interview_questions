#Java  
  
  
##Libraries  
import java.util.regex.*;   
  
  
##matching  
  
###Util.regex 
String content = "This is Chaitanya " + "from Beginnersbook.com.";  
String pattern = ".\*book.\*";  
boolean isMatch = Pattern.matches(pattern, content);  
(or)  
String content = "This is a tutorial Website!";  
String patternString = ".\*tuToRiAl.\*";  
Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);  
Matcher matcher = pattern.matcher(content);  
boolean isMatched = matcher.matches();  
System.out.println("Is it a Match?" + isMatched);  
  
###From Strings  
"Java is fun".matches("Java.*")  
"440-02-4534".matches("\\d{3}-\\d{2}-\\d{4}")  
  
  
##Splitting  
  
###Util.regex  
String text = "ThisIsChaitanya.ItISMyWebsite";  
String patternString = "is";  
Pattern pattern = Pattern.compile(patternString, Pattern.CASE_INSENSITIVE);  
String[] myStrings = pattern.split(text);  
  
###From Strings  
"Java,C?C#,C++".split("[.,:;?]")  
the regular expression [.,:;?] specifies a pattern that matches ., ,, :, ;, or ?.  
Each of these characters is a delimiter for splitting the string. Thus, the string is split into
Java, C, C#, and C++, which are stored in array tokens.  
  
  
##Replacement  
