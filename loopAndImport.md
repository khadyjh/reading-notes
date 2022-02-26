# Arrays, Loops, Imports

## Packages and Import
package : it is like directory (folder) holds all the file in your project,it named by the of the folder that contain java classes 

package name declare in the top of the java file before anything else  then after it you can import other classes you want to use in your program 

**like that =>**

```
package basiclibrary;


import java.util.ArrayList;
import java.util.Arrays;
import java.util.Random;
```

**you can use the import inside the class like that =>**

```
class ImportRandome {
    public static void main(String[] args) {
     java.util. Random rand = new Random();
     int randomRollNum = 1 + rand.nextInt((6 - 1) + 1);
     System.out.println(randomRollNum);

        
    }
}
```

but it best practices to import it in the top after package declaration 

also you can use multiply sign “*” to import all the classes in one time and it will not affect the project size
**like that =>**

```
import java.util.*;
```

## Loops
**'looping is a feature which facilitates the execution of a set of instructions until the controlling Boolean-expression evaluates to false.'**

there are three type of loops :

- the Simple for loop
```
for (initialization; Boolean-expression; step) 
  statement;

  ```
**example :**

```
int sum=0;
for (int index = 0; index < num.length; index++) {
   sum +=num[index];
}
```
the index will increase in each iterate until reach the condition and break the loop 

-  Enhanced for Loop =>Foreach

**' For each element in items, assign the element to the item variable and run the body of the loop.'**

**example :**
```
int[] intArr = { 0,1,2,3,4 }; 
for (int num : intArr) {
    System.out.println("Enhanced for-each loop: i = " + num);
}

```

- While Loop

in the while loop the boolean expression declare out while block and changed in the end of while block 

**example :**
```
int i = 0;
while (i < 5) {
    System.out.println("While loop: i = " + i);
      i++;
}
```

- Do-While Loop

same as while loop expect that the code block will execute one time before check the condition 

**example :**
```
int i = 0;
do {
    System.out.println("Do-While loop: i = " + i++);
} while (i < 5);
```

resources =>

[Loops](https://www.baeldung.com/java-do-while-loop)

[Packages and Import](https://perso.ensta-paris.fr/~diam/java/online/notes-java/language/10basics/import.html)