# **VARIABLES, CONSTANTS, AND DATA TYPES**

**CONTENTS OF THE CHAPTER**

* *The concepts of constants and variables.*

* *Variable classification.*

* *Naming rules.*

* *Basic data types.*

* *The concept of operators and types of operators.*

*Chapter 2 covers the most fundamental concepts in Java, including constants, variables, data types, and operators. Java also provides rules and conventions for naming conventions such as variable names, class names, method names, and constant names. Adhering to these naming rules helps create valid declarations and makes the source code easier to read and maintain. This chapter also discusses the use of strings, including how to declare and initialize character strings and how to use methods to work with strings. The final part of the chapter covers the use of five common operators in Java: arithmetic operators, assignment operators, comparison operators, logical operators, and conditional operators.*

# **2.1. NAMING IN JAVA**

In the programs, **place** **Names (** also known as **identifiers)** are used to identify different components in a program. These can be variables, functions, classes, objects, methods, etc. A **name** is a string of one or more characters and usually must begin with a letter and typically does not allow special characters.

## **2.1.1. Naming Rules**

Each programming language typically has different naming   
**conventions** . Java also has naming rules that must **be** followed, specifically as follows:

* Do not use keywords **in** the names (refer to the appendix for keyword research).

* **letters** , **numbers** , the dollar sign **($)** , and the underscore **(\_)** are allowed when   
  naming.

* Names **cannot** begin with a number.

Here are some examples of valid naming conventions:

* age

* $salary

* \_structure

* First

* NUMBER 1

Here are some examples of invalid naming conventions:

* 123abc

* Document

* \-salary

* @test

It's important to note that, not just Java, most programming languages don't allow names containing spaces. In that case, "HelloWorld" is a valid identifier, but "Hello World" is not. Java is case-sensitive; therefore, "HelloWorld," "helloworld," "HELLOWORLD," and "hElloWorLD" are all distinct names.

## **2.1.2. Naming Conventions**

Besides the naming conventions that every programmer **must** follow, naming **should also** adhere to the following guidelines:

***Class Naming Convention:***

* It should start with a capital letter.

* It is a noun (like Color, Button, System, Topic).

* Use proper words, instead of abbreviations.

For example:

| class Employee{ } |
| :---- |

***Method naming conventions:***

* Start with a lowercase letter.

* It is a verb like main(), print(), println().

* If the name contains multiple words, start it with a lowercase letter followed by an uppercase letter, such as (camelCase) as in actionPerformed().

For example:

| class Employee{ //method Void draw(){ } } |
| :---- |

***Variable Naming Conventions:***

* Start with a lowercase letter like id, name.

* If the name contains multiple words, start with a lowercase letter followed by an uppercase letter, such as firstName, lastName, etc.

* Avoid using single-character variables like x, y, z, or variables that don't clearly describe their meaning.

For example, declaring a variable as an attribute of the Employee class:

| class Employee{ //variable int id; } |
| :---- |

***Interface Naming Convention:***

* It should start with a capital letter (usually the letter I).

* This is followed by an adjective such as Runnable, Remote, ActionListener.

* Use proper words, instead of abbreviations.

For example:

| interface IPrintable{ } |
| :---- |

***Package Naming Convention:***

* The name should be a lowercase letter like java, lang.

* If the name contains multiple words, they should be separated by dots (.), such as java.util, java.lang.

For example:

| package com.javatpoint; //package class Employee{ } |
| :---- |

***Conventions for naming Hang (Constant):***

* It should be written in capital letters like RED, YELLOW.

* If the name contains multiple words, they should be separated by underscores (\_), such as MAX\_PRIORITY.

For example:

| class Employee{ //constant static final int MIN\_AGE \= 18; } |
| :---- |

# **2.2. VARIABLES **

## **2.2.1. The concept of variables**

A variable is a value **that can change** within a program. A variable is allocated a **memory location** in main memory to store its value. Each variable must be given a unique name (identifier). To declare a variable, you need to specify its data type. For example:

| int x \= 15; |
| :---- |

![A black arrows pointing to a numberDescription automatically generated][image1]

**Figure 2 \-1. Variable accessing a memory region in main memory**

In Java, the only way to put data into a variable is by using **an assignment statement** . An assignment statement uses **the assignment operator** “=” to assign data to a previously declared variable. Variable declarations usually include specifying **the data type** . However, since Java 10, variable declarations can be done with the keyword **\`var\`** . In this case, the variable's type will correspond to the data type assigned to that variable, for example:

| var x \= 15; var y \= 21.2f; |
| :---- |

In Java, there are **three types of variables** :

* Local variable

* Property variables

* Static variables

Examples of declaring and initializing valid variables in Java:

| int a, b, c; // Declare three variables of type int: a, b, and c. int a \= 5, b \= 7; // For example, create a variable byte A \= 11;     // Start creating a byte type variable named A. double pi \= 3.14159; // Declare and assign a value of PI. char nam \= 'b'; // The variable nam is initialized with the value 'a'. |
| :---- |

## **2.2.2 . Local Variables**

**Local variables are** variables declared within methods or code blocks. Local variables are created when these methods or code blocks are called and are automatically destroyed after the methods or code blocks have finished executing. Access modifiers cannot be used for local variables. Local variables are executed internally within the code block. For example, the local variable \` **tuoi\` in** the code below can only work within the \`tuoiCon()\` method:

| public class Test{ public void tuoiCon(){ int age \= 0; age \= age \+ 10; System.out.println("Child's age is: " \+ age); }     public static void main(String args\[\]){ Test test \= new Test(); test.tuoiCon(); } } |
| :---- |

The result when running the program above:

| The child's age is : 10 |
| :---- |

Variables need to be initialized before use. No default values are assigned to local variables, so these variables should be declared and assigned an initial value before use. The following example uses the variable \` **age\`** before initializing it, so it will generate a compile-time error.

| public class Test{ public void tuoiCon(){ int age; age \= age \+ 10; System.out.println("Child's age is : " \+ age); }     public static void main(String args\[\]){ Test test \= new Test(); test.tuoiCon(); } } |
| :---- |

Compilation error message:

| Test.java:4: variable number might not have been initialized age \= age \+ 10; ^ 1 error |
| :---- |

## **2.2.3. Attribute Variables**

**Property variables** are declared within a class, but outside a method. For example, the variables **\`ten\`** and **\`hocphi\`** .

| public class Student{ public String ten; Private double tuition;     public Student (String nameSV){ ten \= tenSV; } public void setHocPhi(double hp){ tuition fee \= salary; } public void inThongTin(){ System.out.println("Name and address: " \+ name ); System.out.println("Course: " \+ course); } public static void main(String args\[\]){ Student sv1 \= new Student("Nguyen Van Doan"); sv1.setHocPhi(4000); sv1.inThongTin(); } } |
| :---- |

The result when running the program above:

| Full name: Nguyen Van Doan Tuition fee: 4000.0 |
| :---- |

**property variables** are created when an object is created using the **\`new\` keyword** and destroyed when the object is destroyed. These properties can be used by all methods, constructors, and code blocks within the class. However, the availability of these properties to other classes depends on the declaration of **access modifiers** .

Objects are allocated space in **the heap memory region** , and their properties are also allocated space regardless of whether they have values or not. When properties are not assigned values, they have **default values** . For numeric properties, the default value is 0; for boolean properties, the default value is false; and for the object itself, it is null. The values of these property variables can be assigned during declaration or in constructor methods.

Properties can be accessed directly **by** calling the variable name within that class. However, from other classes, it must be called using the full, valid name as follows: “Object Name.Property Name”.

## **2.2.4. Static Variables** 

**Static** variables ( **variables )** **A static** variable is declared with the **\`static\` keyword** within a class, but outside of methods, and is typically used as a class variable. Static variables are stored in **the \` static\` domain.** **remember static** (It's part of the heap memory). Static variables are created when the program starts and destroyed when the program ends. This is extremely important because, unlike property variables, static variables **are independent of the object** . The default value of a static variable is the same as that of a property variable. For numeric types, the default value is 0; for boolean types, it's false; and for objects, it's null. Values can be assigned during declaration or within methods. Additionally, values can be assigned within **static methods** . Static variables are rarely used, other than being declared as constants **.** Constants are variables that are declared as static variables and have the keyword \` **final\` added** . Constant variables never change from their initial value.

Static variables can be accessed by calling the class name: “Class name.Static variable name” or “Object name.Static variable name”, however the first method is more accurate.

When declaring static variables using the **\`final\` keyword** , those variables are constants and are usually written in uppercase. Note that Java has the **\`const\` keyword** , but it is not used to declare constants. The example below declares the constant \`FACULTY\`:

| public class Student{ private static double tuition; public static final String FACULTY \= "Faculty"; public static void main(String args\[\]){ Tuition fee \= 4000; System.out.println(FACULTY \+ "average tuition fee: " \+ tuition fee); } } |
| :---- |

Running the program above gives us the following result:

| The average tuition fee for the IT department is 4000\. |
| :---- |

In the example above, there are two static variables, where FACULTY is a constant. If the variables are accessed from an outer class, static variables should be accessed in the form: “Class Name.Static Variable Name”, for example: Student.FACULTY.

# **2.3. DATA TYPES** 

## **2.3.1. Basic Data Types**

**Basic data** types are the simplest data types in Java. At any given time, a basic data type stores only a single value, without any other information. In Java, there are eight basic data types:

**Table 2 \-1. Basic Data Types in Java**

| Data type | Size (bits) | range of values | For example |
| :---: | :---: | :---: | :---: |
| over | 8 | \-128 to 127 | byte byteNumber \= 100; |
| large | 16 | \-32,768 to 32,767 | short shortNumber \= 10000; |
| int | 32 | \-2,147,483,648 to 2,147,483,647 | int intNumber \= 100000; |
| dragon | 64 | \-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | long longNumber \= 100000l; |
| Balance | 32 | 1.4E \-45 to 3.4028235E 38 | float floatNumber \= 9.08f; |
| double | 64 | 4.9E \-34 to 1.7976931348623157E 308 | double doubleNumber \= 9.08; |
| boolean | 1 | true/false (default is false) | boolean boolValue \= true; |
| bra | 16 | 0 to 65,535 | char charValue \= 'a'; |

Data types such as **byte** , **short** , **int** **The \`long\` variable** is used to store integers. The size and range of these variables are shown in the table above.

**Boolean** data type The \`char\` data type is used to store true or false values **.** The **\`** char\` data type, on the other hand, is used to store characters. Unlike C, the \`char\` type uses 16 bits, so it can represent 65,535 different characters.

Any numeric character containing a decimal point is a **double character** . The double type uses 8 bytes, equivalent to 64 bits. Meanwhile, the **float type** , used for floating-point data, is represented by 32 bits, with 1 sign bit, 8 exponent bits, and 23 bits for the numeric part.

To create a float **,** you must add "F" or "f" to the end of the number. For example, "1.2F" is an abbreviation for the value 1.2 in float.

| float income; Income \= 3223.56F; System.out.println(income); |
| :---- |

When the program is run, the result is:

| 3223.56 |
| :---- |

## **2.3.2. The "Wrapper" data type**

In Java, for each basic data type, there is a wrapper **data type . These are called wrappers because they "wrap" the basic data** types within a single object. Therefore, wrappers are data types that can both store single values and have additional methods. Below is a list of wrapper classes corresponding to each basic data type:

**Table 2.2 \-. References to the base data and corresponding Wrapper layers.**

| Basic data types | Corresponding Wrapper Layer |
| :---: | :---: |
| boolean | Boolean |
| bra | Character |
| over | Byte |
| large | Short |
| int | Integer |
| dragon | Long |
| Balance | Float |
| double | Double |

For example, the number 8 can be stored using a basic data type, but it can also be wrapped using the Integer class. In that case, it will be provided with additional important methods. Furthermore, Wrapper classes also have useful methods for working with this data.

| public static void main ( String \[\] args) { String str \= "45" ; Integer x \= Integer. *valueOf* (str);     System . *out* .println( Integer . *toHexString* ( x )); } |
| :---- |

## **2.3.3 . Input and Output of Data Types**

In Java, the most common way to input data from the keyboard is to use a **Scanner object** . The first step is to create a Scanner object named \`print\` to scan data from **\`System.in\`** (the data stream from the keyboard).

| Scanner in \= new Scanner(System.in); |
| :---- |

The next step will be to use the corresponding methods of this Scanner object to input data with different data types. For example:

* Use nextInt() to read an integer.

* Use nextDouble() to read a real number.

* Use next() to read a string.

| int num1; double num2; String str; System. *out* .print( "Enter an integer: " ); num1 \= in.nextInt(); System. *out* .print( "Enter a floating point: " ); num2 \= in.nextDouble(); System. *out* .print( "Enter a string: " ); str \= in.next(); |
| :---- |

Similar to C and C++, Java also uses the " **printf** " method to output data types in a format, for example:

| System. *out* .printf( "%s, Sum of %d & %.2f is %.2f \\n " , str, num1, num2, num1+num2) |
| :---- |

Execute the two code snippets above to input numbers and strings and print the output to the screen; the result will be as follows:

| Enter an integer: 3 Enter a floating point: 2.3 Enter a string: Hello Hello, Sum of 3 & 2.30 is 5.30 |
| :---- |

# **2.4 . CHARACTER STRINGS**

**A string** is a continuous sequence of characters. In Java, the String class is used to create strings. Therefore, it can be seen that String is not a basic data type; it consists of many characters (char) and is understood as a derived data type, created from the basic character data type.

## **2.4.1. Initializing a character string**

**String** object can be created by assigning it a string of characters enclosed in double quotes. For example:

| String s1 \= "Cat"; String s2 \= "Cat"; |
| :---- |

Java uses a String Pool (a special memory area within the Heap) to store strings in order to optimize storage. However, by default, Java does not store all string objects in the String Pool. This is the biggest difference between Java and Java. **Use assignment to create Strings** and use the word \` **new\` to create Strings** . Each time a string constant is created by assigning a value, the JVM first checks the Pool containing the string constant. If the string already exists in the Pool, a reference to the Pool is returned. If the string does not exist in the Pool, a new instance of the string is created and placed in the Pool.

For example, in the above case, **s1 will** create the string "Cat" in the String Pool because that string already exists in the String Pool, so the variable **s2** will reference this string. Meanwhile, if you create a string using the keyword \`new\`, the created string will not be stored in the String Pool. For example:

| String s3 \= new String("Cat"); |
| :---- |

![A diagram of a catDescription automatically generated][image2]

**Figure 2.2 \-. How String Pool works in Heap memory.**

## **2.4.2. Methods for processing character strings**

Java provides several methods for manipulating character strings. The following section will explore the functionality and usage of these methods.

**The format() method** Returns a String object. Use this method to create a formatted string. For example:

| String fs; float floatVar=4.5f; int intVar \= 9; String stringVar="abc"; fs \= String.format("The value of the float variable is " \+ "%f, while the value of the integer variable " \+ "The variable is %d, and the string is " \+ "is %s", floatVar, intVar, stringVar); System.out.println(fs); |
| :---- |

The result when running the program:

| The value of the float variable is 4.500000, while the value of the integer variable is 9, and the string is abc. |
| :---- |

**The \`length()\` method** returns the length of a string by counting the characters in the string. Syntax:

| int length \= string\_name.length(); |
| :---- |

For example:

| public static void main(String\[\] args) { String chuoi; int doDai; Scanner scanner \= new Scanner(System.in);           System.out.println("Enter any string from the keyboard: "); string \= scanner.nextLine();           // calculate string length doDai \= chuoi.length();           System.out.println("String " \+ chuoi \+ " has length \= " \+ doDai); } |
| :---- |

We get the following result when running the program:

| The string "hello" has a length of 5\. |
| :---- |

**concat() method** To concatenate two strings. In fact, Java has two ways to concatenate two strings. The first way is to use the \+ operator, and the second way is to use **the concat() method.**

Syntax:

| String string3 \= string1.concat(String string2); |
| :---- |

For example:

| public static void main(String\[\] args) { String string1 \= "Happy", string2 \= "new year\!"; String string3 \= string1.concat(string2); System.out.println(chuoi3); } |
| :---- |

The result when running the program:

| Happy New Year\! |
| :---- |

**The charAt() method** returns the character in a string according to its index. A string is a collection of characters, and the first character in a string has an index of 0\. For example, if a string has a length of 10, the indices of the characters in that string will be numbered from 0 to 9\. The syntax of the charAt() method is:

| char character \= string.charAt(int index); |
| :---- |

For example:

| public static void main(String\[\] args) { String string \= "Happy new year\!"; char character \= chuoi.charAt(4); // Returns the character with index 4 in the string System.out.println(character); } |
| :---- |

The result after running the program:

| y |
| :---- |

**The compareTo() method** compares two strings, string1 and string2, and returns the result.

* If result \= 0, then the two strings are equal.

* If result \< 0, then string1 \< string2.

* If result \> 0, then string1 \> string2.

Syntax:

| int result \= string1.compareTo(String string2); |
| :---- |

For example:

| public static void main(String\[\] args) { int result; String string1 \= "Happy new year\!"; String string2 \= "Happy new year\!";           result \= string1.compareTo(string2); if (result \== 0\) { System.out.println("String " \+ string1 \+ " \= " \+ string2); } else if (result \< 0\) { System.out.println("String " \+ string1 \+ " \< " \+ string2); else { System.out.println("String " \+ string1 \+ " \> " \+ string2); } } |
| :---- |

Result:

| Happy new year series\! \= Happy new year\! |
| :---- |

**The indexOf() method** returns the position of the first occurrence of string2 in string1. If string2 is not present in string1, the result returned is \-1.

Syntax:

| int result \= string1.indexOf(String string2); |
| :---- |

For example:

| public static void main(String\[\] args) { int result; String string1 \= "Happy new year\!"; String string2 \= "new year\!";           result \= string1.indexOf(string2); System.out.println("First position of string " \+ string2 \+ " in string " \+ string1 \+ " \= " \+ result); } |
| :---- |

Result:

| The first position where the string "new year\!" appears in the string "Happy new year\!" is 19\. |
| :---- |

**The replace() method** will replace the character you want to replace with another character in the string. If the character to be replaced is not present in string1, it will return string1.

Syntax:

| string1.replace(char oldChar, char newChar); |
| :---- |

For example:

| public static void main(String\[\] args) { String string1 \= new String("Happy new year\!");           // The replacement character 'l' is not present in string1 System.out.println(string1.replace('l', 'r'));           // Replace the character 'y' in string1 with 'r' System.out.println("The string after replacement is " \+ string1.replace('y', 'r')); } |
| :---- |

Result:

| Happy New Year\! The replacement string is Happy new rear\! |
| :---- |

**The trim() method** removes leading and trailing spaces from string1. If the string is free of extra spaces, the program returns the original string.

Syntax:

| String string1 \= string1.trim(); |
| :---- |

For example:

| public static void main(String\[\] args) { String string1 \= new String(" Welcome to Vietnam\! "); // Remove extra spaces from string1 string1 \= string1.trim(); System.out.println("The string after removing extra spaces is " \+ string1); } |
| :---- |

Result:

| The string after removing the extra spaces is Welcome to Vietnam\! |
| :---- |

**The substring() method** creates a substring starting at the position with index beginIndex and ending at the position with index endIndex in the parent string.

Syntax:

| String stringChild \= stringParent.substring(int beginIndex, int endIndex); // or from beginIndex to the end of the parent string String stringChild \= stringParent.substring(int beginIndex); |
| :---- |

For example:

| public static void main(String\[\] args) { String string \= new String("Welcome to NEU\!"); String stringCon1 \= stringChain.substring(11); System.out.println(sequenceCon1); } |
| :---- |

Result:

| NEU\! |
| :---- |

Besides the methods above, Java has many other methods for working with strings.

# **2.5. OPERATORS**

## **2.5.1. The concept of operators**

Operators are used to perform operations on variables **and** values **.** In the example below, we use the '+' operator to add two values   
together:

| public class Main { public static void main(String\[\] args) { int x \= 100 \+ 50; System.out.println(x); } } |
| :---- |

Although the '+' operator is commonly used to add two values together, as in the example above, it can also be used to add a variable and a value or a variable and another variable:

| public class Main { public static void main(String\[\] args) { int sum1 \= 100 \+ 50; int sum2 \= sum1 \+ 250; int sum3 \= sum2 \+ sum2; System.out.println(sum1); System.out.println(sum2); System.out.println(sum3); } } |
| :---- |

Result:

| 150 400 800 |
| :---- |

Java divides operators into the following groups:

* Arithmetic operators

* Assignment operator

* Comparison operators

* Logical operators

* Conditional operators

* Bitwise operators

## **2.5.2. Arithmetic Operators**

**Arithmetic operators** are used to perform common mathematical operations .

**Table 2.3 \-. List of arithmetic operators**

| Operator | Describe | For example |
| :---: | :---: | :---: |
| \+ | Add two operands | x \+ y |
| But | Subtract two operands | x \- y |
| \* | Multiply two operands | x \* y |
| / | Divide the two operands | x / y |
| % | Divide and take the remainder. | x % y |
| \++ | Increase the value of the operand by 1\. | \++x |
| \-- | Decrease the value of the operand by 1 unit. | \--x |

## **2.5.3. Assignment Operator**

**Assignment operators** are used to assign values to variables. In the example below, use the assignment operator (=) to assign the value 10 to a variable named x:

| int x \= 10; |
| :---- |

**Table 2 \-4. List of assignment operators**

| Operator | For example | Equivalent |
| :---: | :---: | :---: |
| \= | x \= 5 | x \= 5 |
| \+= | x \+= 3 | x \= x \+ 3 |
| \-= | x \-= 3 | x \= x \- 3 |
| \*= | x \*= 3 | x \= x \* 3 |
| /= | x /= 3 | x \= x / 3 |
| %= | x %= 3 | x \= x % 3 |
| &= | x &= 3 | x \= x & 3 |
| |= | x |= 3 | x \= x | 3 |
| ^= | x \= 3 | x \= x^3 |
| \>\>\> | x \>\>= 3 | x \= x \>\> 3 |

## **2.5.4. Comparison Operators**

**Comparison operators** are used to compare two values.

**Table 2.5 \-. List of comparison operators**

| Operator | Describe | For example |
| :---: | :---: | :---: |
| \== | Comparison of equality | x \== y |
| \!= | Comparison of differences | x \!= y |
| news | Greater than comparison | x \> y |
| \< | Comparison of less than | x \< y |
| \>= | Comparison: greater than or equal to | x \>= y |
| \<= | Comparison: less than or equal to | x \<= y |

## **2.5.5. Logical Operators **

**Logical operators** are used to define logic between variables or values.

**Table 2 \-6. List of logical operators**

| Operator | Describe | For example |
| :---: | ----- | :---: |
| && | Returns true if both operators are true. | x \< 5 && x \< 10 |
| || | Returns true if any of the operators are true. | x \< 5 || x \< 4 |
| \! | Reverse the result | \!(x \< 5 && x \< 10\) |

## **2.5.6. Conditional Expressions**

Any good programming language has a few handy little features that make writing code easier. Java has the Ternary Operator , a **ternary operator** that makes writing if statements more concise. Its structure is as follows:

| Expression? Command 1: Command 2 |
| :---- |

The computer checks the value of **the expression** . If the value is true, it executes **command 1** ; if false, it executes **command 2 .** 

For example:

| next \= (N % 2 \== 0\) ? (N/2) : (3\*N+1); |
| :---- |

The above statement will assign the value N/2 to next if N is even (i.e., if N % 2 \== 0 is true) and it will assign the value (3 \* N \+ 1\) to next if N is odd. (The parentheses in this example are not required, but they make the expression easier to read).

Consider another example:

| public class Main { public static void main(String\[\] args) { int time \= 20; String leads; result \= (time \< 18\) ? "Good day." : "Good evening."; System.out.println(result); } } |
| :---- |

Results after running:

| Good evening. |
| :---- |

## **2.5.7. Bitwise Operators**

**Bitwise operators** are used to work with the single bit value of a number. These operators can be used with integer data types such as int, short, char, long, etc.

| Operator | Describe | For example |
| :---: | :---: | :---: |
| \~ | Reverse the value of the bit. | \~ x |
| & | Returns 1 if there are 2 bits of 1\. | x & y |
| ^ | Returns 1 if the two bits are different. | x ^ y |
| | | Returns 1 if either of the two bits is 1\. | x | y |
| \<\< | Translate the left page bits | x \<\< 2 |
| \>\> | Shift the bits to the right. | x \>\> 2 |

For example:

| int x \= 20 ; *//10100* int y \= 4 ; *//00100* System . *out* .println( "\~x \= " \+ \~ x ); System . *out* .println( "x & y \= " \+ ( x & y )); System . *out* .println( "x ^ y \= " \+ ( x ^ y )); System . *out* .println( "x | y \= " \+ ( x | y )); System . *out* .println( "x \<\< y \= " \+ ( x \<\< y )); System . *out* .println( "x \>\> y \= " \+ ( x \>\> y )); |
| :---- |

Result:

| \~x \= \-21 x & y \= 4 x ^ y \= 16 x | y \= 20 x \<\< y \= 320 x \>\> y \= 1 |
| :---- |

**PRACTICE**

## **Lesson 1\. Identifying information about data types**

This exercise will involve writing code to print the maximum, minimum, and bit length of basic data types. Begin by creating a TypesMinMax class with a main() method.

| public class TypesMinMax {    public static void main(String\[\] args) { } } |
| :---- |

In the main() method, print the Max and Min values of the int type:

| System . *out* .println("int(min) \= " \+ Integer . *MIN\_VALUE* ); System . *out* .println("int(max) \= " \+ Integer . *MAX\_VALUE* ); System . *out* .println( "int(bit-length) \= " \+ Integer . *SIZE* ); |
| :---- |

Print the maximum and minimum values for the byte type:

| System. *out* .println( "byte(min) \= " \+ Byte. *MIN\_VALUE* ); System. *out* .println( "byte(max) \= " \+ Byte. *MAX\_VALUE* ); System. *out* .println( "byte(bit-length)=" \+ Byte. *SIZE* ); |
| :---- |

Print the maximum and minimum values for the short data type:

| System. *out* .println( "short(min) \= " \+ Short. *MIN\_VALUE* ); System. *out* .println( "short(max) \= " \+ Short. *MAX\_VALUE* ); System. *out* .println( "short(bit-length) \= " \+ Short. *SIZE* ); |
| :---- |

Print the Max and Min values of the long type:

| System. *out* .println( "long(min) \= " \+ Long. *MIN\_VALUE* ); System. *out* .println( "long(max) \= " \+ Long. *MAX\_VALUE* ); System. *out* .println( "long(bit-length) \= " \+ Long. *SIZE* ); |
| :---- |

Print the maximum and minimum values of a char type (16-bit character or 16-bit unsigned integer):

| System.out.println("char(min) \= " \+ (int)Character.MIN\_VALUE); System.out.println("char(max) \= " \+ (int)Character.MAX\_VALUE); System.out.println("char(bit-length) \= " \+ Character.SIZE); |
| :---- |

Print the maximum and minimum values of a float type:

| System. *out* .println( "float(min) \= " \+ Float. *MIN\_VALUE* ); System. *out* .println( "float(max) \= " \+ Float. *MAX\_VALUE* ); System. *out* .println( "float(bit-length) \= " \+ Float. *SIZE* ); |
| :---- |

Print the maximum and minimum values for a double data type:

| System. *out* .println( "float(min) \= " \+ Float. *MIN\_VALUE* ); System. *out* .println( "float(max) \= " \+ Float. *MAX\_VALUE* ); System. *out* .println( "float(bit-length) \= " \+ Float. *SIZE* ); |
| :---- |

When you execute the program, the output will show information about the base data type:

| int(min) \= \-2147483648 int(max) \= 2147483647 int(bit-length) \= 32 byte(min) \= \-128 byte(max) \= 127 byte(bit-length)=8 short(min) \= \-32768 short(max) \= 32767 short(bit-length) \= 16 long(min) \= \-9223372036854775808 long(max) \= 9223372036854775807 long(bit-length) \= 64 char(min) \= 0 char(max) \= 65535 char(bit-length) \= 16 float(min) \= 1.4E-45 float(max) \= 3.4028235E38 float(bit-length) \= 32 |
| :---- |

## **Lesson 2\. Comparing strings**

Create a StringTest class with the main() method:

| public class StringTest {    public static void main(String\[\] args) { } } |
| :---- |

Perform string declarations and comparisons:

| String s1 \= "Cat" ; String s2 \= "Cat" ; String s3= new String( "Cat" ); String s4 \= "Dog" ; String s5 \= "CAT" ; System.out.println *(* s1==s2); System.out.println *(* s1==s3); System. *out* .println(s1.equals(s2)); System. *out* .println(s1.equals(s3)); System. *out* .println(s1.equals(s5)); System. *out* .println(s1.equalsIgnoreCase(s5)); |
| :---- |

Check the printed output:

| true false true true false true |
| :---- |

## **Lesson 3\. Operators**

Create the OpTest class. Declare and initialize the variables:

| int age \= 18; Double weight \= 71.23; int height \= 191; boolean married \= false; boolean attached \= false; char gender \= 'm'; |
| :---- |

Check the relational and logical operators:

| System.out.println(\!married && \!attached && (gender \== 'm')); System.out.println(married && (gender \== 'f')); System.out.println((height \>= 180\) && (weight \>= 65\) && (weight \<= 80)); System.out.println((height \>= 180\) || (weight \>= 90)); |
| :---- |

Implement the program and check the results:

| true false true true |
| :---- |

**QUIZ**

| What is the appropriate data type for the number 20.15? |  |
| :---- | :---- |
| dragon |  |
| large |  |
| Integer |  |
| Balance |  |

| The assignment operator is used to: |  |
| :---- | :---- |
| Assign a value to a variable |  |
| Assign a statement to a method |  |
| Assign a name to a value. |  |
| Assign a value to an expression |  |

| The byte data type has the following range: |  |
| :---- | :---- |
| 0 to 256 |  |
| From 0 to 128 |  |
| From 0 to 8 |  |
| From \-128 to 127 |  |

| A variable in Java can contain: |  |
| :---- | :---- |
| The $ character |  |
| The @ symbol |  |
| The character \- |  |
| The % symbol |  |

| The keyword/break statement is used to: |  |
| :---- | :---- |
| Break a block of code |  |
| Skip a loop |  |
| Exiting a loop or switch block |  |
| End a branching order |  |

| Which one is NOT a Wrapper class? |  |
| :---- | :---- |
| Integer |  |
| Byte |  |
| a |  |
| Float |  |

| Declare a constant using the keyword: |  |
| :---- | :---- |
| static |  |
| final |  |
| const |  |
| front |  |

| How many bytes does a double variable use? |  |
| :---- | :---- |
| 2 |  |
| 4 |  |
| 8 |  |
| 16 |  |

| The Scanner object is used for: |  |
| :---- | :---- |
| Search for information from variables |  |
| Scan for potential errors. |  |
| Scan data from an input stream. |  |
| Retrieving information from the array |  |

| A package name may contain: |  |
| :---- | :---- |
| The period. |  |
| Exclamation mark\! |  |
| Curly brackets {} |  |
| Percentage symbol (%) |  |

| What is the result when the following code is executed ? int a \= \- 10 ; int b \= a \< 0 ? \- a : a ; System.out.println("a \= " \+ b);  |  |
| :---- | :---- |
| b \= \-10 |  |
| b \= 10 |  |
| b \= 0 |  |
| b \= 1 |  |

| What is the output of the following code snippet ? for ( int i \= 0 ; i \< 26 ; i \++) {     char letter \= ( char ) ( 'a' \+ i );     System . *out* .println( letter ); }  |  |
| :---- | :---- |
| Display 25 letters a |  |
| Display the 26 letters a |  |
| Display the alphabet |  |
| A compilation error occurred. |  |

| What is the output of the following code snippet ? short high \= Short . *MAX\_VALUE* ; short low \= Short . *MIN\_VALUE* ; System.out.println(high \- low);  |  |
| :---- | :---- |
| 32767 |  |
| 0 |  |
| 65534 |  |
| 65535 |  |

| What is the output of the following code snippet ? String strObj \= new String( "NEU" ); String str \= "NEU" ; System.out.println(strObj.equals(str));  |  |
| :---- | :---- |
| Print: true |  |
| print: false |  |
| Compilation error |  |
| print the word NEU |  |

| What is the result of executing the following code? String strObj \= new String( "NEU" ); String str \= "NEU" ; System.out.println(str \== strObj);  |  |
| :---- | :---- |
| Print: true |  |
| print: false |  |
| Compilation error |  |
| print the word NEU |  |

## **PRACTICE EXERCISES**

## **Lesson 1\. Calculating Taxes**

The sales tax on each product is 8.25%. Write a program that takes the initial **price of a product as input and prints the amount to be paid for the tax** and **the price after** the tax is applied.

## **Lesson 2\. The Overtime Payment Problem**

Write a program that prompts the user to input **the number of working hours** and **the hourly rate** . Then, calculate and print **the total amount payable** to that employee.

## **Lesson 3\. Converting Centimeters to Inch**

Knowing that 2.54 cm \= 1 inch, write a program to convert a number from **cm** to **inches** . The user will input the length in **cm** , and the program will display the result after conversion to **inches** .

**REFERENCES**

\[1\] Core Java: Fundamentals (2021) , Cay Horstmann (Oracle Press Java).

\[2\] Head First Java: A Brain-Friendly Guide (2022), Kathy Sierra, O'Reilly Media.

\[3\] Java OOP Done Right: Create object oriented code you can be proud of with modern Java Paperback (2019), Mr Alan Mellor, Mellor Books.

\[4\] Murach's Java Programming (5th Edition) (2017), Joe Murach, Mike Murach & Associates.

\[5\]. Java for Absolute Beginners Learn to Program the Fundamentals the Java 9+ Way.

\[6\]. Modern Java Recipes: Simple Solutions to Difficult Problems in Java 8 and 9 (2017), by Ken Kousen, O'Reilly Media.

\[7\] Effective Java (2018), Joshua Bloch, Addison-Wesley Professional.

[image1]: <data:image/png;base64,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>

[image2]: <data:image/png;base64,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>