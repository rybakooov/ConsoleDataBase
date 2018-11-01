#include <stdio.h>
#include <conio.h>
#include <stdlib.h>
#include <string.h>
int N;
struct EDB{
    char firstName[6];
    char secondName[6];
    int age;
    int weight;
} A[20];
 
void menu1(){
    FILE *file;
    int i, p, n, sort, fir, search, aggge, ves, k, z, asc1, asc2, sec; 
    char c, name[6], family[6]; 
    fflush(stdin);
    printf("1.Vvod \n2.Vyvod \n3.Add \n4.Delete \n5.Search \n6.Sort \n7.Exit \n");
    c = getchar();
    switch(c){
    case '1' :
    	printf("1.File\n2.Vvod s klavy\n");
		scanf("%d", &fir);
    	if(fir == 1){

    		file = fopen("edb.txt", "r");
    		i = 0;
    		N = 0;
			while (fscanf(file, "%s%s%d%d", &A[i].firstName, &A[i].secondName, &(A[i].age), &(A[i].weight)) != EOF) {
				N++;
				i++;
			}
			printf("%d", N);
			fclose(file);
		}
		if(fir == 2){
        	printf("vvedite kol-vo studentov\n");
        	scanf("%d", &N);
        	printf("vvedite imya, familiu, vozrast, ves xherez probel\n");
        	for (i = 0; i < N; i++) {
            	scanf("%s %s %d %d", &A[i].firstName, &A[i].secondName, &A[i].age, &A[i].weight);
        	}
    	}
    	break;
    case '2':
    	file = fopen("edb1.txt", "w");
    	printf("1.File\n2.Vyvod na ekran\n");
    	scanf("%d", &sec);
    	if(sec == 1){
    		for(i = 0; i < N; i++){
    			fprintf(file, "%6s %6s %6d %6d\n", A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
			}
			fclose(file);
		}
    	if(sec == 2){
	        printf("------------------------------------\n");
	        printf("|   num|    fN|    sN|   age|weight|\n");
	        for (i = 0; i < N; i++) {
	            printf("------------------------------------\n");
	            printf("|%6d|%6s|%6s|%6d|%6d|\n", i, A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
	        }
	        printf("------------------------------------\n");
    	}
    	break;
    case '3':
        printf("vvedite kol-vo studentov dlya dobavl\n");
        scanf("%d", &n);
        printf("vvedite imya, familiu, vozrast, ves cherez probel\n");
        for (i = N; i < N + n; i++) {
            scanf("%s %s %d %d", &A[i].firstName, &A[i].secondName, &A[i].age, &A[i].weight);
        }
        N += n;
		break;
    case '4':
        printf("Vvedite nomer stroki dlya ydaleniya\n");
        scanf("%d", &p);
        for(i = p; i < N - 1; i++){
            strcpy(A[i].firstName, A[i+1].firstName);
            strcpy(A[i].secondName, A[i+1].secondName);
            A[i].age = A[i+1].age;
            A[i].weight = A[i+1].weight;
		}
		N--;
		break;
	case '5':
		printf("Vyberite priznak:\n1.fN\n2.sN\n3.age\n4.weight\n");
		scanf("%d", &search);
		switch(search){
			case 1 : 
				printf("Vvedite IMYA\n");
				scanf("%s", &name);
				printf("------------------------------------\n");
        		printf("|   num|    fN|    sN|   age|weight|\n");
				for(i = 0; i < N; i++){
					if(strcmp(name, A[i].firstName) == 0){
						printf("------------------------------------\n");
            			printf("|%6d|%6s|%6s|%6d|%6d|\n", i, A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
					}
				}
			printf("------------------------------------\n");	
			break;
			case 2 : 
				printf("Vvedite FAMILYU\n");
				scanf("%s", &family);
				printf("------------------------------------\n");
        		printf("|   num|    fN|    sN|   age|weight|\n");
				for(i = 0; i < N; i++){
					if(strcmp(family, A[i].secondName) == 0){
						printf("------------------------------------\n");
            			printf("|%6d|%6s|%6s|%6d|%6d|\n", i, A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
					}
				}
			printf("------------------------------------\n");
			break;
			case 3 : 
				printf("Vvedite VOZRAST\n");
				scanf("%d", &aggge);
				printf("------------------------------------\n");
        		printf("|   num|    fN|    sN|   age|weight|\n");
				for(i = 0; i < N; i++){
					if(aggge == A[i].age){
						printf("------------------------------------\n");
            			printf("|%6d|%6s|%6s|%6d|%6d|\n", i, A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
					}
				}
			printf("------------------------------------\n");
			break;
			case 4 : 
				printf("Vvedite VES\n");
				scanf("%d", &ves);
				printf("------------------------------------\n");
        		printf("|   num|    fN|    sN|   age|weight|\n");
				for(i = 0; i < N; i++){
					if(ves == A[i].weight){
						printf("------------------------------------\n");
            			printf("|%6d|%6s|%6s|%6d|%6d|\n", i, A[i].firstName, A[i].secondName, A[i].age, A[i].weight);
					}
				}
			printf("------------------------------------\n");
			break;
		}
	break;
	case '6':
		printf("Vyberite priznak:\n1.fN\n2.sN\n3.age\n4.weight\n");
		scanf("%d", &sort);
		switch(sort){
			case 1 :
				for(z = 0; z < (N-1); z++){
					for(i = 0; i < (N-1); i++){
						for(k = 0; k < 6; k++){
							asc1 = A[i].firstName[k];
							asc2 = A[i+1].firstName[k];
							if(asc1 > asc2){
								strcpy(name, A[i].firstName);
								strcpy(family, A[i].secondName);
								aggge = A[i].age;
								ves = A[i].weight;
								
								strcpy(A[i].firstName, A[i+1].firstName);
								strcpy(A[i].secondName, A[i+1].secondName);
								A[i].age = A[i+1].age;
								A[i].weight = A[i+1].weight;
								
								strcpy(A[i+1].firstName, name);
								strcpy(A[i+1].secondName, family);
								A[i+1].age = aggge;
								A[i+1].weight = ves;
								goto xxx;
							}
							if (asc1 < asc2){
								goto xxx;
							}
							
							
						}
						xxx: ;
					}
				}
			break;
			case 2 :
				for(z = 0; z < (N-1); z++){
					for(i = 0; i < (N-1); i++){
						for(k = 0; k < 6; k++){
							asc1 = A[i].secondName[k];
							asc2 = A[i+1].secondName[k];
							if(asc1 > asc2){
								strcpy(name, A[i+1].firstName);
								strcpy(family, A[i+1].secondName);
								aggge = A[i+1].age;
								ves = A[i+1].weight;
								
								strcpy(A[i+1].firstName, A[i].firstName);
								strcpy(A[i+1].secondName, A[i].secondName);
								A[i+1].age = A[i].age;
								A[i+1].weight = A[i].weight;
								
								strcpy(A[i].firstName, name);
								strcpy(A[i].secondName, family);
								A[i].age = aggge;
								A[i].weight = ves;
								goto ccc;
							}
							if (asc1 < asc2){
								goto ccc;
							}
						}
						ccc: ;
					}	
				}
			break;
			case 3 :
				for(z = 0; z < N-1; z++){
				for(i = 0; i < N-1; i++){
					if((A[i].age)>(A[i+1].age)){
						strcpy(name, A[i+1].firstName);
						strcpy(family, A[i+1].secondName);
						aggge = A[i+1].age;
						ves = A[i+1].weight;
						
						strcpy(A[i+1].firstName, A[i].firstName);
						strcpy(A[i+1].secondName, A[i].secondName);
						A[i+1].age = A[i].age;
						A[i+1].weight = A[i].weight;
						
						strcpy(A[i].firstName, name);
						strcpy(A[i].secondName, family);
						A[i].age = aggge;
						A[i].weight = ves;
					}
				}
				}
			break;
			case 4 :
				for(z = 0; z < N-1; z++){
				for(i = 0; i < N-1; i++){
					if((A[i].weight)>(A[i+1].weight)){
						strcpy(name, A[i+1].firstName);
						strcpy(family, A[i+1].secondName);
						aggge = A[i+1].age;
						ves = A[i+1].weight;
						
						strcpy(A[i+1].firstName, A[i].firstName);
						strcpy(A[i+1].secondName, A[i].secondName);
						A[i+1].age = A[i].age;
						A[i+1].weight = A[i].weight;
						
						strcpy(A[i].firstName, name);
						strcpy(A[i].secondName, family);
						A[i].age = aggge;
						A[i].weight = ves;
					}
				}
				}
			break;
		}
	break;
    case '7':
        exit(0);
	}
	printf("\n");
    menu1();
}
void main(){
    menu1();
    getch();
}
