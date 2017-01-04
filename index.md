

public class NumerosRomanos {
	
	char romanos[] = {'I','V','X','L','C','D','M'};
	int numeros[] = {1,5,10,50,100,500,1000};	
	int valorFinal;		
	
	int ConverterNumero(String valor){		
		
		int valorFinal = 0;
		char romano[] = valor.toCharArray();
		int num = 0, num2 = 0, num3 = 0;
		
		
		for (int x=0; x < romano.length; x++){
			for (int y=0; y <= 6; y++){				
				if (romanos[y] == romano[x]){		
					
					if (romano.length <= 2){
						if (num == 0){						
							num = numeros[y];
							valorFinal = num;						
						}else if (num < numeros[y]){						
							valorFinal = numeros[y] - num;						
						}else if (num >= numeros[y]){						
							valorFinal = valorFinal + numeros[y];
						}
					}else{
						if (num == 0){						
							num = numeros[y];
							valorFinal = num;						
						}else if (num2 == 0){								
							if (numeros[y] <= num){
								num2 = numeros[y];					
							}							
						}else if(num3 == 0){
							num3 = numeros[y];
							if(romano[x] != 'I'){	
								if (num2 < num3){
									valorFinal = num - num2 + num3;
								}else{
									valorFinal += num2 + num3;
								}															
							}
							else{
								valorFinal += num2 + num3;
							}
						}else{
							valorFinal = valorFinal + numeros[y];
						}	
					}					
				}				
			}				
		}		
		return valorFinal;
	}	
}
