#include<stdio.h>
#include<stdlib.h>
#include<string.h>
	int main()
	{
		char *text;
		int len;
		int i=0;
		FILE *fp1;
		int n;
		char s[10];
		int j=0;
		char m[11];
		fp1 = fopen("export.gpx","r");
	if((fp1 = fopen("export.gpx","r"))==0)
		{
			printf("文件不能正常打开");
			return (-1);
		}              
		fseek(fp1,0,SEEK_END);                 
		len=ftell(fp1);
		text=(char *)malloc(len);
		printf("length=%d\n",len);	
		fseek(fp1,0,SEEK_SET);
		fread(text,1,len,fp1);		
		while(!((*(text+i)=='l')&&(*(text+i+1)=='a')&&(*(text+i+2)=='t')))
		{
			i++;
		}
		strncpy(s,text+i+5,9);	
		printf("lat=%s\n",s);		
		free(text);
		return 0;
	}
