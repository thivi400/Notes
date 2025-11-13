# Java Basics   

### Everything is inside a Class   

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Go through my Java notes");
    }
}
```

```public``` → accessible everywhere <br>
```static``` → no object needed <br>
```void``` → no return <br>
```String[] args``` → command-line arguments <br>

### Allowed variable naming
```$myName``` But don't prefer this. <br>
```_myName```
<br>

## 1. Data types

**1. Primitive Data Types:**
Predefined by the Java language. <br>
They **directly store values** and are not objects. <br>

| Data Type | Size (bytes) | Range / Description |
|------------|---------------|----------------------|
| byte | 1 | -128 to 127 |
| short | 2 | -32,768 to 32,767 |
| int | 4 | Common choice for whole numbers |
| long | 8 | Very large whole numbers (requires 'L' suffix, e.g., 100L) |
| float | 4 | Requires 'f' suffix (e.g., 3.14f) |
| double | 8 | **Default** for decimal values |
| boolean | 1 bit (conceptually) | Stores `true` or `false` |
| char | 2 | Stores single characters (e.g., `'A'`) |
<br>

```java
char percentage='%'
char unicodeChar='\u0041'  // Represents 'A'
```
<br>

**2. Non-Primitive (Reference) Data Types:**
Created by the programmer or provided by the Java API. <br>
They **store references to objects** in memory, not the values themselves. <br>

| Concept | Description |
|----------|-------------|
| String | String is a class in Java. |
| Arrays | Collections of elements of the same data type. |
| Classes | User-defined blueprints for creating objects. |
| Interfaces | Abstract types that define a contract for classes to implement. |
<br>

### Default Values : 
Primitive types have default values (e.g., 0 for numeric types, false for boolean).
Non-primitive types have a default value of ```null```.

### var :
```java
var count = 10; // inferred as int
var company = "abc"; // inferred as String
```
```java
System.out.println(company.getClass().getName()  // java.lang.String
```
<br>

## 2. Implicit, Explicit conversion
| Implicit | automatic | ✅ safe | small → big |
|-----------|------------|------|--------------|
| Explicit  | manual     | risky(data loss) | big → small  |

### 🔹 Implicit Conversion (Type Promotion)

```java
int x = 10;
double y = x;   // int → double (automatic)
```

### 🔹 Explicit Conversion (Casting)

```java
double a = 9.7;
int b = (int) a;  // double → int (fraction lost)
```
<br>


```java
12/5    // 2   ie, int/int => int
12/5.0  // 2.4 ie, int/double or double/int => double
12.0/5  // 2.4
```
<br>

## 3. String Pool

Java maintains a special memory area called the String Pool to optimize memory usage for strings. <br>
<br>
String literals (**String**), Java checks the pool. <br>
If the string already exists, it <em >**reuses the reference**</em>. And save memory. <br>
<br>
create with ```new String()```, so they are <em>two different objects</em> on the **heap**. <br>
'==' compares references, which are different, so it prints **false**. <br>

```java
String str1="abc";
String str2= "abc";
System.out.println(str1==str2);    // true

String obj1= new String("xyz");
String obj2= new String("xyz");
System.out.println(obj1==obj2);    //false
```
<br>

To compare the <em>**content of strings**</em>, use .equals() instead of ==.
```java
System.out.println(obj1.equals(obj2));     // true
```
<br>

## 4. string methods

```java
String word1= new String("TVK");
String word2= new String("tvk");
System.out.println(word1.equalsIgnoreCase(word2));    //true
```
<br>

```java
String str1="The sky is red";
String str2="";
System.out.println(str1.length());      //14
System.out.println(str2.isEmpty());     //true
System.out.println(str1.toUpperCase());     //THE SKY IS RED
System.out.println(str1.replace("red","blue"));     //The sky is blue
System.out.println(str1.contains("sky"));       //true
```
<br>

## 5. string format

```println``` → prints a single string <br>
```printf``` → allows format specifiers like %s, %d, %f, %b <br>

```java
String name="Thivi";    // %s
int age=23;     // %d
double gpa=3.45;    // %f
char symbol='%';    // %c
boolean surity=true;    // %b
System.out.printf("My name is %s. I am %d years. My gpa %.2f. These are 100 %c %b",name,age,gpa,symbol,surity);
```
