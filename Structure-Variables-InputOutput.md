Day 1: Introduction to C Language, Program Structure, Variables, Input and Output
Introduction to C Language

C is one of the most popular and widely used programming languages in the world. It was developed by Dennis Ritchie in 1972 at Bell Laboratories. C is known as a middle-level programming language because it combines the features of both low-level and high-level languages. It provides direct access to memory while also offering easy-to-understand syntax.

Many modern programming languages such as C++, Java, C#, and Python have borrowed concepts from C. Learning C helps students understand how programs work internally and builds a strong foundation for learning data structures, algorithms, operating systems, and other advanced computer science subjects.

Before writing complex programs, it is important to understand the basic structure of a C program and the fundamental concepts used in programming.

Structure of a C Program

Every C program follows a specific structure. The structure helps the compiler understand different parts of the program and execute it correctly.

Consider the following program:

```c
#include <stdio.h>

int main()
{
    printf("Hello World");

    return 0;
}
```

This program may look small, but it contains all the essential components of a C program.

The first line contains #include <stdio.h>. This statement is used to include the Standard Input Output header file. The header file contains predefined functions such as printf() and scanf() which allow us to display output and take input from the user.

The execution of every C program starts from the main() function. The compiler searches for the main() function and begins executing statements written inside it.

The printf() function is used to display information on the screen. In this program, it displays the message "Hello World".

The statement return 0; indicates that the program has executed successfully and is returning control back to the operating system.

Writing Your First Program

The traditional first program in almost every programming language is the Hello World program.

```c
#include <stdio.h>

int main()
{
    printf("Hello World");

    return 0;
}
```

Output:
Hello World

This simple program demonstrates how a message can be displayed on the screen using the printf() function.

Comments in C

Comments are used to add explanations inside a program. They help programmers understand the purpose of different sections of code. Comments are ignored by the compiler and do not affect program execution.

C supports two types of comments.

A single-line comment is used when the explanation is short and occupies only one line.

```c
#include <stdio.h>

int main()
{
    // This program prints a message

    printf("Welcome to C Programming");

    return 0;
}
```

A multi-line comment is used when the explanation spans multiple lines.

```c
#include <stdio.h>

int main()
{
    /*
        This program demonstrates
        the use of multi-line comments
        in C language
    */

    printf("Welcome");

    return 0;
}
```

Comments make programs easier to read and maintain, especially when projects become large.

Variables in C
A variable is a named memory location used to store data. Whenever a program needs to store information such as age, marks, salary, or temperature, variables are used.

Before using a variable, it must be declared with an appropriate data type.

For example: int age;

In this statement, age is the variable name and int specifies that the variable will store integer values.

A variable can also be assigned a value during declaration.
int age = 18;
Here, the value 18 is stored inside the variable age.

Data Types in C
Different types of information require different data types. C provides several built-in data types.

The int data type is used to store whole numbers.

The float data type is used to store decimal values.

The char data type is used to store a single character.

The double data type is used to store large decimal values with higher precision.

The following program demonstrates different data types.

```c
#include <stdio.h>

int main()
{
    int age = 18;
    float percentage = 85.5;
    char grade = 'A';

    printf("Age = %d\n", age);
    printf("Percentage = %.1f\n", percentage);
    printf("Grade = %c\n", grade);

    return 0;
}
```

Output:
Age = 18
Percentage = 85.5
Grade = A

Output in C Using printf()

The printf() function is used to display output on the screen. It is one of the most commonly used functions in C programming.

The following program displays multiple messages.

```c
#include <stdio.h>

int main()
{
    printf("Welcome to C Programming\n");
    printf("This is Day 1 Workshop\n");

    return 0;
}
```

Output:
Welcome to C Programming
This is Day 1 Workshop

The \n symbol is called a newline character. It moves the cursor to the next line after printing text.

Format Specifiers
When displaying variable values, C uses format specifiers.

The format specifier %d is used for integers.

The format specifier %f is used for floating-point values.

The format specifier %c is used for characters.

The following program demonstrates the use of format specifiers.

```c
#include <stdio.h>

int main()
{
    int age = 20;
    float marks = 88.5;
    char grade = 'A';

    printf("Age = %d\n", age);
    printf("Marks = %.1f\n", marks);
    printf("Grade = %c\n", grade);

    return 0;
}
```

Input in C Using scanf()
Programs become useful when they can accept input from users. The scanf() function is used to take input from the keyboard.

The following program takes an integer as input and displays it.

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Your age is %d", age);

    return 0;
}
```

Output:
Enter your age: 19
Your age is 19

The symbol & is called the address operator. It provides the memory address of the variable where the input value will be stored.

Example 1: Addition of Two Numbers
This program takes two numbers from the user and displays their sum.

```c#include <stdio.h>

int main()
{
    int num1, num2, sum;

    printf("Enter first number: ");
    scanf("%d", &num1);

    printf("Enter second number: ");
    scanf("%d", &num2);

    sum = num1 + num2;

    printf("Sum = %d", sum);

    return 0;
}
```

Output:

Enter first number: 10
Enter second number: 20
Sum = 30

Example 2: Area of Rectangle

```c
#include <stdio.h>

int main()
{
    int length, width, area;

    printf("Enter length: ");
    scanf("%d", &length);

    printf("Enter width: ");
    scanf("%d", &width);

    area = length * width;

    printf("Area of rectangle = %d", area);

    return 0;
}
```

Example 3: Average of Three Numbers

```c
#include <stdio.h>

int main()
{
    int a, b, c;
    float average;

    printf("Enter three numbers: ");
    scanf("%d%d%d", &a, &b, &c);

    average = (a + b + c) / 3.0;

    printf("Average = %.2f", average);

    return 0;
}
```

Homework Questions
1.Write a program to calculate simple interest.
2.Write a program to convert rupees into paise.
3.Write a program to calculate the volume of a cuboid.
