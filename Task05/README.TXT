#include <stdio.h>
#include "billing.h"

int main() {
    int units;

    printf("Enter Units: ");
    scanf("%d", &units);

    printf("Total Bill: Rs %ld.%02ld\n",
           compute_bill(units) / 100,
           compute_bill(units) % 100);

    return 0;
}

