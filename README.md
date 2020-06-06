#include <stdio.h>
#include <conio.h>
#include <dos.h>
//To avoid floting point error
void dummy (float a)
{
float *p=&a;
}
struct bill
{
char item[40];
float qty, price;
}b[100];

int main()
{
clrscr();
int i=0, c=1;
char ch;
float amt, total=0;

do
{
flushall();
printf("Enter Product Name  :");
gets(b[i].item);
printf("Enter Qty and Price : ");
scanf("%f%f",&b[i].qty, &b[i].price);
flushall();
printf("Add More Items [y/n]");
scanf("%c",&ch);
if(ch=='y')
{i++;c++;};
}
while(ch=='y');
printf("============================================================");
textcolor(RED);
textbackground(WHITE);
printf("\t\t\t\t\t\t\b\b\b");
cprintf("S U P E R  M A R K E T\n");
puts("\n============================================================");
printf("%-10s%15s%17s%17s\n", "Item", "Qty", "Price", "Amount");
puts("------------------------------------------------------------");
for(i=0;i<c;i++)
{
amt=b[i].qty*b[i].price;
total=total+amt;
printf("%-9s %16.2f\t%10.2f\t%11.2f\n",b[i].item, b[i].qty,b[i].price, amt);
}
puts("------------------------------------------------------------");

struct date d;
getdate(&d);
printf("Total Amount :\t\t\t\t\%.3f\n",total);
printf("Billing Date :%d/%d/%d\n",d.da_day,d.da_mon,d.da_year);
puts("Happy Shopping\n");
puts("\t\t\tVisit ForGeeky.com");
getch();
}
