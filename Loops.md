Day 3: Loop Statements in C
Introduction to Loops
In programming, there are many situations where we need to perform the same task multiple times. Writing the same statement again and again increases the length of the program and makes it difficult to manage. To solve this problem, C provides loop statements.

A loop allows a block of code to execute repeatedly as long as a specified condition remains true. Loops make programs shorter, easier to understand, and more efficient.

For example, if we want to print the message "Hello" ten times, we can either write ten separate printf() statements or use a loop. Using a loop is a much better approach because it reduces code repetition and improves readability.

Why Do We Need Loops?
Consider the following program.

```c
#include <stdio.h>

int main()
{
    printf("Hello\n");
    printf("Hello\n");
    printf("Hello\n");
    printf("Hello\n");
    printf("Hello\n");

    return 0;
}
```

The program works correctly, but it is not efficient. If we need to print "Hello" 100 times, writing 100 printf() statements would be impractical.

Loops allow us to solve this problem easily.

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        printf("Hello\n");
    }

    return 0;
}
```

Output:
Hello
Hello
Hello
Hello
Hello

The loop repeats the statement automatically.

Types of Loops in C

C provides three types of loops:

1.for loop
2.while loop
3.do-while loop

Each loop can perform repetitive tasks, but they differ slightly in syntax and behavior.

The for Loop
The for loop is one of the most commonly used loops in C. It is generally used when the number of repetitions is known beforehand.

The syntax of a for loop is:

```c
for(initialization; condition; increment/decrement)
{
    statements;
}
```

The initialization part executes only once at the beginning of the loop.
The condition is checked before each iteration.
The increment or decrement statement updates the loop variable after every iteration.

Program to Print Numbers from 1 to 10

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

Output:
1
2
3
4
5
6
7
8
9
10

The loop starts with i = 1 and continues until i becomes greater than 10.

Program to Print Numbers from 10 to 1
Loops can also count backwards using the decrement operator.

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 10; i >= 1; i--)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

Output:
10
9
8
7
6
5
4
3
2
1

Program to Print Even Numbers from 1 to 20

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 2; i <= 20; i = i + 2)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

Output:
2
4
6
8
10
12
14
16
18
20

The while Loop
The while loop is used when the number of repetitions is not known in advance.

The condition is checked before executing the loop body.

The syntax of a while loop is:

```c
while(condition)
{
    statements;
}
```

If the condition is true, the loop executes. If the condition is false, the loop stops.

Program to Print Numbers from 1 to 10 Using while Loop

```c
#include <stdio.h>

int main()
{
    int i = 1;

    while(i <= 10)
    {
        printf("%d\n", i);
        i++;
    }

    return 0;
}
```

Output:
1
2
3
4
5
6
7
8
9
10

Program to Print Multiples of 5

```c
#include <stdio.h>

int main()
{
    int i = 1;

    while(i <= 10)
    {
        printf("%d\n", i * 5);
        i++;
    }

    return 0;
}
```

Output:
5
10
15
20
25
30
35
40
45
50

The do-while Loop
The do-while loop is similar to the while loop. The main difference is that the loop body executes first and the condition is checked afterwards.

This guarantees that the loop executes at least one time.

The syntax is:

```c
do
{
    statements;
}
while(condition);
```

```c
#include <stdio.h>

int main()
{
    int i = 1;

    do
    {
        printf("%d\n", i);
        i++;
    }
    while(i <= 5);

    return 0;
}
```

Output:
1
2
3
4
5

Difference Between while and do-while Loop
In a while loop, the condition is checked before execution.

In a do-while loop, the condition is checked after execution.

Consider the following program.

```c
#include <stdio.h>

int main()
{
    int i = 10;

    while(i < 5)
    {
        printf("Hello\n");
    }

    return 0;
}
```

Output:
No Output

```c
#include <stdio.h>

int main()
{
    int i = 10;

    do
    {
        printf("Hello\n");
    }
    while(i < 5);

    return 0;
}
```

Output:
Hello

The statement executes once before the condition is checked.

Nested Loops
A loop inside another loop is called a nested loop.

Nested loops are commonly used to create patterns and tables.

```c
#include <stdio.h>

int main()
{
    int i, j;

    for(i = 1; i <= 4; i++)
    {
        for(j = 1; j <= 4; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

Output:

---

---

---

---

Example 1: Sum of First 10 Natural Numbers

```c
#include <stdio.h>

int main()
{
    int i;
    int sum = 0;

    for(i = 1; i <= 10; i++)
    {
        sum = sum + i;
    }

    printf("Sum = %d", sum);

    return 0;
}
```

Output:
Sum = 55

Example 2: Multiplication Table

```c
#include <stdio.h>

int main()
{
    int number;
    int i;

    printf("Enter a number: ");
    scanf("%d", &number);

    for(i = 1; i <= 10; i++)
    {
        printf("%d x %d = %d\n", number, i, number * i);
    }

    return 0;
}
```

Output:
Enter a number: 5
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50

Example 3: Factorial of a Number

```c
#include <stdio.h>

int main()
{
    int number;
    int i;
    int factorial = 1;

    printf("Enter a number: ");
    scanf("%d", &number);

    for(i = 1; i <= number; i++)
    {
        factorial = factorial * i;
    }

    printf("Factorial = %d", factorial);

    return 0;
}
```

Example 4: Count Digits in a Number

```c
#include <stdio.h>

int main()
{
    int number;
    int count = 0;

    printf("Enter a number: ");
    scanf("%d", &number);

    while(number > 0)
    {
        number = number / 10;
        count++;
    }

    printf("Number of digits = %d", count);

    return 0;
}
```

Example 5: Reverse a Number

```c
#include <stdio.h>

int main()
{
    int number;
    int remainder;
    int reverse = 0;

    printf("Enter a number: ");
    scanf("%d", &number);

    while(number > 0)
    {
        remainder = number % 10;
        reverse = reverse * 10 + remainder;
        number = number / 10;
    }

    printf("Reverse Number = %d", reverse);

    return 0;
}
```

Infinite Loop
An infinite loop is a loop that never stops because its condition always remains true.

```c
#include <stdio.h>

int main()
{
    while(1)
    {
        printf("Hello\n");
    }

    return 0;
}
```

This program keeps printing "Hello" forever until it is manually stopped.
Programmers should be careful while writing loop conditions to avoid creating infinite loops unintentionally.

Homework Questions
1.Write a program to check whether a number is a palindrome.
2.Write a program to print all multiples of 7 between 1 and 100.
3.Write a program to display the first 20 natural numbers using a while loop.
4.Write a program to find the sum of the first 20 natural numbers.
5.Write a program to check whether a number is a armstrong