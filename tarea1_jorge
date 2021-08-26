#include"LPC17xx.h"

void retardo(uint32_t tiempo);

int main(void){

	//Definimos variables
	uint32_t tiempo=100000;
    uint32_t tiempo1=1000000;
    uint32_t contador1;


    //P0.0 A P0.9 DIGITALES
	LPC_PINCON->PINSEL0  &= ~(0X3FF);    //0B10010101010101  &  0B11110000000000 = 0B101010...0000000000


    //P0.0-P0.9  SALIDAS

	LPC_GPIO0->FIODIR |= (0X3FF);     // 0B0101..1111111111 | 0B010101..101 = 0B0101..1111111111


	while(1){

	    for(contador1=0 ; contador1<tiempo1; contador1++){

	    	//SECUENCIA A
			LPC_GPIO0->FIOCLRL|=(0x3FF);       //CLR DE P0.0 A P0.9
			retardo(tiempo);
		    LPC_GPIO0->FIOSETL |= (0x3FF);     //SET DE P0.0 A P0.9
			retardo(tiempo);
	    }

	    for(contador1=0 ; contador1<tiempo1; contador1++){

	    	//SECUENCIA B
	    	LPC_GPIO0->FIOCLRL |= (0X3FF);     //CLR DE P0.0 A P0.9
	    	retardo(tiempo);
	    	LPC_GPIO0->FIOSETL |= (0X2AA);     //SET IMPARES
	    	retardo(tiempo);
	    }

	}

	return 0;
}

void retardo(uint32_t tiempo){

	uint32_t contador;
	for(contador =0 ; contador<tiempo; contador++){};

}
