# Assignment 2 Solutions

## Task 1: The Smart Cashier

### Problem Statement

A customer buys an item for ₹455.50 and pays with a ₹500 note.

Calculate:

- Exact change due
- Number of ₹1 coins required

Use type casting to convert the decimal change into an integer.

### Solution

```c
#include <stdio.h>

int main()
{
    float itemPrice = 455.50;
    float amountPaid = 500.00;
    float change;

    int coins;

    change = amountPaid - itemPrice;

    coins = (int)change;

    printf("Cashier Receipt\n");
    printf("-------------------------\n");
    printf("Item Price\t: %.2f\n", itemPrice);
    printf("Amount Paid\t: %.2f\n", amountPaid);
    printf("Exact Change\t: %.2f\n", change);
    printf("1 Rupee Coins\t: %d\n", coins);

    return 0;
}
```

### Output

## Cashier Receipt

Item Price : 455.50
Amount Paid : 500.00
Exact Change : 44.50
1 Rupee Coins : 44

## Task 2: Movie Ticket Checker

### Problem Statement

A theater requires a viewer to be at least 13 years old to watch a movie.

Display:

- Access Granted
- Access Denied

### Solution

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter your age: ");
    scanf("%d", &age);

    if(age >= 13)
    {
        printf("\nAccess Granted");
    }
    else
    {
        printf("\nAccess Denied");
    }

    return 0;
}
```

### Sample Output

Enter your age: 18

Access Granted

## Task 3: Dual-Factor Login

### Problem Statement

The system should allow login when:

- Username and Password are correct
- OR the user is an Admin

Otherwise display Login Failed.

### Solution

```c
#include <stdio.h>

int main()
{
    int enteredUsername;
    int enteredPassword;

    int storedUsername = 1234;
    int storedPassword = 5678;

    int isAdmin;

    printf("Enter Username: ");
    scanf("%d", &enteredUsername);

    printf("Enter Password: ");
    scanf("%d", &enteredPassword);

    printf("Are you Admin? (1 = Yes, 0 = No): ");
    scanf("%d", &isAdmin);

    if((enteredUsername == storedUsername &&
        enteredPassword == storedPassword)
        || isAdmin == 1)
    {
        printf("\nLogin Successful");
    }
    else
    {
        printf("\nLogin Failed");
    }

    return 0;
}
```

### Sample Output

Enter Username: 1234
Enter Password: 5678
Are you Admin? (1 = Yes, 0 = No): 0

Login Successful

## Task 4: Weather Suggestion Engine

### Problem Statement

Suggest suitable clothing based on temperature.

- Below 15°C → Wear a heavy jacket
- Between 15°C and 25°C → Wear a sweater
- Above 25°C → Wear a t-shirt

### Solution

```c
#include <stdio.h>

int main()
{
    int temperature;

    printf("Enter Temperature: ");
    scanf("%d", &temperature);

    if(temperature < 15)
    {
        printf("\nSuggestion: Wear a heavy jacket");
    }
    else if(temperature <= 25)
    {
        printf("\nSuggestion: Wear a sweater");
    }
    else
    {
        printf("\nSuggestion: Wear a t-shirt");
    }

    return 0;
}
```

### Sample Output

Enter Temperature: 28

Suggestion: Wear a t-shirt

## Task 5: Even, Odd, or Zero?

### Problem Statement

Check whether a number is:

- Zero
- Even
- Odd

### Solution

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if(number == 0)
    {
        printf("\nThe number is Zero");
    }
    else if(number % 2 == 0)
    {
        printf("\nThe number is Even");
    }
    else
    {
        printf("\nThe number is Odd");
    }

    return 0;
}
```

### Sample Output 1

Enter a number: 0

The number is Zero

### Sample Output 2

Enter a number: 12

The number is Even

### Sample Output 3

Enter a number: 15

The number is Odd
