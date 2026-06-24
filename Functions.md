Day 4: Functions in C

Introduction to Functions
As programs become larger, writing all the code inside the main() function makes the program difficult to read, understand, and maintain. A better approach is to divide a large problem into smaller parts and solve each part separately. In C, this is achieved using functions.

A function is a block of code designed to perform a specific task. Instead of writing the same code multiple times, a function can be created once and used whenever needed. Functions improve code reusability, readability, debugging, and maintenance.

For example, if a program needs to calculate the sum of two numbers several times, we can create a function that performs the addition and call it whenever required.

Why Do We Need Functions?
Consider a program that calculates the area of a rectangle multiple times.

Without functions, the same logic would need to be written repeatedly, making the program longer and harder to manage.

Functions help solve this problem by allowing programmers to write the logic once and reuse it multiple times.

Functions are one of the most important concepts in programming because they help organize programs into smaller and manageable modules.

Built-in Functions
C provides many predefined functions through header files.

Some common built-in functions are:

printf() for displaying output.
scanf() for taking input.
sqrt() for finding square roots.
pow() for calculating powers.

The following program uses built-in functions.

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    printf("Age = %d", age);

    return 0;
}
```

In this example, both printf() and scanf() are predefined functions available in the Standard Input Output library.

User Defined Functions
Apart from built-in functions, programmers can create their own functions according to their requirements. These functions are called user-defined functions.

The following program demonstrates a simple user-defined function.

```c
#include <stdio.h>

void display()
{
    printf("Welcome to C Programming");
}

int main()
{
    display();

    return 0;
}
```

Output:
Welcome to C Programming

The function display() is created by the programmer and called from the main() function.

Components of a Function
A function generally consists of three parts:
Function Declaration
Function Definition
Function Call
Understanding these three components is important before writing complex functions.

Function Declaration
A function declaration informs the compiler about the function's name, return type, and parameters before the function is used.

```c
void display();
```

This statement tells the compiler that a function named display exists and does not return any value.

Function Definition
The function definition contains the actual code that executes when the function is called.

```c
void display()
{
    printf("Welcome");
}
```

Function Call
A function call is used to execute the function.

```c
display();
```

When this statement executes, control transfers to the function and executes its statements.

Program Demonstrating Declaration, Definition and Function Call

```c
#include <stdio.h>

void display();

int main()
{
    display();

    return 0;
}

void display()
{
    printf("Hello Students");
}
```

Output:
Hello Students

Return Type of a Function
The return type specifies what kind of value a function returns to the calling function.

Some common return types are:
int
float
char
void

When a function does not return any value, the return type is void.

```c
void display()
{
    printf("Hello");
}
```

Function Without Arguments and Without Return Value
This is the simplest type of function.

The function neither receives data nor returns data.

```c
#include <stdio.h>

void greet()
{
    printf("Welcome to Function Programming");
}

int main()
{
    greet();

    return 0;
}
```

Output:
Welcome to Function Programming

Function Without Arguments but With Return Value
In this type, the function does not receive data from the caller but returns a value.

```c
#include <stdio.h>

int getNumber()
{
    return 100;
}

int main()
{
    int value;

    value = getNumber();

    printf("Value = %d", value);

    return 0;
}
```

Output:
Value = 100

The function returns the value 100 to the main function.

Function With Arguments but Without Return Value
In this type, data is passed to the function, but the function does not return anything.

```c
#include <stdio.h>

void displaySquare(int number)
{
    printf("Square = %d", number * number);
}

int main()
{
    displaySquare(5);

    return 0;
}
```

Output:
Square = 25

The value 5 is passed as an argument to the function.

Function With Arguments and Return Value
This is one of the most commonly used types of functions.

The function receives data, processes it, and returns a result.

```c
#include <stdio.h>

int add(int a, int b)
{
    return a + b;
}

int main()
{
    int result;

    result = add(10, 20);

    printf("Sum = %d", result);

    return 0;
}
```

Output:
Sum = 30

Example 1: Find Sum Using Function

```c
#include <stdio.h>

int sum(int a, int b)
{
    return a + b;
}

int main()
{
    int num1, num2;

    printf("Enter two numbers: ");
    scanf("%d%d", &num1, &num2);

    printf("Sum = %d", sum(num1, num2));

    return 0;
}
```

Example 2: Find Maximum of Two Numbers

```c
#include <stdio.h>

int maximum(int a, int b)
{
    if(a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}

int main()
{
    int num1, num2;

    printf("Enter two numbers: ");
    scanf("%d%d", &num1, &num2);

    printf("Largest Number = %d", maximum(num1, num2));

    return 0;
}
```

Example 3: Find Square of a Number

```c
#include <stdio.h>

int square(int number)
{
    return number * number;
}

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    printf("Square = %d", square(number));

    return 0;
}
```

Example 4: Check Even or Odd Using Function

```c
#include <stdio.h>

void checkEvenOdd(int number)
{
    if(number % 2 == 0)
    {
        printf("Even Number");
    }
    else
    {
        printf("Odd Number");
    }
}

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    checkEvenOdd(number);

    return 0;
}
```

Example 5: Find Factorial Using Function

```c
#include <stdio.h>

int factorial(int number)
{
    int i;
    int fact = 1;

    for(i = 1; i <= number; i++)
    {
        fact = fact * i;
    }

    return fact;
}

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    printf("Factorial = %d", factorial(number));

    return 0;
}
```

Variable Scope in Functions
Variables declared inside a function are called local variables. These variables can only be used inside that function.

```c
#include <stdio.h>

void display()
{
    int number = 10;

    printf("%d", number);
}

int main()
{
    display();

    return 0;
}
```

The variable number exists only inside the display() function.

Advantages of Functions
Functions help break large programs into smaller parts. They reduce code repetition and make programs easier to understand. Functions also simplify debugging because errors can be located within a specific function. Reusable functions save development time and improve program organization.

Because of these advantages, almost every large software project uses functions extensively.

Homework Questions
1.Write a function to find the largest of two numbers.
2.Write a function to calculate the factorial of a number.
3.Write a function to calculate simple interest.
4.Write a function to print the multiplication table of a number.
5.Write a function to find the cube of a number.