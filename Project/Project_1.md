# Project 1: AeroFreight Lite - Smart Cargo Billing System

```c
#include <stdio.h>

float calculateVolumetricWeight(float length, float width, float height)
{
    return (length * width * height) / 5000.0;
}

float calculateShippingBill(float weight, char zone)
{
    float bill = 0;

    if(zone == 'D' || zone == 'd')
    {
        if(weight <= 5)
        {
            bill = weight * 50;
        }
        else
        {
            bill = (5 * 50) + ((weight - 5) * 40);
        }
    }
    else if(zone == 'I' || zone == 'i')
    {
        if(weight <= 5)
        {
            bill = weight * 150;
        }
        else
        {
            bill = (5 * 150) + ((weight - 5) * 120);
        }
    }

    return bill;
}

int calculateChecksum(int batchCode)
{
    int sum = 0;

    while(batchCode > 0)
    {
        sum = sum + (batchCode % 10);
        batchCode = batchCode / 10;
    }

    return sum;
}

int main()
{
    int operatorID;
    int passcode;
    int attempts;

    int totalShipments = 0;

    printf("AEROFREIGHT LITE SYSTEM\n");

    for(attempts = 1; attempts <= 3; attempts++)
    {
        printf("\nEnter Operator ID : ");
        scanf("%d", &operatorID);

        printf("Enter Passcode    : ");
        scanf("%d", &passcode);

        if(operatorID == 101 && passcode == 2026)
        {
            printf("\nAccess Granted\n");
            break;
        }

        printf("Invalid Credentials\n");
    }

    if(attempts > 3)
    {
        printf("\nSystem Locked\n");
        return 0;
    }

    while(1)
    {
        int choice;

        printf("MAIN MENU\n");
        printf("1. Process New Shipment\n");
        printf("2. Check Terminal Status\n");
        printf("3. Shutdown Engine\n");

        printf("Enter Choice : ");
        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
            {
                float length;
                float width;
                float height;
                float physicalWeight;
                float volumetricWeight;
                float chargeableWeight;
                float bill;
                float fuelPremium = 0;
                float expressCharge = 0;

                int distance;
                int express;

                int batchCode;
                int checksum;

                char zone;

                printf("\nEnter Length (cm) : ");
                scanf("%f", &length);

                printf("Enter Width (cm)  : ");
                scanf("%f", &width);

                printf("Enter Height (cm) : ");
                scanf("%f", &height);

                printf("Enter Physical Weight (kg) : ");
                scanf("%f", &physicalWeight);

                if(length > 150 ||
                   width > 150 ||
                   height > 150 ||
                   physicalWeight > 250)
                {
                    printf("\nOVERSIZED_REJECT\n");
                    break;
                }

                volumetricWeight =
                calculateVolumetricWeight(length,
                                          width,
                                          height);

                if(physicalWeight > volumetricWeight)
                {
                    chargeableWeight = physicalWeight;
                }
                else
                {
                    chargeableWeight = volumetricWeight;
                }

                printf("Enter Zone (D/I) : ");
                scanf(" %c", &zone);

                bill =
                calculateShippingBill(chargeableWeight,
                                      zone);

                printf("Enter Distance (km) : ");
                scanf("%d", &distance);

                if((zone == 'I' || zone == 'i')
                    && distance > 1000)
                {
                    fuelPremium = 1500;
                }

                printf("Express Delivery?\n");
                printf("1. Yes\n");
                printf("0. No\n");
                printf("Enter Choice : ");
                scanf("%d", &express);

                if(express == 1)
                {
                    expressCharge =
                    (bill + fuelPremium) * 0.5;
                }

                printf("Enter 5 Digit Batch Code : ");
                scanf("%d", &batchCode);

                checksum =
                calculateChecksum(batchCode);

                totalShipments++;

                printf("\n");
                printf("AEROFREIGHT INVOICE\n");

                printf("Verification ID\t\t: %d\n",
                       passcode);

                printf("Physical Weight\t\t: %.2f kg\n",
                       physicalWeight);

                printf("Volumetric Weight\t: %.2f kg\n",
                       volumetricWeight);

                printf("Chargeable Weight\t: %.2f kg\n",
                       chargeableWeight);

                printf("Checksum Signature\t: %d\n",
                       checksum);

                printf("\n");

                printf("Base Shipping Cost\t: %.2f\n",
                       bill);

                printf("Fuel Premium\t\t: %.2f\n",
                       fuelPremium);

                printf("Express Charges\t\t: %.2f\n",
                       expressCharge);

                printf("\n");

                printf("Final Amount\t\t: %.2f\n",
                       bill +
                       fuelPremium +
                       expressCharge);

                printf("\n");

                break;
            }

            case 2:
            {
                printf("\n");
                printf("Total Shipments Processed : %d\n",
                       totalShipments);
                break;
            }

            case 3:
            {
                printf("\nShutting Down System...\n");
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
      AEROFREIGHT LITE SYSTEM
=====================================

Enter Operator ID : 101
Enter Passcode    : 2026

Access Granted

1. Process New Shipment
2. Check Terminal Status
3. Shutdown Engine

Enter Choice : 1

Enter Length (cm) : 50
Enter Width (cm)  : 40
Enter Height (cm) : 30
Enter Physical Weight (kg) : 10

Enter Zone (D/I) : D

Enter Distance (km) : 500

Express Delivery?
1. Yes
0. No
Enter Choice : 1

Enter 5 Digit Batch Code : 45612
```
