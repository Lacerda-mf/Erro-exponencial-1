/*# Erro-exponencial
Erro numérico da exponencial*/


// PROGRAMA 1


#include<stdio.h>
#include<stdlib.h>
#include<math.h>

double resultado;
int contador;
int n;
double xis;
double fat;
double m;
FILE *file;

main()
{
	file = fopen("dados_exponencial(-somatorio).txt", "w");
	for(xis =0; xis<= 70; xis++)// variando o x
	{
		resultado = 1;
		for(contador = 1;contador < 200;contador++)// somatorio
		{
			n = contador;
			for(fat = 1; n > 1; n--) // fatorial
			{
				fat = n * fat;
			}
			n = contador;
			m = pow(-1,n)*(pow(xis,n) / fat); // formula matematica;
			resultado = resultado + m;
		}
		fprintf(file,"\n %.15g \n",resultado);
	}
	fclose(file);
	system("pause");
}


// PROGRAMA 2



#include <stdio.h>
#include <stdlib.h>
#include <math.h>

int contador;
double resultado;
int n;
double sn;
double xis;

main()
{
	for(xis =1;xis<=70;xis++)
	{
		sn=1;
		resultado = 0;
		for(contador=1;contador<200;contador++)
			{	
				n = contador;
				sn = -sn * (xis / n);
				resultado = resultado + sn;	
			}
		printf("\n %.15g \n", resultado+1);
	}
	system("pause");
}



//PROGRAMA 3



#include<stdio.h>
#include<stdlib.h>
#include<math.h>

double resultado;
int contador;
int n;
double xis;
double fat;
double m;
FILE *file;

main()
{
	file = fopen("dados_exponencial(+somatorio).txt", "w");
	for(xis =0; xis<= 70; xis=xis+1)// variando o x
	{
		resultado = 1;
		for(contador = 1;contador < 200;contador++)// somatorio
		{
			n = contador;
			for(fat = 1; n > 1; n--) // fatorial
			{
				fat = n * fat;
			}
			n = contador;
			m = (pow(xis,n) / fat); // formula matematica;
			resultado = resultado + m;
		}
		fprintf(file,"\n %.15g \n",1/resultado);
	}
	fclose(file);
	system("pause");
}



// PROGRAMA 4



#include <stdio.h>
#include <stdlib.h>
#include <math.h>

int contador;
double resultado;
int n;
double sn;
double xis;
FILE *file;
main()
{
	file = fopen("dados_exponencial(recorrencia).txt", "w");
	for(xis =1;xis<=70;xis++)
	{
		sn=1;
		resultado = 0;
		for(contador=1;contador<200;contador++)
			{	
				n = contador;
				sn = sn * (xis / n);
				resultado = resultado + sn;	
			}
		fprintf(file,"\n %.15g \n", 1/(resultado+1));
	}
	fclose(file);
	system("pause");
}
