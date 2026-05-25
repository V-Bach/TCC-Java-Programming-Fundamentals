

# **CONTROL STRUCTURES AND ARRAYS**

**CONTENTS OF THE CHAPTER**

* *Control structure.*

* *Command block.*

* *Conditional structures: if, switch.*

* *Enum data type.*

* *Loop structures: for, while, do...while.*

* *Working with arrays.*

*Chapter 3 covers key topics related to control structures and arrays. Commonly used control structures in Java, such as if...else, switch...case, while, do...while, and for, are illustrated through flow diagrams and visual examples to help readers understand how these structures work and how to write code. Several special data types, such as enumerations (Enum) and arrays, are also discussed in this chapter, further enhancing readers' understanding of data types in Java.*

# **3.1. CONTROL STRUCTURE AND INSTRUCTION BLOCKS**

An **algorithm** can be represented by a **flowchart** . The flowchart of a simple program is shown in **Figure 3-1** . In this case, the program does not use branching or looping; the statements are executed in their entirety, from top to bottom, each statement executed once. However, in reality, problems have much more complex logic. In such cases, branching and looping structures are needed. These structures allow a block of code to be executed, not executed, or executed repeatedly. The number of executions is usually determined by logical expressions.

**Figure 3.1 \-. Flowchart of a simple program execution.**

**A block of code** consists of a sequence of statements enclosed within a pair of curly braces "{" and "}". For example:

| { Command } |
| :---- |

In fact, a block can contain no statements at all; such a block is called **an empty block** and is useful in some cases. A block of code can be used validly anywhere a statement might occur. There is one place where a block is required, and that is in the case of declaring a **method** . In fact, a method is just a **named block of code** . Here are two examples of unnamed blocks of code:

| { System.out.print("The answer is"); System.out.println(traloi); } { int bientam; // Declare temporary variable bientam \= x; // Store the value of variable x in the variable bientam x \= y; // Store the value of variable y in variable x y \= variable\_meta; // Stores the value of variable\_meta into variable y } |
| :---- |

In the second example, a **temporary variable** is declared inside the block. This is perfectly valid, and declaring a variable inside a block ensures that the variable is only **used within that block** . A variable declared inside a block is completely inaccessible and invisible from outside that block. When the computer executes the variable declaration statement, it allocates **memory** to hold the variable's value. When the block finishes, that memory is **reclaimed** .

# **3.2. IF…ELSE CONDITIONAL STATEMENT**

**if** ... **else** " statements . The flowchart of a conditional statement is as follows:

**Figure 3.2 \-. Block diagram of branching structure using the if statement.**

| if (expression){ block of code 1 else{ block of code 2 } |
| :---- |

**if** statement instructs the computer to perform one of two actions, depending on whether the value of a given **expression** is true or false. When the computer executes the if statement, it evaluates the value of the expression. If the value is **true** , the computer executes **block 1\.** If the value of the expression is **false** , the computer skips **block 1** and executes **block 2\.** Note that in all cases, one and only one block of code is executed. An example of an if ... else statement:

| public class Main { public static void main(String\[\] args) { int time \= 22; if (time \< 10\) { System.out.println("Good morning."); } else if (time \< 20\) { System.out.println("Good day."); else { System.out.println("Good evening."); } } } |
| :---- |

The results when running will be displayed:

| Good evening. |
| :---- |

In many cases, if you want to choose between **executing or not executing** a block of code, you can use an **if statement** that omits the **else part.** as follows:

| if (boolean expression) block of commands |
| :---- |

Example of **swapping** **Change x and y** when x is greater than y:

| if ( x \> y ) { int temp; // A temporary variable used within this block. temp \= x; // Store a copy of the value x in the temp variable. x \= y; // Copy the value of y to x. y \= temp; // Copy the value of the temp variable to y. } |
| :---- |

This is an if statement that swaps the values of two variables, x and y, but the swap only occurs if x is greater than y. If x is less than y, the swap does not happen. After this if statement is executed, the value of x will always be less than or equal to the value of y.

## **3.2.1. Notes on the use of parentheses**

For example, suppose you write the following code:

| if (x \> 0\) if (y \> 0\) System.out.println("First case"); Elle System.out.println("Second case"); |
| :---- |

Remember that this **indentation** has no meaning to the computer. You might think that the **else part** is the second half of the "if (x \> 0)" statement, but the rule the computer follows is to attach the **else part** to **"if (y \> 0)"** . In other words, the computer executes the statement as follows:

| if ( x \> 0 ) if (y \> 0\) System.out.println("First case"); Elle System.out.println("Second case"); |
| :---- |

You can force your computer to use the method you want by adding curly braces like this:

| if ( x \> 0 ) { if (y \> 0\) System.out.println("First case"); } Elle System.out.println("Second case"); |
| :---- |

## **3.2.2. Empty statements**

This section will discuss another type of statement in Java: **the empty statement** .

| if (x \< 0\) { x \= \-x; }; |
| :---- |

This is a statement consisting of only a semicolon, and it instructs the computer to do nothing. The existence of the empty statement makes the following statement valid:

| if ( done ) ; // Empty statement Elle System.out.println("Other"); |
| :---- |

It's not possible to omit **the semicolon** in the example above, because Java syntax requires a statement between **the if** and **else statements** . However, it's also possible to use an empty { } block with nothing in between for such cases. Sometimes, empty statements can cause **hard-to-find errors** in the program. For example, the code snippet will always print "Hello" regardless of whether the value of x is greater than or less than 0;

| if (x \< 0); { System.out.println( "Hello"); } |
| :---- |

The reason is that the semicolon at the end of the first line is a statement, and this empty statement is executed. The System.out.println statement isn't actually inside the if statement, so it will always execute in any case.

## **3.2.3. Assigning values in an if statement**

Another point to note is the assignment **of values within the if statement** . Consider the following two code snippets:

| int y;                  int y; if (x \< 0\) { if (x \< 0\) { y \= 1;                  y \= 1; } } else { if (x \>= 0\) { y \= 2;                  y \= 2; } } System.out.println(y);          System.out.println(y); |
| :---- |

In the left-hand version, y is assigned the value 1 if x \< 0 and 2 otherwise. The same applies to the right-hand version. However, in practice, the Java compiler will **report an error for the System.out.println statement** in the right-hand code, while the left-hand code is perfectly fine.

The problem is that in the code on the right, the computer cannot know that **the variable y has definitely been assigned a value** . When the if statement lacks an else part, the statement inside the if may or may not be executed, depending on the value of the condition. The compiler cannot know whether it was executed or not, because the condition will only be evaluated while the program is running. For the code on the right above, as far as the compiler is concerned, it is possible that neither statement, y \= 1 or y \= 2, will be evaluated, so it is possible that the output statement is **trying to print an undefined value** and the compiler considers this an error. The value of a variable can only be used if the compiler can verify that the variable will be assigned a value at that point while the program is running. Note that, in the code snippet on the left above, y is definitely assigned a value, because in an if...else statement, one of the two alternatives will be executed regardless of the value of the condition in the if statement.

Consider another example below. After the code on the left is executed, x is 1; after the code on the right, x is 2\.

| int x; int x; x \= \-1; x \= \-1; if (x \< 0\) if (x \< 0\) x \= 1; x \= 1; else if (x \>= 0\) x \= 2; x \= 2; |
| :---- |

# **3.3. ASSERT STATEMENT**

**assertions** help detect errors by checking code that we believe is correct. An assertion is made using the **\`assert\` keyword** .

Its syntax is:

| assert condition; |
| :---- |

Here, **the condition** is an expression that we assert is true when the program executes. If the assertion is false, an exception will be thrown.

For example:

| String \[\] weekends \= { "Friday" , "Saturday" , "Sunday" }; assert weekends . length \== 2 ; System . *out* .println( "There are " \+ weekends . length \+ " weekends in a week" ); |
| :---- |

In the code above, on the second line, an assertion is made that the length of the **'weekends' array** is 2\. However, since the array is actually 3, an error will occur in the program.

However, this feature only works when the program needs to enable it using the \-ea parameter. In IntelliJ IDEA, to enable this feature, you need to declare **VM options** inside **Run/Debug.** **Configurations** .

![][image1]

**Figure 3.3 \-. Enabling the effect of the assert keyword in IntelliJ IDEA**

# **3.4. The Switch Statement**

## **3.4.1. Traditional switch statement**

**switch** statement allows you to check the values of the same expression and, depending on that value, directly pass the   
corresponding statement and block of code.

**Figure 3.4 \-. Block diagram of the switch statement.**

**switch** statement includes cases **,** which are possible scenarios:

| switch (expression) { Case constant 1: commands 1 Rank; Case constant 2: commands 2 Rank; . . . case constant n: n commands Rank; default: n \+ 1 commands } |
| :---- |

The value of **an expression** can be one of several integer types such as **int** , **short , long** , or **byte** . It can also be another type such as **char** , **string** , or **enum . Importantly, note that the expression cannot be a double** or **float** value . The positions within a **switch statement** that it can jump to when its value equals the constants declared in each **case are specified. Default** labels can also be used. In the switch statement, this provides a default jump point used when the value of the expression is not listed in any of the constants.

**Break** statements The \`break\` clause in **a switch** statement isn't strictly enforced according to the switch statement syntax. Its purpose is to cause the computer to skip the end of the switch statement, ignoring all remaining cases. If the \`break\` clause is omitted, the computer will only resume after completing one case and will execute the statements associated with **that case.** **next** **According to** . Note that multiple labels can be used consecutively, containing different constants. This simply means the computer will jump to the same place and perform the same action as long as the expression has a value equal to one of the labels.

The switch statement above can be replaced with if…else statements   
as follows:

| if (expression \== constant-1) { commands 1 } else if expression \== constant-2) { commands 2 } . . . else if (expression \== constant-n) { n commands } else { n \+ 1 commands } |
| :---- |

**switch** statement can be more efficient than an **if statement** because the computer can evaluate one expression and move directly to the correct case, whereas in an if statement, the computer must evaluate up to N expressions before it knows which set of statements to execute. Here is an example of a **switch statement** :

| public class Main { public static void main(String\[\] args) { int day \= 4; switch (day) { Case 1: System.out.println("Monday"); Rank; Case 2: System.out.println("Tuesday"); Rank; Case 3: System.out.println("Wednesday"); Rank; Case 4: System.out.println("Thursday"); Rank; Case 5: System.out.println("Friday"); Rank; Case 6: System.out.println("Saturday"); Rank; Case 7: System.out.println("Sunday"); Rank; } } } |
| :---- |

The results are displayed:

| England |
| :---- |

## **3.4.2. Enumeration type**

**Listing** type **e num** is a special data type that allows a variable to be a set of predefined constants. For example, suppose the type of the expression is the enumeration type Season, defined by:

| enum Season {SPRING, SUMMER, FALL, WINTER} |
| :---- |

**The type of the expression in a switch statement can be an enumeration type** . In that case, the constants in the case must be values from the enumeration type. As in this case, the constants in **the case** must be selected from the values Season.SPRING, Season.SUMMER, Season.FALL, or Season.WINTER. However, there is one point to note: the enum used in the case only needs to declare a value such as “SPRING”, not the full “Season.SPRING”.   
For example, assuming that **currentSeason** is a variable of type **Season , the** following **switch** statement might be possible :

| switch ( currentSeason ) { WINTER case: System.out.println("December, January, February"); Rank; case SPRING: System.out.println("March, April, May"); Rank; SUMMER case: System.out.println("June, July, August"); Rank; case FALL: System.out.println("September, October, November"); Rank; } |
| :---- |

## **3.4.3. The new switch statement**

**new** version of the **switch statement** has been added in **Java 14\.** The syntax is as follows:

| switch (expression) { case constant-1 \-\> Statement 1; case constant-1 \-\> Statement 2; ... case constant-n \-\> Statement n; default \-\> Statement n+1; } |
| :---- |

For example:

| switch ( N ) { case 1 \-\> System.out.println("Number equals 1"); case 2, 4, 8 \-\> { System.out.println("(Number is a power of 2)"); } case 3, 6, 9 \-\> { System.out.println("Number divisible by 3"); } case 5,7 \-\> System.out.println("The number is 5 or 7"); default \-\> System.out.println("The number is not between 1 and 9"); } |
| :---- |

**The new version** uses the **“arrow” operator** instead of a colon after each case, and the code within a case is either a single statement or a block of statements enclosed in curly braces. A **break statement is not required** , although a break statement can be used to terminate a case early. This avoids the common error caused by **forgotten break statements. Furthermore, instead of allowing only one value per case, it can check for multiple** comma-separated values.

The syntax of the new **switch statement** can also be written as an expression:

| String computerMove \= switch ( (int)(3\*Math.random()) ) { case 1 \-\> "Rock"; case 2 \-\> "Paper"; default \-\> "Scissors"; }; |
| :---- |

A **switch expression** must always evaluate to a value and therefore will almost always have **a default** . The expression within a case can be replaced by a block containing several statements; the value for that case must then be specified by the **yield statement** (such as “yield 42;”) instead of the return statement.

# **3.5. LOOP**

In programming, we often need to perform several operations **repeatedly.** Take, for example, sorting an array of integers. The most well-known algorithm for this is "bubble sort." This algorithm compares the first element of an array with the rest; if they are not in the correct order, it swaps the two elements. This operation is repeated throughout the array until no more swapping is needed. In programming languages, algorithms are often solved using **loops** . Java provides three types of loops: **while** , **do-while** , and **for** , with the for loop seemingly being the most commonly used. While each type of loop has its own advantages, having multiple loop types doesn't necessarily make a language more powerful. Any problem that can be solved using one type of loop can also be solved using another.

## **3.5.1. The while loop**

**while** loop This allows a block of code to be executed multiple times, as shown in the diagram   
below:

**Figure 3.5 \-. Block diagram of the while loop.**

**while** loop can be written as follows:

| while (expression){ block of commands } |
| :---- |

**The block of code** is called the loop body. The loop body is repeated as long as **the expression** remains true. This expression is also known as **the conditional expression** or the loop's **test .**

There are a few points that may need clarification:

* What happens if **the condition is false from the start** , before the loop body is executed even once? In that case, the loop body is never executed.

* What happens if **the condition is true, but then becomes false** somewhere in the middle of the loop body? Does the loop terminate immediately after this happens? No, because the computer continues executing the loop body until it finishes. Only then does it jump back to the beginning of the loop and check the condition, at which point the loop can terminate.

Consider an example using a loop to calculate the average of numbers:

| public static void main ( String \[\] args) {    int inputNumber ; //One of the integers entered by the user.    int sum ; // Sum of positive integers.    int count ; // The number of positive integers.    double average ; // The average value of positive integers. *   *Scanner scanner \= new Scanner( System . *in* );    Initialize the sum and counter variables. *   *sum \= 0 ;    count \= 0 ;    /\* Reads and processes user input. \*/ *   *System.out.print ( " *Enter* the first positive integer: " ) ;    inputNumber \= scanner .nextInt();    while ( inputNumber \!= 0 ) {        sum \+= inputNumber ;        count \++;        System.out.print ( *" Enter* the next positive integer (enter 0 if you want to end):" );        inputNumber \= scanner .nextInt(); }    /\* Display results. \*/ *   *if ( count \== 0 )        System.out.println ( " *You* did not enter any numbers" ) ;    else {        average \= (( double ) sum ) / count ;        System.out.println ( ) *;*        System.out.println ( "You entered a positive integer " \+ count \+ *"* ).        System.out.printf ( "The average of the numbers is %1.3f. *\\* n " , average ) ; } } |
| :---- |

Results after running:

| Enter the first positive integer: 2 Enter the next positive integer (enter 0 if you want to end): 7 Enter the next positive integer (enter 0 if you want to end): 4 Enter the next positive integer (enter 0 if you want to end): 9 Enter the next positive integer (enter 0 if you want to end): 0 You have entered four positive integers. The average number is 5,500. |
| :---- |

**while** loop is often used when the number of iterations is unknown; for example, in the case above, the programmer wouldn't know how many iterations are needed.

## **3.5.2. The do ... while loop**

**do-while** loop This allows a block of code to be executed multiple times, similar to a while loop; however, the condition will be checked later. The diagram is as follows:

**Figure 3.6 \-. Block diagram of the do-while command**

The do...while statement has the following syntax:

| by { Command } while (expression); |
| :---- |

it's more convenient to check the continuation condition at **the end of the loop, rather than at the beginning, as is done in a while loop. The do...while** statement   
is very similar to the while statement, except the word "while," along with the condition it checks, has been **moved to the end** . The word "do" is added to mark the beginning of the loop.

To execute a do...while loop, the computer first executes the loop body, i.e., the statement(s) inside the loop, and then evaluates **the expression** . If the value of the expression is **true** , the computer returns to the beginning of the loop and repeats the process; if the value is **false** , the loop terminates and continues with the next part of the program. Because the condition is not checked until the end of the loop, the do loop body **is always executed at least once** .

Note that there is a semicolon “;” at the end. This semicolon is part of the statement, just like the semicolon at the end of an assignment statement or a declaration is part of a statement. Omitting the “;” will cause a syntax error. In general, every statement in Java ends with a semicolon or right-hand curly brace “}”

Consider another example:

| boolean wantToContinue; // True if the user wants to replay. by { //Play Game ; System.out.print("Do you want to play again?"); wantToContinue \= new Scanner(System.in).nextInt(); } while (wantToContinue \== true); |
| :---- |

Suppose the program allows the user to play a game and asks the player if they want to continue playing at the end of each level (which may result in a win or loss). This statement needs to be modified. Note that this logical expression can also be written concisely as \` **while(wantToContinue)\`** .

## **3.5.3. The for loop**

**for** loop also allows for condition checking and the execution of blocks of code multiple times. It is often used in conjunction with **counter variables** .

**Figure 3.7 \-. Block diagram of the for loop.**

The syntax for a for loop is as follows:

| for(Initialize; Conditional expression; Update){ Command block; } |
| :---- |

**for** loop , the condition must be an expression that evaluates to true or false. Initialization **is** usually a declaration or an assignment statement, but it can be any statement within a program. **Updating** a counter variable is usually an increment or decrement statement; however, any statement can be placed in this position. Similar to a while loop, **the conditional expression** is checked before the code block is executed. If the expression remains **true** , the code block continues **to execute.**

It's important to note that any of the three parts can be left empty. If the condition remains empty, it's treated as "true," so the loop will repeat indefinitely or until it terminates for some other reason, such as a break statement. (Some people prefer to start an infinite loop with "for (;;)" instead of "while (true)".

The most commonly used **for** loop is the **counting loop** , where a loop control variable takes all integer values between a minimum and a maximum number of values. A counting loop has the form:

| for (variable \= min ; variable \<= max ; variable \++) { command } |
| :---- |

In this loop , **min** and **max** are expressions with integer values (usually constants). The variable takes the values min, min \+ 1, min \+ 2, ..., max. The value of the loop control variable is usually used in the loop body. The example below will print the numbers from 0 to 4:

| public class Main { public static void main(String\[\] args) { for (int i \= 0; i \< 5; i++) { System.out.println(i); } } } |
| :---- |

The results are displayed:

| 0 1 2 3 4 |
| :---- |

For various reasons, Java programmers prefer to start counting at 0 instead of 1, and they tend to use “\<” in conditions, rather than “\<=”. It’s easy to count down with a for loop. Just start with 10, decrease the counter variable instead of increasing it, and continue as long as the variable is greater than or equal to 1\. The code would look like this:

| for ( N \= 10 ; N \>= 1 ; N-- ) System.out.println( N ); |
| :---- |

In fact, the official syntax of the for loop actually allows both the initialization and update parts to include several expressions, separated by commas. Therefore, it's even possible to count up from 1 to 10 and count down from 10 to 1 simultaneously. For example:

| for ( i=1, j=10; i \<= 10; i++, j-- ){ System.out.printf("%5d", i); System.out.printf("%5d", j); System.out.println(); } |
| :---- |

Consider another example using a for loop to print the alphabet.

| char ch; for (ch \= 'A'; ch \<= 'Z'; ch \++) System.out.print(ch); System.out.println(); |
| :---- |

## **3.5.4. Nested Loops**

Control structures can **contain** other control structures inside themselves. For example, an **if statement inside a loop** , or a **while loop inside another while loop** . Therefore, it can be said that one structure is **nested** inside another, and there can even be multiple levels of nesting. Java syntax does not set a limit on the number of levels of nesting. Consider an example of printing a multiplication table as follows:

| 1 2 3 4 5 6 7 8 9 10 11 12 2 4 6 8 10 12 14 16 18 20 22 24 3 6 9 12 15 18 21 24 27 30 33 36 4 8 12 16 20 24 28 32 36 40 44 48 5 10 15 20 25 30 35 40 45 50 55 60 6 12 18 24 30 36 42 48 54 60 66 72 7 14 21 28 35 42 49 56 63 70 77 84 8 16 24 32 40 48 56 64 72 80 88 96 9 18 27 36 45 54 63 72 81 90 99 108 10 20 30 40 50 60 70 80 90 100 110 120 11 22 33 44 55 66 77 88 99 110 121 132 12 24 36 48 60 72 84 96 108 120 132 144 |
| :---- |

The data in the table is sorted into 12 rows and 12 columns. You can write code using nested for loops like this to create the table:

| for (int rowNumber \= 1; rowNumber \<= 12; rowNumber++ ) { for (int N \= 1; N \<= 12; N++ ) { System.out.printf( "%4d", N \* rowNumber ); } System.out.println(); } |
| :---- |

# **3.6. BREAK AND CONTINUE**

**while** loop and **do...while loop** allows checking the condition to continue the loop at the beginning or end of the loop. Sometimes, the check is **within...** **A loop** is a more suitable alternative. Java provides a method to exit a loop from any point within the loop body using the **\`break\` and \`continue\` statements** . When the machine encounters a **\`break\` statement** in a loop, it immediately jumps out of the loop. However, if it encounters a **\`continue\` statement** , it returns to check the **conditional expression** without executing the subsequent statements in that loop.

## **3.6.1. The break statement**

**break** statement is used to exit a loop. For example:

| public static void main ( String \[\] args) {    for ( int i \= 0 ; i \< 10 ; i \++) {        if ( i \== 4 ) {            Break ; }        System.out.println *(* i ) ;​ } } |
| :---- |

The example above stops the loop when i \= 4\. The output when run will be:

| 0 1 2 3 |
| :---- |

**\`break\`** statement inside a nested loop, it will only exit that loop, not the outer loop. To **exit a nested loop** from the inside, you need to use **\`break\` followed by the label \`\<div\>\`** , the syntax is as follows:

| Label category; |
| :---- |

In this case, the label is assigned to the outer loop. Consider, for example, a piece of code that checks if two strings, s1 and s2, have a common character:

| String s1 \= "Java laptop" ; String s2 \= "win" ; boolean nothingInCommon \= true ; // Assume s1 and s2 have no characters in common int i \= 0 , j ; // Variables to iterate through the characters in s1 and s2 bigloop: while ( i \< s1 .length()) {    j \= 0 ;    while ( j \< s2 .length()) {         if ( s1 .charAt( i ) \== s2 .charAt( j )) { *// s1 and s2 have a common character             *nothingInCommon \= false ;             System . *out* .println( s1 .charAt( i ));             break bigloop; // Exit BOTH loops         }         j \++; // Go to the next character in s2     }    i \++; // Go to the next character in s1 } System . *out* .println( nothingInCommon ); |
| :---- |

If a common character is found, the value of the variable **nothingInCommon** is set to false, and the search for the common character ends immediately. This \`break\` statement works similarly to the **\`goto\` statement** in some programming languages like C or C++. It's worth noting that **\`goto\`** is also a keyword in Java, but it's not used as a command.

## **3.6.2. The continue statement**

**\`continue\`** statement is used to skip a iteration. For example:

| for (int i \= 0; i \< 10; i++) { if (i \== 4\) { continue; } System.out.println(i); } |
| :---- |

Result:

| 0 1 2 3 5 6 7 8 9 |
| :---- |

**\`continue\`** statement is related to **\`break\`** ; however, instead of jumping out of the loop entirely, it jumps back to the beginning of the loop and continues with the next iteration (including evaluating the loop's continue condition to see if further iterations are needed). Thus, the \` **continue\` statement** instructs the computer to skip the remainder of the current iteration of the loop. Similarly to **\`break\`** , when **\`continue\`** is within a nested loop, it continues the iteration directly containing it; instead, a \` **continue\` label** can be used to continue the iteration of the outer loop.

# **3.7. ARRAY**

## **3.7.1. The concept of arrays**

An array is a **data structure** consisting of a collection of data elements of the same type (numbers, characters, objects, etc.) declared together in a variable. In Java, all elements are **indexed** (starting with 0). The data type of an array can be any valid data type in Java; if it is of the base type int, it is called an "integer array". An array of type String is called a "string array".

We can access array elements through their indices. When using an array in a program, you can use a variable to refer to the entire array. But to refer to individual elements of the array, you need the array name and the element's index. For example, the syntax to refer to an element is as follows: namelist\[7\]. Here, namelist is the variable that names the entire array, and namelist\[7\] refers to the element at index 7 in that array. That is, to refer to an element of the array, use the array name, followed by the element's index enclosed in square brackets.

## **3.7.2. Creating and using arrays**

Arrays are created using the keyword **\`new\`** . For example, to create a String array with 100 elements, you can do the following:

| String\[\] array \= new String\[100\]; |
| :---- |

Before a variable can be used to reference an array, it must be declared and have a type. For example, for a string array, the type for the array variable would be String\[\] and for an int array, it would be int\[\]. Generally, the array type consists of the array type followed by a pair of empty square brackets. Arrays are always created with the array type and size. The length of the array can be provided as an integer or an expression with an integer value. For example, after the assignment statement “A \= new int \[5\];”, A is an array containing five integer elements A\[0\], A\[1\], A\[2\], A\[3\], and A\[4\]. The length of the array list can be obtained by accessing the array's **length property** . For example, to print the length of array A:

| System.out.println(A.length); |
| :---- |

When creating an array, the array elements are allocated space in memory. The elements always contain default values. For example, when creating an int array, each element is automatically initialized to **0\.** A boolean array will have elements with a default value of **false** . And a character array will have a default value of **null** .

## **3.7.3. Array Traversal**

Arrays are often handled with **for loops** . For example, to print all the elements in an array:

| int i; for (i \= 0; i \< list.length; i++) { System.out.println( list\[i\] ); } |
| :---- |

In the first iteration, i is 0 and list\[i\] references list\[0\]. Therefore, the value list\[0\] is printed. The second iteration of the loop, i is 1 and the value stored in the array, list\[1\], is printed. If the length of the list is 5, the loop terminates after printing the value of list\[4\], when i equals 5 and the continue condition **i \< list.length** is no longer true. This is a typical example of using a **for loop** to process an array.

Let's look at a few more examples. Suppose that A is an **array of real numbers** and we want to find the average value of all the elements in the array. We can use a for loop to add the numbers, then divide by the length of the array to get the average value:

| public static void main ( String \[\] args) {    double arr \[\] \= { 64 , 25 , 73 , 64 };    double total ;    double average ;    int i ;    total \= 0 ;    for ( i \= 0 ; i \< arr . length ; i \++ ) {        total \= total \+ arr \[ i \]; }    average \= total / arr . length ;    System . *out* .println( average ); } |
| :---- |

Alternatively, arrays can be manipulated using a "foreach" loop; the syntax for a foreach loop is as follows:

| for ( double e : arr ) { } |
| :---- |

Each iteration of the loop will return an element of the array. For example, find the largest element in the array:

| public static void main ( String \[\] args) {    double arr \[\] \= { 64 , 25 , 73 , 64 };    double max \= arr \[ 0 \]; *   *for ( double e : arr ) {        if ( e \> max ) max \= e ; }    System.out.println *(* max ) ;​ } |
| :---- |

## **3.7.4. Sorting Arrays**

The following program performs sorting of an array:

| public static void main ( String \[\] args) {    int temp ;    int \[\] a \= { 4 , 5 , 3 , 7 , \- 3 , 9 , 7 };    for ( int i \= 0 ; i \< a . length \- 1 ; i \++) {        for ( int j \= i ; j \<= a . length \- 1 ; j \++) {            if ( a \[ i \] \> a \[ j \]) {                temp \= a \[ i \];                a \[ i \] \= a \[ j \];                a \[ j \] \= temp ; } } }    for ( int i \= 0 ; i \< a . length \- 1 ; i \++) {        System . *out* .print( a \[ i \] \+ " " ); } } |
| :---- |

Implement the program:

| \-3 3 4 5 7 7 |
| :---- |

When working with arrays in Java, there is a class called Arrays. This class provides many utilities for arrays; for example, sorting an array and printing it is done as follows:

| int\[\] a \= {4, 5, 3, 7, \-3, 9, 7}; Arrays.sort(a); Arrays.stream(a).forEach(System.out::println); |
| :---- |

## **3.7.5. Two-dimensional arrays**

In a **two-dimensional** , or “2D,” array, elements can be arranged in rows and columns. Here, for example, is a 2D array of int elements with **five rows** and **seven columns** :

|  | 0 | 1 | 2 | 3 | 4 | 5 | 6 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 0 | 58 | 38 | 5 | 58 | \-5 | 56 | 9 |
| 1 | 5 | 8 | 15 | 2 | 88 | \-25 | 69 |
| 2 | \-39 | 7 | \-11 | 55 | 82 | 7 | 37 |
| 3 | 75 | 57 | 7 | 15 | 58 | \-8 | 58 |
| 4 | \-85 | 1 | \-9 | 88 | 8 | 23 | 38 |

This 5 x 7 array contains a total of 35 elements. Declaring this array in Java would be as follows:

| int \[\]\[\] arr \= new int \[ 5 \]\[ 7 \]; |
| :---- |

Two-dimensional arrays are often handled using nested for loops. For example, the following code will print the elements of the array arr:

| for ( int row \= 0 ; row \< 5 ; row \++ ) {    for ( int col \= 0 ; col \< 7 ; col \++ ) {        System . *out* .printf( "%7d" , arr \[ row \]\[ col \] ); }    System.out.println ( ) *;* } |
| :---- |

Two-dimensional arrays have many uses in application design. For example, a 2D array can be used to store the contents of a chessboard in a game like chess or checkers. 2D arrays can also be used to hold the colors of a grid of colored squares.

Consider a company that owns 25 stores. Assume the company has data on the profit earned at each store for each month of 2018\. If the stores are numbered from 0 to 24 and if the twelve months from January 2018 to December 2018 are numbered from 0 to 11, then the profit data could be stored in an array, profit, created as follows:

| double\[\]\[\] profit \= new double\[25\]\[12\]; |
| :---- |

Then, profit\[storeNum\]\[monthNum\] will be the profit earned from storeNum in monthNum. For example, profit\[3\]\[2\] will be the profit earned at store number 4 in month 3\. With this storage method, it is easy to calculate the company's total profit for the whole year from all stores as follows:

| Double Total Profit; int store, month; totalProfit \= 0; for ( store \= 0; store \< 25; store++ ) { for ( month \= 0; month \< 12; month++ ) totalProfit \+= profit\[store\]\[month\]; } |
| :---- |

Sometimes, we only need to process a single row or column of an array, not the entire array. For example, to calculate the total profit a company earned in December (which has a column index of 11), we can use a loop like this:

| Double December Profit; int storeNum; DecemberProfit \= 0.0; for ( storeNum \= 0; storeNum \< 25; storeNum++ ) { DecemberProfit \+= profit\[storeNum\]\[11\]; } |
| :---- |

**PRACTICE**

## **Lesson 1\. Point Conversion Problem**

The following exercise will involve writing a program to perform a point conversion. First, create a Mark class:

| public class Mark {    public static void main(String\[\] args) {        int testscore \= 76 ;        char grade;        if (testscore \>= 90 ) { grade \= 'A' ; } else if (testscore \>= 80 ) { grade \= 'B' ; } else if (testscore \>= 70 ) { grade \= 'C' ; } else if (testscore \>= 60 ) { grade \= 'D' ; else {​ grade \= 'F' ; } System. *out* .println( "Grade \= " \+ grade); } } |
| :---- |

Program implementation results:

| C |
| :---- |

## **Lesson 2\. The problem of months in a year**

Practice with the following switch statement and convert it to the new syntax.

| public class Month {    public static void main(String\[\] args) { System. *out* .print( "Enter a month:" ); Scanner scanner= new Scanner(System. *in* );        int month=scanner.nextInt(); String monthString;        switch (month) {            case 1 : monthString \= "January" ; break ;            case 2 : monthString \= "February" ; break ;            case 3 : monthString \= "March" ; break ;            case 4 : monthString \= "April" ; break ;            case 5 : monthString \= "May" ; break ;            case 6 : monthString \= "June" ; break ;            case 7 : monthString \= "July" ; break ;            case 8 : monthString \= "August" ; break ;            case 9 : monthString \= "September" ; break ;            case 10 : monthString \= "October" ; break ;            case 11 : monthString \= "November" ; break ;            case 12 : monthString \= "December" ; break ;            default : monthString \= "Invalid month" ; break ; } System. *out* .println(monthString); } } |
| :---- |

Run the program, enter the month, and view the results:

| Enter a month: 6 Novel |
| :---- |

## **Lesson 3\. Menu selection using the switch statement**

In command-line programming, menus can be presented as a numbered list of options, and the user can select an option by typing in its number. One application of the switch statement is in processing menus. The menu is a list of options. The user selects one of the options. The computer must respond to each selection, which may be in a different way, as in the following exercise:

| int optionNumber ; Double measurement ; double inches \= 0 ; Scanner scanner \= new Scanner( System . *in* ); System.out.println *(* "What unit of measurement do you want to use? " ) ; System . *out* .println( " 1\. inches" ); System . *out* .println( " 2\. feet" ); System . *out* .println( " 3\. yards" ); System . *out* .println( " 4\. miles" ); System.out.println ( "Option 1-4: *"* ) ; optionNumber \= scanner .nextInt(); switch ( optionNumber ) {    Case 1 :        System.out.println ( " *Enter* length in inches: " ) ;        measurement \= scanner .nextDouble();        inches \= measurement ;        Break ;    Case 2 :        System.out.println ( " *Enter* length in feet: " ) ;        measurement \= scanner .nextDouble();        inches \= measurement \* 12 ;        Break ;    Case 3 :        System.out.println ( " *Enter* length in yards: " ) ;        measurement \= scanner .nextDouble();        inches \= measurement \* 36 ;        Break ;    Case 4 :        System.out.println ( " *Enter* length in miles: " ) ;        measurement \= scanner .nextDouble();        inches \= measurement \* 12 \* 5280 ;        Break ;    default :        System.out.println ( "You need to select 1-4" *)* ; } System.out.println ( "Size: " \+ inches \+ *"* inches" ) ; |
| :---- |

Implement the program above and explain how it works.

## **Lesson 4\. Reverse a string.**

Create a class to reverse the string:

| public class ReverseString {    public static void main(String\[\] args) { String palindrome \= "Java laptop" ;        int len \= palindrome.length();        char \[\] tempCharArray \= new char \[len\];        char \[\] charArray \= new char \[len\];        // put original string in an array of chars *       *for ( int i \= 0 ; i \< len; i++) { tempCharArray\[i\] \= palindrome.charAt(i); }        // reverse array of characters *       *for ( int j \= 0 ; j \< len; j++) { charArray\[j\] \= tempCharArray\[len \- 1 \- j\]; } String reversePalindrome \= new String(charArray); System. *out* .println(reversePalindrome); } } |
| :---- |

Implement the program above and explain how it works.

## **Lesson 5\. String Arrays**

Write a program that takes a number as input and returns the corresponding day of the week:

| public class Day of Week {    public static void main(String\[\] args) { Scanner scanner \= new Scanner(System. *in* ); String\[\] calendarDays \= { "Monday" , "Tuesday" , "Wednesday" , "Thursday" , "Friday" , "Saturday" , "Sunday" }; System. *out* .print( "Input day of week:" );        int dayofweek \= scanner.nextInt(); System. *out* .println( "It is " \+ calendarDays\[dayofweek \- 1 \]); } } |
| :---- |

## **Lesson 6\. The for loop**

The problem of counting the divisors of a number.

| public static void main ( String \[\] args) { long N ;    long testDivisor ;    long divisorCount \= 0 ;    Long number tested ;    while ( true ) {        System . *out* .print( "Enter a positive integer: " );        N \= new Scanner( System . *in* ).nextLong();        if ( N \> 0 )            Break ;        System . *out* .println( "That number is not positive. Please try again." ); }    divisorCount \= 0 ;    numberTested \= 0 ;    for ( testDivisor \= 1 ; testDivisor \<= N ; testDivisor \++) {        if ( N % testDivisor \== 0 )            divisorCount \++;        numberTested \++;        if ( numberTested \== 10000000 ) {            System . *out* .print( '.' );            numberTested \= 0 ; } }    System.out.println ( ) *;*    System . *out* .println( "The number of divisors of " \+ N \+ " is " \+ divisorCount ); } |
| :---- |

## **Lesson 7\. Counting Characters**

Write a program that takes a string of no more than 80 characters and any character as input from the keyboard. Count and print to the screen the number of times that character appears in the input string.

| public static void main(String\[\] args) { String chuoi; char kyTu; int count \= 0; Scanner scanner \= new Scanner(System.in);           // If the input string length is greater than 80, re-enter the length. by { System.out.println("Enter any string: "); string \= scanner.nextLine(); } while (string.length() \> 80);           System.out.println("Enter the character you want to count the number of occurrences of: "); kyTu \= scanner.next().charAt(0);           /\* \* Count and print the number of occurrences of that character in the string \* Iterate from the beginning to the end of the string \* If any character at position i is equal to the character ch, then increment the count variable by 1\. \*/ for (int i \= 0; i \< string.length(); i++) { if (kyTu \== chuoi.charAt(i)) { count++; } }           System.out.println("Number of occurrences of the character " \+ kyTu \+ ) " in the string " \+ string \+ " \= " \+ count); } |
| :---- |

The result after compiling the program:

| Enter any string: Welcome to Java\! Enter the character whose occurrences you want to count: a The number of occurrences of the character 'a' in the string 'Welcome to Java\!' \= 2 |
| :---- |

Write a program that takes any string containing numbers, lowercase letters, and uppercase letters as input from the keyboard. Then, count and print the number of lowercase letters, uppercase letters, and numbers in that string.

| public static void main(String\[\] args) { String chuoi; int soKyTuInHoa \= 0, soKyTuInThuong \= 0, soChuSo \= 0; Scanner scanner \= new Scanner(System.in);           // If the input string length is greater than 80, re-enter the length. by { System.out.println("Enter any string: "); string \= scanner.nextLine(); } while (string.length() \> 80);           // Count and print the number of occurrences of that character in the string // iterate from the beginning to the end of the string // If any character at position i is equal to the character ch, then increment the count variable by 1\. for (int i \= 0; i \< string.length(); i++) { // The \`isUpperCase()\` method is used to check for the character at position i. // Is it an uppercase character or not? if (Character.isUpperCase(sequence.charAt(i))) { soKyTuInHoa++; }               // The \`isLowerCase()\` method is used to check for the character at position i. // Is this a lowercase letter? if (Character.isLowerCase(sequence.charAt(i))) { soKyTuInThuong++; }               // The \`isDigit()\` method is used to check for the character at position i. // Is it a number or not? if (Character.isDigit(sequence.charAt(i))) { soChuSo++; } }           System.out.println("In string " \+ string \+ " has " \+ soKyTuInHoa \+ " uppercase characters," \+ " has " \+ soKyTuInThuong \+ " lowercase characters" \+ " and there is " \+ number \+ " number."); } |
| :---- |

The result after compiling the program:

| Enter any string: Welcome to Java\! The string "Welcome to Java\!" contains 2 uppercase characters, 11 lowercase characters, and 0 numbers. |
| :---- |

**QUIZ**

| What is the correct command to create an array? |  |
| :---- | :---- |
| int arr\[\] \= {2, 4, 5} |  |
| int arr\[\] \= {"0","1","2"} |  |
| int arr\[\] \= \[1, 3, 5\] |  |
| int arr\[\] \= (1, 2, 3\) |  |

| What is the standard syntax for declaring a two-dimensional array? |  |
| :---- | :---- |
| int\[\] arr; arr \= new int\[5\]; |  |
| int\[5\]\[7\] arr; arr \= new int\[\]\[\]; |  |
| int\[\] arr \= new int\[5\]\[7\]; |  |
| int\[\]\[\] arr; arr \= new int\[5\]\[7\]; |  |

| The keyword enum helps to define: |  |
| :---- | :---- |
| Array data type |  |
| String data |  |
| Structured data |  |
| Listed data |  |

| The check expression in a switch statement cannot contain a value: |  |
| :---- | :---- |
| a |  |
| enum |  |
| int |  |
| Balance |  |

| What is the correct statement to declare an enum? |  |
| :---- | :---- |
| enum Season \[SPRING, SUMMER, FALL, WINTER\] |  |
| enum Season "SPRING, SUMMER, FALL, WINTER" |  |
| enum Season (SPRING, SUMMER, FALL, WINTER) |  |
| enum Season {SPRING, SUMMER, FALL, WINTER} |  |

| To exit the outer loop of a nested loop structure, you can use: |  |
| :---- | :---- |
| continue command |  |
| Break command with label |  |
| Unlock order |  |
| Stop order with end position |  |

| A loop that checks a condition before executing a command is a: |  |
| :---- | :---- |
| while |  |
| do while |  |
| for |  |
| loop |  |

| Which array declaration is correct? double \[\] a1 \= new double \[\] { "4.56", 332.267, 7.0, 0.3367, 10.0 }; a a2 \= new String\[\] { "a" , "b" , "c" }; Object \[\] a3 \= new Object\[\] { new Object(), "Love" , 3 };  |  |
| :---- | :---- |
| array a1 |  |
| array a2 |  |
| array a3 |  |
| All arrays are declared with incorrect syntax. |  |

## **PRACTICE EXERCISES**

## **Lesson 1\. Overtime pay calculation problem**

Write a program that asks the user to input the number of working hours and the hourly wage for the employee, then prints out the amount to be paid to that employee. Display warning information for the payroll problem as follows: if the wage paid is lower than the minimum wage (25,000 VND per hour) or if the employee works more hours in a week (40).

## **Lesson 2\. Days of the week**

Write a program that takes a number (1-7) as input, corresponding to the day of the week, and displays the following result:

1: Monday

2: Tuesday

...

7: Sunday

## **Lesson 3\. CozaLozaWoza**

Write a program called **CozaLozaWoza** to print the numbers from 1 to 100 such that there are 11 numbers on each line. The program should also print:

* " **Coza** " represents the positions of numbers that are multiples of 3\.

* " **Loza** " represents the positions of numbers that are multiples of 5\.

* " **Woza** " represents the positions of numbers that are multiples of 7\.

* " **CozaLoza** " replaces the numerical positions with multiples of 3 and 5\.

The results are as follows:

| 1 2 Coza 4 Loza Coza Woza 8 Coza Loza 11 Coza 13 Woza CozaLoza 16 17 Coza 19 Loza CozaWoza 22 23 Coza Loza 26 Coza Woza 29 CozaLoza 31 32 Coza 34 LozaWoza Coza 37 38 Coza Loza 41 CozaWoza 43 44 CozaLoza 46 47 Coza Woza Loza Coza 52 53 Coza Loza Woza Coza 58 59 CozaLoza 61 62 CozaWoza 64 Loza Coza 67 68 Coza LozaWoza 71 Coza 73 74 CozaLoza 76 Woza Coza 79 Loza Coza 82 83 CozaWoza Loza 86 Coza 88 89 CozaLoza Woza 92 Coza 94 Loza Coza 97 Woza Coza |
| :---- |

Suggest:

| public class CozaLozaWoza { public static void main(String\[\] args) {   	int lowerbound \= 1;   	int upperbound \= 110;   	for (int number \= lowerbound; number \<= upperbound; number++) {      	// Print "Coza" if number is divisible by 3      	if (......) {         	System.out.print("Coza");      	}      	// Print "Loza" if number is divisible by 5      	if (......) { System.out.print(.....);      	}      	// Print "Woza" if number is divisible by 7      	10      	// Print the number if it is not visible by 3, 5 and 7      	if (......) {         	10      	}     	Print a space      	10      	// Print a newline if number is divisible by 11      	if (......) {         	System.out.println();      	}   	} } } |
| :---- |

## **Lesson 4\. Fibonacci**

In mathematics, Fibonacci numbers are a sequence of integers of the following form:

| 0 1 1 2 3 5 8 13 24 34 ... |
| :---- |

By definition, the first two numbers in the Fibonacci sequence are 0 and 1, and each subsequent number is the sum of the two preceding numbers. In mathematical terms, the sequence Fn of Fibonacci numbers is defined by the following iterative relationship:

| Fn \= Fn-1 \+ Fn-2 |
| :---- |

With the original value

| F0=0, F1=1 |
| :---- |

Write a program called Fibonacci to display **the first 20 Fibonacci numbers** using a loop (without recursion).

## **Lesson 5\. Random Arrays**

Write a program that randomly fills a 3 x 4 x 6 array, then prints the largest and smallest values in the array.

**REFERENCES**

\[1\] Core Java: Fundamentals (2021) , Cay Horstmann (Oracle Press Java).

\[2\] Head First Java: A Brain-Friendly Guide (2022), Kathy Sierra, O'Reilly Media.

\[3\] Java OOP Done Right: Create object oriented code you can be proud of with modern Java Paperback (2019), Mr Alan Mellor, Mellor Books.

\[4\] Murach's Java Programming (5th Edition) (2017), Joe Murach, Mike Murach & Associates.

\[5\]. Java for Absolute Beginners Learn to Program the Fundamentals the Java 9+ Way.

\[6\]. Modern Java Recipes: Simple Solutions to Difficult Problems in Java 8 and 9 (2017), by Ken Kousen, O'Reilly Media.

\[7\] Effective Java (2018), Joshua Bloch, Addison-Wesley Professional.

[image1]: <data:image/png;base64,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>