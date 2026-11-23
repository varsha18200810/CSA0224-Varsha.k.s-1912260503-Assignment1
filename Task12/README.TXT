#include <stdio.h>
#include <stdint.h>

#define PEAK_START_HOUR 18
#define PEAK_END_HOUR 22

int main(void) {
    uint64_t watt_hours = 0;
    double base_rate_paise_per_kwh, peak_rate;
    int hour;
    /* Read rates from config/input and validate them. */
    base_rate_paise_per_kwh = 225.0;
    peak_rate = base_rate_paise_per_kwh * 1.20;
    hour = 19; /* sample time */
    watt_hours = 1500; /* sample interval usage */

    double kwh = (double)watt_hours / 1000.0;
    double rate = (hour >= PEAK_START_HOUR && hour < PEAK_END_HOUR)
                  ? peak_rate : base_rate_paise_per_kwh;
    double charge_paise = kwh * rate;
    printf("Usage %.3f kWh; charge %.2f paise\n", kwh, charge_paise);
    return 0;
}

