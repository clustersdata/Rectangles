# Rectangles

Rectangles

Problem Description

Given two rectangles and the coordinates of two points on the diagonals of each rectangle,you have to calculate the area of the intersected part of two rectangles. its sides are parallel to OX and OY .

Input

Input The first line of input is 8 positive numbers which indicate the coordinates of four points that must be on each diagonal.The 8 numbers are x1,y1,x2,y2,x3,y3,x4,y4.That means the two points on the first rectangle are(x1,y1),(x2,y2);the other two points on the second rectangle are (x3,y3),(x4,y4).

Output

Output For each case output the area of their intersected part in a single line.accurate up to 2 decimal places.

Sample Input

1.00 1.00 3.00 3.00 2.00 2.00 4.00 4.00 5.00 5.00 13.00 13.00 4.00 4.00 12.50 12.50

Sample Output

1.00 56.25


代码：

#include<stdio.h>

void res(double x1,double y1,double x2,double y2,double x3,double y3,double x4,double y4)

{

    double tmpx1,tmpy1,tmpx2,tmpy2;
    
    double tmpx,tmpy;
    
    tmpx=x1+x2;   x1=(x1>x2)?x2:x1;     x2=tmpx-x1;
    
  tmpy=y1+y2;   y1=(y1>y2)?y2:y1;     y2=tmpy-y1;
  
  tmpx=x3+x4;   x3=(x3>x4)?x4:x3;     x4=tmpx-x3;
  
tmpy=y3+y4;   y3=(y3>y4)?y4:y3;     y4=tmpy-y3;

 tmpx1=(x1>x3)?x1:x3;    tmpx2=(x2>x4)?x4:x2;
 
    tmpy1=(y1>y3)?y1:y3;    tmpy2=(y2>y4)?y4:y2;    
    
    if(tmpx1<tmpx2&&tmpy1<tmpy2)    printf("%.2lf\n",(tmpx1-tmpx2)*(tmpy1-tmpy2));
    
    else    printf("0.00\n");   
    
}

int main()

{

    double x1,y1,x2,y2;   double x3,y3,x4,y4;
    
    while(scanf("%lf%lf%lf%lf%lf%lf%lf%lf",&x1,&y1,&x2,&y2,&x3,&y3,&x4,&y4)!=EOF)
    
    {
    
        res(x1,y1,x2,y2,x3,y3,x4,y4);
        
    }
    
    return 0;
    
}

