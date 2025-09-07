# Line-follower-8051
#include<reg51.h> 
sbit ir1=P1^0; 
sbit ir2=P1^1; 
sbit m0_0=P2^0; //right motor 
sbit m0_1=P2^1; 
sbit m1_0=P2^2; //left motor 
sbit m1_1=P2^3;  

void goAhead(); 
void goBack(); 
void goRight(); 
void goLeft(); 
void stop(); 
void main() 
{ 
m0_0=m0_1=m1_0=m1_1=0; 
ir1=1;  
ir2=1;    
while(1)   
{      

if(ir1==0 && ir2==0)               //motor=forward;                 goAhead();     

else if(ir1==0 && ir2==1         //motor=turn_left;  
goLeft();     

else if(ir1==1 && ir2==0)  //motor=turn_right;    
goRight();   

else         
//motor=stop;  
stop(); 
}
} 
void goAhead() 
{ 
m0_0=1; 
m0_1=0;
m1_0=1; 
m1_1=0; 
} 
void stop() 
{   
m0_0=0;
m0_1=0;
m1_0=0; 
m1_1=0;
} 
void goBack() 
{   
m0_0=0;  
m0_1=1;  
m1_0=0; 
m1_1=1; 
} 
void goRight() 
{    
m0_0=1; 
m0_1=0; 
m1_0=0; 
m1_1=1; 
}
void goLeft() 
{    
m0_0=0;
m0_1=1;  
m1_0=1;  
m1_1=0; 
} 
