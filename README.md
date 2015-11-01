#include <stdio.h>
#include <conio.h>
#include <stdlib.h>

typedef struct linked {
	int no;
	char ad[15];
	char soyad[20];
	struct linked *next;
	}Blist;
	
	int menu ();
	void ekle(Blist *take);
	void listele(Blist *take);
	
	int main (){
		int al;
		struct linked *first;
		first=NULL;
		while(true){
			al=menu();
			if(al==1){
				 ekle(first);
			}
			
			else if(al==2){
				listele (first);
				
			}
			
			else if(al==3){
				break;
			}
			
			else {
				printf("hatali secim yaptiniz.\n");
			}
		}		
		
		getch();
		return 0;
	}
	
	void ekle(Blist *take){
		int d;
		if(take==NULL){
			printf("sicil numarasini giriniz.\n");
			scanf("%d",&d);
			take->no=d;
			fflush(stdin);
			printf("isim giriniz.\n");
			gets(take->ad);
			printf("soyisim giriniz.\n");
			gets(take->soyad);
		}
		else {
			ekle(take->next);
		}
		
	}
	
	void listele (Blist *take){
			printf("Sicil no	");
			printf("isim		");
			printf("Soyisim\n");
		while(take){
			printf("%d	",take->no);
			printf("%s	",take->ad);
			printf("%s \n",take->soyad);
			take=take->next;
		}
		
	}
	
	int menu(){
		int sec;
		printf("1-) ekleme\n 2-)listele \n 3-)cikis.\n\n\n");
		scanf("%d",&sec);
		
		return sec;
	}
