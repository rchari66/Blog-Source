---
title: "Java Collections"
date: 2019-06-20T19:23:25Z
categories: ["Java"]
draft: false

---

#### **Collections**
* Map entry

	``` java
	  Map<String, String> map = new HashMap<String, String>();
	  for (Map.Entry<String,String> entry : gfg.entrySet())  
            System.out.println("Key = " + entry.getKey() + 
                             ", Value = " + entry.getValue()); 
	```
* Loops
	``` java
	for(String str : strArray) {
		System.out.println(str);
	}
	```
* Array to list
	``` java
	List<Integer> list = Arrays.asList(integerArray)
	```
# List to Array
	``` java
	int[] arr = list.toArray();
	```
* Streams
	``` java
	 Stream<Integer> stream = list.stream();
     List<Integer> evenNumbersList = list.stream()
    								.filter(i -> i%2 == 0)
    								.collect(Collectors.toList());
	```
	```java
	memberNames.stream().filter((s) -> s.startsWith("A"))
                     .map(String::toUpperCase)
                     .forEach(System.out::println);
	```
	``` java
	map.stream().sorted().map(String::toUpperCase).collect(Collectors.toList());
	
	
	// sort and println
	memberNames.stream().sorted()
                    .map(String::toUpperCase)
                    .forEach(System.out::println);
	```
