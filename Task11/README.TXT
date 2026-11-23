#include <stdio.h>

int main() {
    int slab1, slab2;
    int rate1, rate2, rate3;
    long fixed;

    int units;
    long bill;

    FILE *fp = fopen("tariff.txt", "r");

    if (fp == NULL) {
        printf("Unable to open tariff file\n");
        return 1;
    }

    if (fscanf(fp, "%d %d %d %d %d %ld",
               &slab1, &slab2,
               &rate1, &rate2, &rate3,
               &fixed) != 6) {
        printf("Invalid tariff file\n");
        fclose(fp);
        return 1;
    }

    fclose(fp);

    printf("Enter Units Consumed: ");
    scanf("%d", &units);

    if (units < 0) {
        printf("Invalid Units\n");
        return 1;
    }

    bill = fixed;

    if (units > slab2)
        bill += (slab2 - slab1) * rate2
              + (units - slab2) * rate3;

    else if (units > slab1)
        bill += (units - slab1) * rate2;

    else
        bill += units * rate1;

    printf("Total Bill: Rs %ld.%02ld\n",
           bill / 100, bill % 100);

    return 0;
}

