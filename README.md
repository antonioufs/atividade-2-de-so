//Antonio Bispo de Jesus Neto
//201410011477
#include <stdio.h>
#include <process.h> // _beginthread()
#include <windows.h>
#include <unistd.h>
 
int i = 0;

void soma();
void beep();
void aviso();

int main ( ) 
{
	_beginthread(beep,0,NULL);
	_beginthread(soma,0,NULL);
	
	//int u;
	//u = 0;
	while(i<20)
	{
			i++;
			printf("%d\n",i);
	}
	_beginthread(aviso,0,NULL);
	MessageBox(0,"primeiro aviso","normal",0);
	MessageBox(0,"terceiro aviso","normal",0);
	return 0;
}

void soma()
{
	while(i<20)
	{
		i= i+2;
		printf("= %d\n",i);
	}
}

void beep()
{
        while(1){
             printf("\a");// som do beep
             sleep(1);
        }
}

void aviso()
{
       MessageBox(0,"segundo aviso","thread",0);
}
 
