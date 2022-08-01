// Se incluye las librerias necesarias para el funcionamiento del programa 
#include <xc.h>
#include <stdio.h>
#include <stdlib.h>
#include "pic16f887.h"

//definir la frecuencia del oscilador 
#define _XTAL_FREQ 48000000

void main(void) {
    
    // Configuramos los 0 como salidas y los 1 como entradas 
    ADCON1 = 0b00001111;
    
    TRISB = 0b00000001;
    
    
    if (PORTBbits.RB0 == 1) // Si presionamos el boton conectado a RB0 ubicado en el PORTB el led conectado prendera
    {
        PORTBbits.RB1 = 1;
        
    } 
     // en caso contrario el led estara apagado
    else {
        PORTBbits.RB1 = 0;
    }  
    
}

