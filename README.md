# Computer_Graphics
My First graphics code in C
/*
  Siddesh Mishra
  To draw solid and dotted line using DDA algorithm
*/
#include<graphics.h>
#include<conio.h>
#include<math.h>
#include<stdio.h>
int sign(int s) ;
int main()
{
 float x1,y1,x2,y2,dx,dy,length;
 float x,y,xinc,yinc;
 int i,ch;
 int gd=DETECT,gm;
clrscr();
 initgraph(&gd,&gm,"C:\\TurboC3\\BGI");
 printf("Enter start point:");
 scanf("%f %f",&x1,&y1);
 printf("Enter end point:");
 scanf("%f %f",&x2,&y2);
dy=y2-y1;
dx=x2-x1;
if(abs(dx)>abs(dy)) length=abs(dx);
else length=abs(dy);
xinc=dx/length;
yinc=dy/length;
x=x1+0.5*sign(xinc);
y=y1+0.5*sign(yinc);
i=0;
 printf("1.Solid Line\n2.Dotted Line\nEnter choice:");
 scanf("%d",&ch);
switch(ch){
 case 1:
   while(i<=length){
   putpixel((int)x,(int)y,GREEN);
   x=x+xinc; y=y+yinc;
   i=i+1;}
 case 2:
   while(i<=length){
   if(i%2==0)
   putpixel((int)x,(int)y,GREEN);
   x=x+xinc; y=y+yinc;
   i=i+1;}
 }
getch();
closegraph();
return 0;
}
int sign(int s){
if(s<0) return(-1);
else if(s>0) return(1);
else return 0;

}


