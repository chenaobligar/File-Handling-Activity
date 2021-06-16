#include <stdio.h>

int main ()

{

  FILE * file;
  
  int i,n;
  
  char str[100];
  
  char name[20];
  
  char str1;
  
	printf("\n A program that append multiple lines in a text file :\n");

	printf("\n Input the file name to be opened : ");
  
	scanf("%s",name);		
  
    file = fopen(name, "a"); 
    
    printf("  Number of lines to be written : ");
    
    scanf("%d", &n);
    
    printf(" The text are : \n");  
    
    for(i = 0; i < n+1;i++)
    
    {
    
    fgets(str, sizeof str, stdin);
    
    fputs(str,file);
    
  }
  
  fclose (file);

	file = fopen (name, "r");  
  
	printf("\n The content of the file %s is  :\n",name);
  
	str1 = fgetc(file);
  
	while (str1 != EOF)
  
		{
    
			printf ("%c", str1);
      
			str1 = fgetc(file);
      
		}
    
    printf("\n\n");
    
    fclose (file);

  return 0;
  
}

