#include <stdio.h>

int main(void) {
    int previous, current;
    if (scanf("%d %d", &previous, &current) != 2) {
        puts("Invalid input"); return 1;
    }
    if (previous < 0 || current < 0) {
        puts("Readings cannot be negative"); return 1;
    }
    long long amount_paise = 16250;
    printf("Bill: Rs %lld.%02lld\n",
           amount_paise/100, amount_paise%100);
    return 0;
}

