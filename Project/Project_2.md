# Project 2: CryptoVault Lite - Digital Trading & Security Ledger

```c
#include <stdio.h>

float calculateTokensBought(char assetType, float amount)
{
    float tokenPrice;

    if(assetType == 'B' || assetType == 'b')
    {
        tokenPrice = 5000000.0;
    }
    else
    {
        tokenPrice = 300000.0;
    }

    return amount / tokenPrice;
}

int generateMFAPin(int sessionCode)
{
    int evenSum = 0;
    int oddSum = 0;
    int digit;

    while(sessionCode > 0)
    {
        digit = sessionCode % 10;

        if(digit % 2 == 0)
        {
            evenSum = evenSum + digit;
        }
        else
        {
            oddSum = oddSum + digit;
        }

        sessionCode = sessionCode / 10;
    }

    return evenSum * oddSum;
}

int main()
{
    int accountNumber;
    int securityKey;
    int attempts;

    float fiatBalance = 0;


    printf("CRYPTOVAULT LITE\n");


    for(attempts = 1; attempts <= 3; attempts++)
    {
        printf("\nEnter Account Number : ");
        scanf("%d", &accountNumber);

        printf("Enter Security Key   : ");
        scanf("%d", &securityKey);

        if(accountNumber == 7707 &&
           securityKey == 9911)
        {
            printf("\nAccess Granted\n");
            break;
        }

        printf("Invalid Credentials\n");
    }

    if(attempts > 3)
    {
        printf("\nConsole Locked\n");
        return 0;
    }

    while(1)
    {
        int choice;


        printf("MAIN MENU\n");

        printf("1. Deposit Funds\n");
        printf("2. Execute Trade\n");
        printf("3. View Balance\n");
        printf("4. Exit\n");


        printf("Enter Choice : ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
            {
                float depositAmount;

                printf("\nEnter Deposit Amount : ");
                scanf("%f", &depositAmount);

                if(depositAmount < 500 ||
                   depositAmount > 500000)
                {
                    printf("\nREJECTED");
                    printf("\nDeposit Outside Limits\n");
                }
                else
                {
                    fiatBalance =
                    fiatBalance + depositAmount;

                    printf("\nDeposit Successful");
                    printf("\nCurrent Balance = %.2f\n",
                           fiatBalance);
                }

                break;
            }

            case 2:
            {
                char assetType;

                float spendAmount;
                float feeRate;
                float feeAmount;
                float netAmount;
                float tokens;

                int sessionCode;
                int generatedPin;
                int enteredPin;

                if(fiatBalance <= 0)
                {
                    printf("\nNo Balance Available\n");
                    break;
                }

                printf("\nChoose Asset\n");
                printf("B - Bitcoin\n");
                printf("E - Ethereum\n");

                printf("Enter Choice : ");
                scanf(" %c", &assetType);

                printf("Enter Amount To Spend : ");
                scanf("%f", &spendAmount);

                if(spendAmount > fiatBalance)
                {
                    printf("\nInsufficient Balance\n");
                    break;
                }

                if(spendAmount <= 10000)
                {
                    feeRate = 2.5;
                }
                else if(spendAmount <= 100000)
                {
                    feeRate = 1.5;
                }
                else
                {
                    feeRate = 0.5;
                }

                feeAmount =
                spendAmount * feeRate / 100.0;

                netAmount =
                spendAmount - feeAmount;

                tokens =
                calculateTokensBought(assetType,
                                      netAmount);

                printf("\nEnter 6 Digit Session Code : ");
                scanf("%d", &sessionCode);

                generatedPin =
                generateMFAPin(sessionCode);

                printf("\nGenerated MFA Key = %d\n",
                       generatedPin);

                printf("Re-enter MFA Key : ");
                scanf("%d", &enteredPin);

                if(enteredPin != generatedPin)
                {
                    printf("\nTrade Cancelled");
                    printf("\nInvalid MFA Verification\n");
                    break;
                }

                fiatBalance =
                fiatBalance - spendAmount;

                printf("\n");

                printf("         CRYPTO TRADE RECEIPT\n");


                printf("Account Number\t\t: %d\n",
                       accountNumber);

                printf("Trade Amount\t\t: %.2f\n",
                       spendAmount);

                printf("Platform Fee\t\t: %.2f\n",
                       feeAmount);

                printf("Net Trade Amount\t: %.2f\n",
                       netAmount);

                printf("MFA Clearance Pin\t: %d\n",
                       generatedPin);

                printf("Tokens Purchased\t: %.6f\n",
                       tokens);

                printf("Remaining Balance\t: %.2f\n",
                       fiatBalance);

                printf("\n");

                break;
            }

            case 3:
            {
                printf("\n");
                printf("Current Fiat Balance = %.2f\n",
                       fiatBalance);

                break;
            }

            case 4:
            {
                printf("\nEjecting Hardware Ledger...\n");
                return 0;
            }

            default:
            {
                printf("\nInvalid Choice\n");
            }
        }
    }

    return 0;
}
```

---

# Sample Output

```text
=====================================
       CRYPTOVAULT LITE
=====================================

Enter Account Number : 7707
Enter Security Key   : 9911

Access Granted

1. Deposit Funds
2. Execute Trade
3. View Balance
4. Exit

Enter Choice : 1

Enter Deposit Amount : 50000

Deposit Successful
Current Balance = 50000.00
```
