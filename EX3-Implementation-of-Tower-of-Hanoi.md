# EX3 Implementation of Tower of Hanoi
## DATE: 22/08/25
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1. Start with n disks on the source peg.
2. If n = 1, move the disk directly from source to destination and stop.
3. If n > 1:

Move n-1 disks from source to auxiliary peg.

Move the largest disk from source to destination peg.

Move the n-1 disks from auxiliary to destination peg.

4. Repeat the steps recursively until all disks are moved.
5. End when all disks are successfully transferred from source to destination.

## Program:
```
/*
Program to implement Tower of Hanoi
Developed by: SANDHIYA R
RegisterNumber: 212223240146
*/

#include<stdio.h>
void TOH(int n,char x,char y,char z)
{
   if(n>0)
   {
      TOH(n-1,x,z,y);
      printf("%c to %c",x,y);
      printf("\n");
      TOH(n-1,z,y,x);
   }
}
int main()
{
   int n=2;
   TOH(n,'A','B','C');
}
```

## Output:
<img width="298" height="206" alt="image" src="https://github.com/user-attachments/assets/4623a882-c936-44c6-a09a-fa88b4983bb0" />



## Result:
Thus, the C program to implement Tower of Hanoi using recursion is implemented successfully.
