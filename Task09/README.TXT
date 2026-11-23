#include <stdio.h>
#include <limits.h>

typedef unsigned short meter_t;
#define SLAB1 100
#define SLAB2 200
#define RATE2 225LL
#define RATE3 450LL
#define FIXED 5000LL

unsigned int units_used(meter_t prev, meter_t curr) {
    return (unsigned short)(curr-prev);
}

long long bill(unsigned int u) {
    long long p=FIXED;
    if(u>SLAB2) p+=(long long)(u-SLAB2)*RATE3;
    if(u>SLAB1) {
        unsigned int mid=(u<SLAB2?u:SLAB2)-SLAB1;
        p+=(long long)mid*RATE2;
    }
    return p;
}

int main(void) {
    unsigned short prev,curr;
    if(scanf("%hu %hu",&prev,&curr)!=2) {
        puts("Invalid input"); return 1;
    }
    unsigned int u=units_used(prev,curr);
    long long p=bill(u);
    printf("Units: %u\nBill: Rs %lld.%02lld\n",u,p/100,p%100);
}

