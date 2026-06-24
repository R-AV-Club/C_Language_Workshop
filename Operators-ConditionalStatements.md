Day 2: Operators and Conditional Statements
Introduction to Operators

In programming, we often need to perform calculations, compare values, or make decisions based on certain conditions. Operators are special symbols that help us perform these tasks. Just as mathematical symbols such as +, -, \*, and / are used in mathematics, C provides operators to perform different types of operations on variables and values.

For example, if a program needs to add two numbers, compare student marks, or check whether a person is eligible to vote, operators are used to perform these tasks.

Arithmetic Operators

Arithmetic operators are used to perform mathematical calculations.

The most commonly used arithmetic operators in C are addition (+), subtraction (-), multiplication (\*), division (/), and modulus (%).

The following program demonstrates the use of arithmetic operators.

```C
#include <stdio.h>

int main()
{
    int a = 20;
    int b = 10;

    printf("Addition = %d\n", a + b);
    printf("Subtraction = %d\n", a - b);
    printf("Multiplication = %d\n", a * b);
    printf("Division = %d\n", a / b);
    printf("Modulus = %d\n", a % b);

    return 0;
}
```

Output:

Addition = 30
Subtraction = 10
Multiplication = 200
Division = 2
Modulus = 0

The modulus operator returns the remainder after division. For example, when 17 is divided by 5, the remainder is 2.

```C
#include <stdio.h>

int main()
{
    int number = 17;

    printf("Remainder = %d", number % 5);

    return 0;
}
```

Output:
Remainder = 2

Assignment Operators
Assignment operators are used to assign values to variables.

The most commonly used assignment operator is =.

```C
#include <stdio.h>

int main()
{
    int age;

    age = 18;

    printf("Age = %d", age);

    return 0;
}
```

Output:
Age = 18

The value on the right side is assigned to the variable on the left side.

Relational Operators

Relational operators are used to compare two values. The result of a comparison is either true (1) or false (0).

These operators are commonly used in decision-making statements such as if and while.

The relational operators available in C are:

== Equal to
!= Not equal to

> Greater than
> < Less than
> = Greater than or equal to
> <= Less than or equal to

The following program demonstrates relational operators.

```C
#include <stdio.h>

int main()
{
    int a = 10;
    int b = 20;

    printf("%d\n", a == b);
    printf("%d\n", a != b);
    printf("%d\n", a < b);
    printf("%d\n", a > b);

    return 0;
}
```

Output:
0
1
1
0
A result of 1 means the condition is true, while 0 means the condition is false.

Logical Operators
Sometimes a program needs to check multiple conditions at the same time. Logical operators are used in such situations.

C provides three logical operators.

AND operator (&&) returns true only when both conditions are true.

OR operator (||) returns true if at least one condition is true.

NOT operator (!) reverses the result of a condition.

The following program demonstrates the AND operator.

```C
#include <stdio.h>

int main()
{
    int age = 20;
    int marks = 80;

    printf("%d", age >= 18 && marks >= 40);

    return 0;
}
```

Output:
1
Both conditions are true, so the result is 1.

Increment and Decrement Operators
The increment operator (++) increases the value of a variable by one.

The decrement operator (--) decreases the value of a variable by one.

```c
#include <stdio.h>

int main()
{
    int number = 10;

    number++;

    printf("Number = %d\n", number);

    number--;

    printf("Number = %d", number);

    return 0;
}
```

Output:
Number = 11
Number = 10

These operators are frequently used inside loops.

Introduction to Conditional Statements
Programs become powerful when they can make decisions. In real life, decisions are based on conditions.

For example:

If age is greater than or equal to 18, a person can vote.
If marks are greater than or equal to 40, a student passes.
If the balance is sufficient, money can be withdrawn.

Conditional statements allow programs to make similar decisions.

The if Statement
The if statement is used when a block of code should execute only if a condition is true.

The following program checks whether a person is eligible to vote.

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if(age >= 18)
    {
        printf("Eligible for voting");
    }

    return 0;
}
```

Output:
Enter age: 20
Eligible for voting

If the condition becomes false, nothing inside the if block executes.

The if-else Statement
The if-else statement is used when one action should occur if the condition is true and another action should occur if the condition is false.

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if(age >= 18)
    {
        printf("Eligible for voting");
    }
    else
    {
        printf("Not eligible for voting");
    }

    return 0;
}
```

Output:
Enter age: 15
Not eligible for voting

Example: Even or Odd Number
One of the most important beginner programs is checking whether a number is even or odd.
A number is even if the remainder after division by 2 is zero.

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if(number % 2 == 0)
    {
        printf("Even Number");
    }
    else
    {
        printf("Odd Number");
    }

    return 0;
}
```

The else-if Ladder
When there are multiple conditions, the else-if ladder is used.

The followig program displays grades based on marks.

```c
#include <stdio.h>

int main()
{
    int marks;

    printf("Enter marks: ");
    scanf("%d", &marks);

    if(marks >= 90)
    {
        printf("Grade A");
    }
    else if(marks >= 75)
    {
        printf("Grade B");
    }
    else if(marks >= 50)
    {
        printf("Grade C");
    }
    else
    {
        printf("Fail");
    }

    return 0;
}
```

Output:
Enter marks: 82
Grade B

Nested if Statement
An if statement inside another if statement is called a nested if statement.

```c
#include <stdio.h>

int main()
{
    int age;
    int citizenship;

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Enter citizenship status (1 for Indian, 0 for Other): ");
    scanf("%d", &citizenship);

    if(age >= 18)
    {
        if(citizenship == 1)
        {
            printf("Eligible for voting");
        }
    }

    return 0;
}
```

Switch Statement
The switch statement is used when there are multiple choices and only one block should execute.

It is often used to create menu-driven programs.

```c
#include <stdio.h>

int main()
{
    int choice;

    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");

    printf("Enter choice: ");
    scanf("%d", &choice);

    switch(choice)
    {
        case 1:
            printf("Addition Selected");
            break;

        case 2:
            printf("Subtraction Selected");
            break;

        case 3:
            printf("Multiplication Selected");
            break;

        default:
            printf("Invalid Choice");
    }

    return 0;
}
```

Example 1: Find the Largest of Two Numbers

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d%d", &a, &b);

    if(a > b)
    {
        printf("%d is greater", a);
    }
    else
    {
        printf("%d is greater", b);
    }

    return 0;
}
```

Example 2: Check Positive or Negative Number

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if(number >= 0)
    {
        printf("Positive Number");
    }
    else
    {
        printf("Negative Number");
    }

    return 0;
}
```

Example 3: Calculate Profit or Loss

```c
#include <stdio.h>

int main()
{
    int costPrice, sellingPrice;

    printf("Enter Cost Price: ");
    scanf("%d", &costPrice);

    printf("Enter Selling Price: ");
    scanf("%d", &sellingPrice);

    if(sellingPrice > costPrice)
    {
        printf("Profit");
    }
    else if(costPrice > sellingPrice)
    {
        printf("Loss");
    }
    else
    {
        printf("No Profit No Loss");
    }

    return 0;
}
```

Homework Questions
1.Write a program to find the largest of two numbers.
2.Write a program to find the largest of three numbers using if-else
3.Write a program to check whether a year is a leap year.
4.Create a simple calculator using switch statement.
5.Create a menu-driven program to display different messages based on user choice.
