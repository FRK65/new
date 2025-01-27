# Coding question Helper syntex and methods.

# 1. Map 

**Declaration**
```java
Map<Integer, Integer> countMap = new HashMap<>();
```

**put method** - To add new value with key
```java
countMap.put(key,value);
```

**getOrDefault(key, default value) method**
```java
countMap.getOrDefault(num, 0)
// Here getOrDefault method in Map take 2 args,
// first key and second default value if key is found then it will return value link to key
// Else it return passed default value here default value is 0;
```

**entrySet() method It don’t taken any args**
```java
countMap.entrySet()
// this return a set containing all of the entries in the map
```

***Dislplay Map using Map.Entry<Integer,Integer> entry**
```java
for(Map.Entry<Integer,Integer> entry : map.entrySet())
{
   System.out.println("key "+entry.getKey()+" Value "+entry.getValue());                
}
// Note : Map.Entry<Integer,Integer> entry : map.entrySet()
```
