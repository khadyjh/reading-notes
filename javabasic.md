## java basic 

java is programing language and development platform it huge language and a i will list in this article it's basic.

**Variables** 

### there is four kind of variable in java 

- instance variable =>declared in a class, but outside a method, constructor or any block Non-static fields=> any field declared with static modifier 
- static variable 
- local variable => variable declared inside the function and used inside it , local variables are only visible to the methods in which they are declared; they are not accessible from the rest of the class
- parameter => variable that declared in function header called parameter 

### there is rules for naming variable  
- variable name is case sensitive, and the name begins with letter or ’ $’ or ’ _’ but it is convention to begin with letter .
- The variable name should be meaningful and avoid cryptic abbreviations .
- if the name consists of one word it should be in lower case, otherwise the second sequence should begin with a capital letter  .

### variable in java statically-typed which means that all variables must first be declared before they can be used.

***example:*** 
```
int count =5;

int speed =0;
```
### Operators
in java we use the operators like other languages .

The assignment operator ‘=’ use to assign value on its right to the operand on its left like .
```
int number = 0;
String car="bmw";
```

the arithmetic operator 

| Operator     | Description|
| -----------  | ----------- |
| +            |   Adding operator |
| -            |         Subtracting operator     |
| *            |     Multiplication operator        |
| /            |    Division operator         |
| %            |     Remainder operator        |

***example:*** 
```
 public static void main(String[] args) {


        int result = 1 + 2;
        System.out.println("1 + 2 = " + result);


        int result1 =3-2;
        System.out.println( " 3-2 = "+ result1);


        int  result2 = 2* 2;
        System.out.println( "2 * 2 = " + result2);


        int result3 =4 / 2;
        System.out.println( "4 / 2 = " + result3);


        int result4 =14% 7;
        System.out.println( " 14% 7 = " + result4);
 }
```

### Control Flow Statements

The statements inside source code files are generally executed from top to bottom, in the order that they appear. Control flow statements, break up the flow of execution by employing decision making, looping, enabling your program to conditionally execute particular blocks of code. This section describes the decision-making statements (if-then, if-then-else, switch), the looping statements (for, while, do-while), and the branching statements (break, continue, return) supported by the Java programming language.

**if-else statement**
conditional statement till the program to execute block of code if condition is true 

```
if (condition)
{
    do some code 
}else{
    do some code 
}
```

**switch Statement**

switch statement can have a number of possible execution paths

```
  public static void main(String[] args) {


     String color="red";
     switch (color){
         case "red":
             System.out.println("the color is red");
             break;
         case "blue":
             System.out.println("the color is blue");
             break;
         default:
             System.out.println("the color is black");
     }
  }
```

**for Statement**

iterate over a range of values ,when you repeat same statement so many times use for loop 

for (initialization; termination; increment) {
   statement(s)
}

```
  public static void main(String[] args) {


        for(int i=1; i<11; i++){
            System.out.println("Count is: " + i);
        }
  }
```
**Compiler**
finally when you want to run your code you need to compile it 
What is a compiler and why use it ?

we write code in human readable language so we need to convert it to binary to the machine language 
the compiler do this work for us 
and the compiler check if you write code without error 
to make sure your program is written correctly according to the rules of the programming language

 in java compiler creates the bytecode instructions. These instructions are stored in .class files and can be executed by the Java Virtual Machine.

