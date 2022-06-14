# cdi-4
#include <stdio.h>
#include "pico/stdlib.h"

int main () {
    stdio_init_all();
    gpio_init_mask(0x3ff);
    gpio_set_dir_out_masked(0x7f);
    gpio_set_dir_in_masked(0x380);
    char incremento= 0;
    while (1) {
        char PIN7= gpio_get(7);
        char PIN8= gpio_get(8);
        char PIN9= gpio_get(9);
        if(PIN7==true) {
            incremento++;
        }
        if(PIN8==true) {   
            incremento--;
        }

        if(PIN9==true) {
            incremento=0
        }
        if(incremento==0) { 
            gpio_put_masked(0x7f,0x3f);
        }

        if(incremento==1) {
            gpio_put_masked(0x7f,0x6);
        }
        if(incremento==2) {
            gpio_put_masked(0x7f,0x5b);
        }
        if(incremento==3) {
            gpio_put_masked(0x7f,0x4f);
        }
        if(incremento==4) {
            gpio_put_masked(0x7f,0x66);
        }
        if(incremento==5) {
            gpio_put_masked(0x7f,0x6d);
        }
        if(incremento==6) {
            gpio_put_masked(0x7f,0x7d);
        }
        if(incremento==7) {
            gpio_put_masked(0x7f,0x7);
        }
        if(incremento==8) {
            gpio_put_masked(0x7f,0x7f);
        }
        if(incremento==9) {
            gpio_put_masked(0x7f,0x67);
        }

        if(incremento==-1) {
            incremento=0;
        }
        if(incremento==10) {
            incremento=9;
        }
        
           }
    }
}

