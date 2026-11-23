#include <stdio.h>

#define RATE 225

int main() {
    int units = 150;
    long bill;

    bill = 5000 + (units - 100) * RATE;

    printf("Total Bill: Rs %ld.%02ld\n",
           bill / 100, bill % 100);

    return 0;
}

