# Ex4 Evaluation of prefix expression
## DATE: 26.04.2025
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
1. Start and initialize an empty stack s with top.
2. Define push() and pop() functions for stack operations.
3. In evalprefix(), scan the prefix expression from right to left.
4. Push digits onto stack; for operators (+, *), pop two operands, perform operation, and push result.
5. After traversal, print the top of the stack and end.

## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: Aliya Sheema 
RegisterNumber: 212223230011
*/
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int s[50];
int top=0;
void push(int ch)
{
top++;
s[top]=ch;
}
int pop()
{
int ch;
ch=s[top];
top=top-1;
return(ch);
}
void evalprefix(char p[50])
{
int a,b,c,i;
for(i=strlen(p)-1;i>=0;i--)
{
if(p[i]=='+')
{
a=pop();
b=pop();
c=a+b;
push(c);
}
else if(p[i]=='*')
{
a=pop();
b=pop();
c=a*b;
push(c);
}
else
{
push(p[i]-48);
}
}
printf("%d",pop());
}

```

## Output:

![image](https://github.com/user-attachments/assets/821892cf-19ff-4d99-8493-cd623238d729)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
