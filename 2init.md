#include<stdio.h>
#include<conio.h>
int za,zb,zc,zd,ze,b,nb;
void enter();
void zone();
void mapping();
void seg();

void enter()
{
printf("YOU HAVE TO ENTER AN APPROXIMATE AMOUNT OF GARBAGE IN YOUR HOUSE.\n");
printf("ENTER THE AMOUNT OF BIODEGRADABLE WASTE :");
scanf("%d",&b);
printf("\nENTER THE AMOUNT OF NON-BIODEGRADABLE WASTE :");
scanf("%d",&nb);
printf("\nYOUR CITY IS DIVIDED INTO 5 ZONES...\n ");
printf("\nENTER THE NUMBER OF HOUSES IN ZONE A:");
scanf("%d",&za);
printf("\nENTER THE NUMBER OF HOUSES IN ZONE B:");
scanf("%d",&zb);
printf("\nENTER THE NUMBER OF HOUSES IN ZONE C:");
scanf("%d",&zc);
printf("\nENTER THE NUMBER OF HOUSES IN ZONE D:");
scanf("%d",&zd);
printf("\nENTER THE NUMBER OF HOUSES IN ZONE E:");
scanf("%d",&ze);
}
void zone()
{
int i,j,t,ar[50],temp;
t=((b+nb)*(za));
int n;
n=(t/800);
printf("\nTHE NUMBER OF GARBAGE CANS REQUIRED IN ZONE A IS %d",n);
printf("\nENTER THE NUMBER OF HOUSES IN THE LOCALITY OF YOUR ZONE:\n");
for(i=0;i<n;i++)
{
 scanf("%d",&ar[i]);
}
for(i=0;i<n;i++)
   {
      for(j=i+1;j<n;j++)
      {
	if(ar[j]>ar[i])
	   {
	     temp=ar[j];
	     ar[j]=ar[i];
	     ar[i]=temp;
	   }
      }
   }
for(i=0;i<n;i++)
{
printf("%d  ",ar[i]);
}
}

void mapping()
{
int zone1,D1,D2,a[100][100],m,n;
float dist1,dist2;
D1=a[50][99];
D2=a[0][99];
printf("\nCONSIDERING ZONE 1 ,ENTER ITS APPROXIMATE CENTRE");
scanf("%d %d",&m,&n);
zone1=a[m][n];
dist1=((m-50)*(m-50))+((n-99)*(n-99));
dist2=(m*m)+((n-99)*(n-99));
if(dist1>dist2)
{
printf("\nGARBAGE IS DUMPED AT DUMPYARD NO.2");
}
else
{
printf("\nGARBAGE IS DUMPED AT DUMPYARD NO.1");
}
}

void seg()
{
int total_garb,b_garb,nb_garb;
total_garb=(za+zb+zc+zd+ze)*(b+nb);
b_garb=((b)*(total_garb))/(b+nb);
nb_garb=((nb)*(total_garb))/(b+nb);
printf("\nTHE TOTAL GARBAGE DUMPED IN THE DUMPYARD IS %d",total_garb);
printf("\nTHE TOTAL BIODEGRADABLE WASTE IN THIS WILL BE %d",b_garb);
printf("\nTHE TOTAL NON-BIODEGRADABLE WASTE IN THIS WILL BE %d",nb_garb);
}

int main()
{

char ch;
printf("              TEAM#10\n\n     ");
printf("          WASTE MANAGEMENT\n\n ");
printf(" MAIN MENU\nSTEP 1.COLLECT INPUT\nSTEP 2.ZONE \nSTEP 3.MAPPING\nSTEP4.SEGREGATING \n 5.END\n");
printf("START BY PRESSING 1");
scanf("%c",&ch);
switch(ch)
{
case '1': enter();
case '2': zone();
case '3': mapping();
case '4': seg();
case '5': printf("\NTHANK YOU");
}
return 0;
}




