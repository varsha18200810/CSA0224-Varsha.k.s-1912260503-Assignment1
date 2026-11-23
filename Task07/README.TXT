#include <stdio.h>

int main() {
    int a = 5, b = 2;
    float x = 5.0f, y = 2.0f;

    printf("Integer Division: %d\n", a / b);

    printf("Floating Division: %.2f\n", x / y);

    printf("Integer Multiplication: %d\n", a * b);

    printf("Explicit Conversion: %.2f\n", (float)a / b);

    printf("Type Conversion: %.2f\n", (double)5 / 2);

    long paise = 16250;

    printf("Bill: Rs %ld.%02ld\n",
           paise / 100, paise % 100);

    return 0;
}

