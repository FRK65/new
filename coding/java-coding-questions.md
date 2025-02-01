
# 1. String Java Coding Questions. 

# 1.1 Reverse a String using StringBuilder class. 

```java
import java.util.Scanner;

public class ReverseString {

     public static void main(String []args){
        System.out.println("Enter String");
        Scanner sc = new Scanner(System.in);
        
        String str = sc.nextLine();
        System.out.println(call(str));
     }
     
     public static String call(String str)
     {
         StringBuilder sb = new StringBuilder("");
         char array [] = str.toCharArray();
         
         for(int i=array.length-1;i>=0;i--)
         {
             sb.append(array[i]);
         }
         return sb.toString();
         
     }
}
```

# 1.2 Reverse a String using StringBuilder class Reverse Function.

```java
import java.util.Scanner;
public class ReverseString{

     public static void main(String []args){
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        System.out.println(call(str));
     }
     
     public static String call(String str)
     {
         StringBuilder sb = new StringBuilder(str);
         return sb.reverse().toString();
     }
}
```

# 2.1 Check if a String is a Palindrome or not using reverse Function.

```java
import java.util.Scanner;
public class Palindrome {

     public static void main(String []args){
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        System.out.println(palindrome(str));
     }
     
     public static String palindrome(String str)
     {
         StringBuilder sb = new StringBuilder(str);
         String rev = sb.reverse().toString();
         if(str.equals(rev))
            return "Palindrom String..";
         else 
            return "Not palindrome String";
     }
}
```

# 2.2 Check if a String is a Palindrom or not using toCharArray() method.

```java
import java.util.Scanner;
public class Palindrome {

     public static void main(String []args){
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        System.out.println(palindrome(str));
     }
     
     public static String palindrome(String str)
     {
         char array [] = str.toCharArray();
         int i=0;
         int k=array.length-1;
         
         while(i<k)
         {
             if(array[i]!=array[k])
                return "Not Palindrom";
             i++;
             k--;
         }
         return "Palindrom";
         
     }
}
```

# 3.1  Count the Number of Occurrences of a Each Character in a String.

```java

import java.util.Scanner;
import java.util.Map;
import java.util.HashMap;
public class Palindrome {

     public static void main(String []args){
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        count(str);
     }
     
     public static void count(String str)
     {
         Map<Character,Integer> map = new HashMap<>();
         for(int i=0;i<str.length();i++)
         {
             char x = str.charAt(i);
             map.put( x , map.getOrDefault( x , 0 ) + 1 );
         }
         
         for(Map.Entry<Character,Integer> ent : map.entrySet())
         {
             System.out.println(ent.getValue()+" "+ent.getKey());
         }
         
     }
}
```

# 4.1 Remove Duplicate Characters from a String

```java
import java.util.Scanner;
import java.util.Map;
import java.util.HashMap;
public class Palindrome {

     public static void main(String []args)
     {
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str = sc.nextLine();
        System.out.println(Remove_Duplicate(str));
     }
     
     public static String Remove_Duplicate(String str)
     {
         StringBuilder sb_new_str = new StringBuilder();
         
         for(int i=0;i<str.length();i++)
         {
             int index = sb_new_str.indexOf(String.valueOf(str.charAt(i)));
             if(index == -1)
                sb_new_str.append(str.charAt(i));
             
         }
         return sb_new_str.toString();
     }
}
```






