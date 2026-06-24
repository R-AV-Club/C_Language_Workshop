# Assignment 1 Solutions

## Task 1: The Bio Data Printer

### Problem Statement

Write a program that prints the student's name, college name, branch, and hobbies. Each piece of information must appear on a new line using a single `printf()` statement.

### Solution

```c
#include <stdio.h>

int main()
{
    printf("Name: abc\nCollege: xyz College\nBranch: Computer Engineering\nHobbies: Coding");

    return 0;
}
```

### Output

Name: Moksha Shah
College: Msu College
Branch: Computer Engineering
Hobbies: Coding

## Task 2: The Age Calculator

### Problem Statement

Ask the user to enter their birth year. Calculate and display their approximate age.

Formula:
Age = 2026 - birth_year

### Solution

```c
#include <stdio.h>

int main()
{
    int birthYear;
    int age;

    printf("Enter your birth year: ");
    scanf("%d", &birthYear);

    age = 2026 - birthYear;

    printf("Your approximate age is %d", age);

    return 0;
}
```

### Sample Output

Enter your birth year: 2000
Your approximate age is 26

## Task 3: The Report Card Generator

### Problem Statement

Ask the student to enter marks for 3 subjects. Calculate total marks and percentage.

Formula:
totalMarks = marks1 + marks2 + marks3
percentage = (totalMarks / 300.0) \* 100

### Solution

```c
#include <stdio.h>

int main()
{
    int marks1;
    int marks2;
    int marks3;
    int totalMarks;
    float percentage;

    printf("Enter marks of Subject 1: ");
    scanf("%d", &marks1);

    printf("Enter marks of Subject 2: ");
    scanf("%d", &marks2);

    printf("Enter marks of Subject 3: ");
    scanf("%d", &marks3);

    totalMarks = marks1 + marks2 + marks3;

    percentage = (totalMarks / 300.0) * 100;

    printf("Total Marks = %d\n", totalMarks);
    printf("Percentage = %.2f", percentage);

    return 0;
}
```

### Sample Output

Enter marks of Subject 1: 80
Enter marks of Subject 2: 90
Enter marks of Subject 3: 70
Total Marks = 240
Percentage = 80.00

## Task 4: Character Swapper

### Problem Statement

Ask the user to input two characters and display them in reverse order.

### Solution

```c
#include <stdio.h>

int main()
{
    char firstCharacter;
    char secondCharacter;
    char temp;

    printf("Enter first character: ");
    scanf(" %c", &firstCharacter);

    printf("Enter second character: ");
    scanf(" %c", &secondCharacter);

    temp = firstCharacter;
    firstCharacter = secondCharacter;
    secondCharacter = temp;

    printf("Characters in reverse order: %c %c ", firstCharacter, secondCharacter);

    return 0;
}
```

### Sample Output

Enter first character: A
Enter second character: B
Characters in reverse order: B A