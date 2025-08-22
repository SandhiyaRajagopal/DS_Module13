# Ex4 Evaluation of prefix expression
## DATE: 22/08/25
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1. Initialize an empty stack.
2. Scan the prefix expression from right to left.
3. If the character is an operand, push it onto the stack.
4. If the character is an operator, pop two operands, apply the operator, and push the result.
5. After scanning, the stack contains the final result.   

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: SANDHIYA R
RegisterNumber: 212223240146
*/

#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int x)
{
	s[++top]=x;
}

int pop()
{
    return s[top--];
}

void evalprefix(char p[50])
{
    int i=strlen(p)-1;
    while(i>=0)
    {
        if(isdigit(p[i]))
        {
            push(p[i]-48);
        }
        else
        {
            int num1,num2,num3;
            num1=pop();
            num2=pop();
            switch(p[i])
            {
                case '+':
                {
                    num3=num2+num1;
                    break;
                }
                case '-':
                {
                    num3=num1-num2;
                    break;
                }
                case '*':
                {
                    num3=num2*num1;
                    break;
                }
            }
            push(num3);
        }
        i--;
    }
    printf("%d",pop());
}

```

## Output:
<img width="280" height="157" alt="image" src="https://github.com/user-attachments/assets/ce712f5d-8a3a-4f42-ace8-613b66a0eddb" />



## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
