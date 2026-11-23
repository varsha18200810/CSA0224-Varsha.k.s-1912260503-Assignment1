#include <stdio.h>
#include <limits.h>

int main(void) {
    printf("int=%zu long=%zu long long=%zu double=%zu bytes\n",
           sizeof(int),sizeof(long),sizeof(long long),sizeof(double));
    printf("INT_MAX=%d LLONG_MAX=%lld\n",INT_MAX,LLONG_MAX);
}

