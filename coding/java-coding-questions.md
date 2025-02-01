
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

# 5.1 Find the First Non-Repeating Character in a String

My code 
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
        System.out.println(Find_First_unique_char(str));
     }
     
     public static char Find_First_unique_char(String str)
     {
         Map<Character,Integer> map = new HashMap<>();
         
         for(int i = 0; i < str.length(); i++)
         {
             char ch = str.charAt(i);
             map.put( ch , map.getOrDefault( ch , 0 ) + 1 );
         }
         
         for(Map.Entry<Character,Integer> ent : map.entrySet())
         {
             if(ent.getValue()==1)
                return ent.getKey();
         }
         return '\0';
         
     }
}
```

# short code
```java
import java.util.HashMap;

public class FirstNonRepeating {
    public static char firstNonRepeating(String str) {
        HashMap<Character, Integer> map = new HashMap<>();
        for (char c : str.toCharArray()) {
            map.put(c, map.getOrDefault(c, 0) + 1);
        }
        for (char c : str.toCharArray()) {
            if (map.get(c) == 1) {
                return c;
            }
        }
        return '\0'; // Return null character if no non-repeating character found
    }
}
```

# 6. Anagram Check "if two strings are anagrams of each other (i.e., if one string is a rearrangement of the other)."
Example : 
Input: "listen", "silent"
Output: true

# 6.1 first solution using map 

```java
import java.util.Scanner;
import java.util.Map;
import java.util.HashMap;
public class Anagram {

     public static void main(String []args)
     {
        System.out.println("Enter a String..");
        Scanner sc = new Scanner(System.in);
        String str1 = sc.nextLine();
        String str2 = sc.nextLine();
        
        System.out.println(AnagramCheck(str1,str2));
        
     }
     
     public static String AnagramCheck(String str1, String str2)
     {
         Map<Character,Integer> map1 = new HashMap<>();
         Map<Character,Integer> map2 = new HashMap<>();
         
         for(int i=0;i<str1.length();i++)
         {
             char ch = str1.charAt(i);
             map1.put( ch , map1.getOrDefault( ch , 0 ) + 1 );
         }
         
         for(int i=0;i<str2.length();i++)
         {
             char ch = str2.charAt(i);
             map2.put( ch , map2.getOrDefault( ch , 0 ) + 1 );
         }
         
         if(map1.equals(map2))
            return "Anagram strings...";
         else 
            return "No Anagram strings...";
     }
}
```

# 6.1 Second solution using Arrays.sort(arr1,arr2)
```java
// import java.util.Arrays;
     public static String AnagramCheck(String str1, String str2)
     {
            char Array1 [ ] = str1.toCharArray(); 
            char Array2 [ ] = str2.toCharArray(); 
            
            Arrays.sort( Array1 );
            Arrays.sort( Array2 );
            
            if(Arrays.equals( Array1, Array2 ))
                return "Yes Anagram String...";
            else 
                return "No Anagram String...";
     }
```








