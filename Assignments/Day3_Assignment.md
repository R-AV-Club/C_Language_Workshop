# Assignment 3 Solutions

# Task 1: Password Retry Limit

## Problem Statement

A user gets exactly 3 attempts to enter the correct PIN. If the PIN is correct, display "Access Granted" and stop. If all three attempts fail, display "Account Locked".

### Solution

```c
#include <stdio.h>

int main()
{
    int pin;
    int attempts;

    for(attempts = 1; attempts <= 3; attempts++)
    {
        printf("Enter PIN: ");
        scanf("%d", &pin);

        if(pin == 1234)
        {
            printf("\nAccess Granted");
            return 0;
        }

        printf("Incorrect PIN\n\n");
    }

    printf("Account Locked");

    return 0;
}
```

### Sample Output

Enter PIN: 1111
Incorrect PIN

Enter PIN: 2222
Incorrect PIN

Enter PIN: 3333
Incorrect PIN

Account Locked

# Task 2: The Fuel Tank Indicator

## Problem Statement

Start with a fuel tank of 50 litres. Reduce fuel by 3 litres for every kilometer travelled. Stop when fuel becomes less than 5 litres.

### Solution

```c
#include <stdio.h>

int main()
{
    int fuel = 50;
    int kilometer = 0;

    while(fuel >= 5)
    {
        kilometer++;

        fuel = fuel - 3;

        printf("Kilometer %d\tFuel Remaining = %d Litres\n",
               kilometer, fuel);
    }

    printf("\nWarning: Fuel Level Low");

    return 0;
}
```

### Sample Output

Kilometer 1 Fuel Remaining = 47 Litres
Kilometer 2 Fuel Remaining = 44 Litres

Warning: Fuel Level Low

# Task 3: The Bus Passenger Fare Collector

## Problem Statement

The bus can carry a maximum of 10 passengers.

- Age greater than 60 → Fare = ₹5
- Otherwise → Fare = ₹10

Calculate the total fare collected.

### Solution

```c
#include <stdio.h>

int main()
{
    int passenger;
    int age;
    int totalCollection = 0;

    for(passenger = 1; passenger <= 10; passenger++)
    {
        printf("Enter age of Passenger %d: ", passenger);
        scanf("%d", &age);

        if(age > 60)
        {
            totalCollection = totalCollection + 5;
        }
        else
        {
            totalCollection = totalCollection + 10;
        }
    }

    printf("\nBus Full");
    printf("\nTotal Collection = Rs. %d", totalCollection);

    return 0;
}
```

### Sample Output

Bus Full
Total Collection = Rs. 85

# Task 4: The Digital Hotel Menu

## Problem Statement

Display a menu repeatedly.

- 1 → Pizza (₹100)
- 2 → Burger (₹80)
- 3 → Sandwich (₹60)
- 0 → Exit

Display the final bill after checkout.

### Solution

```c
#include <stdio.h>

int main()
{
    int choice;
    int bill = 0;

    while(1)
    {
        printf("\n===== MENU =====\n");
        printf("1. Pizza      Rs.100\n");
        printf("2. Burger     Rs.80\n");
        printf("3. Sandwich   Rs.60\n");
        printf("0. Exit\n");

        printf("\nEnter Choice: ");
        scanf("%d", &choice);

        if(choice == 0)
        {
            break;
        }
        else if(choice == 1)
        {
            bill = bill + 100;
        }
        else if(choice == 2)
        {
            bill = bill + 80;
        }
        else if(choice == 3)
        {
            bill = bill + 60;
        }
        else
        {
            printf("Invalid Choice");
        }
    }

    printf("\nFinal Bill = Rs. %d", bill);

    return 0;
}
```

### Sample Output

1. Pizza
2. Burger
3. Sandwich
4. Exit

Enter Choice: 1

Enter Choice: 2

Enter Choice: 0

Final Bill = Rs. 180

# Task 5: Pattern Programs

## Pattern 1

### Output

1
22
333
4444
55555

### Solution

```c
#include <stdio.h>

int main()
{
    int i, j;

    for(i = 1; i <= 5; i++)
    {
        for(j = 1; j <= i; j++)
        {
            printf("%d", i);
        }

        printf("\n");
    }

    return 0;
}
```

---

## Pattern 2

### Output

---

---

---

\*\*

-

### Solution

```c
#include <stdio.h>

int main()
{
    int i, j;

    for(i = 5; i >= 1; i--)
    {
        for(j = 1; j <= i; j++)
        {
            printf("*");
        }

        printf("\n");
    }

    return 0;
}
```

---

## Pattern 3

### Output

1
2 3
4 5 6
7 8 9 10

### Solution

```c
#include <stdio.h>

int main()
{
    int i, j;
    int number = 1;

    for(i = 1; i <= 4; i++)
    {
        for(j = 1; j <= i; j++)
        {
            printf("%d ", number);
            number++;
        }

        printf("\n");
    }

    return 0;
}
```

---

## Pattern 4

### Output

1010
0101
1010
0101

### Solution

```c
#include <stdio.h>

int main()
{
    int value = 1;

    for(int i = 0; i < 4; i++)
    {
        if(i % 2 == 0)
        {
            for(int j = 0; j < 4; j++)
            {
                printf("%d", value);
                value = !value;
            }
        }

        else
        {
            for(int j = 0; j < 4; j++)
            {
                value = !value;
                printf("%d", value);
            }
        }
        printf("\n");
    }

    return 0;
}
```