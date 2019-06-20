---
title: "Java Strings"
date: 2019-06-20T19:23:43Z
categories: ["Java"]
draft: true
---

#### **String Methods**
* char charAt(index) : return char at sepecified index
``` java
String str = "techtaste.me";
char c = str.chatAt(0); // returns 't'
```

* bool equals(Object object) : if both string matches.
	``` java
	String str = "techtaste.me";
	string str2 = new String(str);
	
	bool result = str.equals(str2); // returns true
	```
* int length()
* bool equalsIgnoreCase(Object object)
* int compareTo(String str)
* int compareToIgnoreCase(String obj)
* bool startsWith(String substring)
* bool startsWith(String prefix, int offset)
* bool endsWith(String suffix)
* int lastIndexOf(char c) & int lastIndexOf(char c, int offset)
* int lastIndexOf(String substring) & int lastIndexOf(String substring, int offset)
* String contcate(String str)
* String subString(int beginIndex) & String subString(int beginIndex, int endIndex) 
* String contains(CharSequence s)
* String toUpperCase()
* String isEmpty();
* String String.join()
	``` java
	String message = String.join("-", "This", "is", "a", "String");
	``` 
* String replace(String regex, String replacement)
* String replaceAll(String regex, String replacement)
* String[] split(Sring regex, int limit)
* String[] split(Sring regex)
* String.format
	``` java
	String formattedString2 = String.format("My String is %.6f",12.121);
	```
* String trim(); // Returns the substring after omitting leading and trailing white spaces
	``` java
	" Hello World!  ".trim() returns "Hello World!"
	```
* char[] toCharArray()
* String.valueOf(String int)
	``` java
	public static String valueOf(boolean b): Used for converting boolean value to a String
	public static String valueOf(char c): char to String
	public static String valueOf(int i): int to String
	public static String valueOf(long l): long to String
	public static String valueOf(float f): float to String
	public static String valueOf(double d): double to String
	```
* bool matches(String regex)
* byte[] getBytes()

#### Other types to String conversion
* Integer.parseInt(str)
* Long.parseLong(str)

#### Arrays to list
* Arrays.asList(String[])