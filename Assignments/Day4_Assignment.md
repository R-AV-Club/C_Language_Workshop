# Assignment 4 Solutions

# Task 1: Find the Largest of Three Numbers

## Problem Statement

Write a function that accepts three integers and returns the largest number.

### Type Used

With Parameters and With Return Type

### Solution

```c
#include <stdio.h>

int findLargest(int a, int b, int c)
{
    if(a > b)
    {
        if(a > c)
        {
            return a;
        }
        else
        {
            return c;
        }
    }
    else
    {
        if(b > c)
        {
            return b;
        }
        else
        {
            return c;
        }
    }
}

int main()
{
    int num1, num2, num3;

    printf("Enter three numbers: ");
    scanf("%d%d%d", &num1, &num2, &num3);

    printf("\nLargest Number = %d",
           findLargest(num1, num2, num3));

    return 0;
}
```

# Task 2: Leap Year Checker

## Problem Statement

Check whether a year is a leap year.

### Type Used

With Parameter and With Return Type

### Solution

```c
#include <stdio.h>

int isLeapYear(int year)
{
    if(year % 400 == 0)
    {
        return 1;
    }
    else if(year % 100 == 0)
    {
        return 0;
    }
    else if(year % 4 == 0)
    {
        return 1;
    }
    else
    {
        return 0;
    }
}

int main()
{
    int year;

    printf("Enter Year: ");
    scanf("%d", &year);

    if(isLeapYear(year))
    {
        printf("\nLeap Year");
    }
    else
    {
        printf("\nNot a Leap Year");
    }

    return 0;
}
```

# Task 3: Electricity Bill Calculator

## Problem Statement

Calculate electricity bill based on units consumed.

### Billing Rules

- First 100 units → ₹1 per unit
- Above 100 units → ₹2 per unit

### Type Used

Without Parameter and Without Return Type

### Solution

```c
#include <stdio.h>

void calculateBill()
{
    int units;
    int bill;

    printf("Enter Units Consumed: ");
    scanf("%d", &units);

    if(units <= 100)
    {
        bill = units * 1;
    }
    else
    {
        bill = (100 * 1) + ((units - 100) * 2);
    }

    printf("\nTotal Bill = Rs. %d", bill);
}

int main()
{
    calculateBill();

    return 0;
}
```

# Task 4: Check Prime Number

## Problem Statement

Determine whether a number is prime.

### Type Used

With Parameter and With Return Type

### Solution

```c
#include <stdio.h>

int isPrime(int number)
{
    for(int i = 2; i < number; i++)
    {
        if(number % i == 0)
        {
            return 0;
        }
    }

    return 1;
}

int main()
{
    int number;

    printf("Enter Number: ");
    scanf("%d", &number);

    if(isPrime(number))
    {
        printf("\nPrime Number");
    }
    else
    {
        printf("\nNot a Prime Number");
    }

    return 0;
}
```

# Task 5: Number Guessing Game

## Problem Statement

Create a guessing game using a hardcoded secret number.

### Type Used

Without Parameters and Without Return Type

### Solution

```c
#include <stdio.h>

void playGame()
{
    int guess;
    int secretNumber = 42;

    while(1)
    {
        printf("Enter Your Guess: ");
        scanf("%d", &guess);

        if(guess > secretNumber)
        {
            printf("Too High\n");
        }
        else if(guess < secretNumber)
        {
            printf("Too Low\n");
        }
        else
        {
            printf("Correct!\n");
            break;
        }
    }
}

int main()
{
    playGame();

    return 0;
}
```

---

# Task 6: Fibonacci Sequence Generator

## Problem Statement

Print Fibonacci sequence up to N terms.

### Type Used

With Parameter and Without Return Type

### Solution

```c
#include <stdio.h>

void fibonacci(int n)
{
    int a = 0;
    int b = 1;
    int c;

    for(int i = 0; i < n; i++)
    {
        printf("%d ", a);

        c = a + b;
        a = b;
        b = c;
    }
}

int main()
{
    int n;

    printf("Enter Number of Terms: ");
    scanf("%d", &n);

    printf("\nFibonacci Series:\n");

    fibonacci(n);

    return 0;
}
```

### Sample Output

Enter Number of Terms: 5

Fibonacci Series:
0 1 1 2 3

---

# Task 7: Factorial Finder

## Problem Statement

Calculate factorial of a number.

### Type Used

With Parameter and With Return Type

### Solution

```c
#include <stdio.h>

int factorial(int number)
{
    int fact = 1;

    for(int i = number; i >= 1; i--)
    {
        fact = fact * i;
    }

    return fact;
}

int main()
{
    int number;

    printf("Enter Number: ");
    scanf("%d", &number);

    printf("\nFactorial = %d",
           factorial(number));

    return 0;
}
```

### Sample Output

Enter Number: 5

Factorial = 120