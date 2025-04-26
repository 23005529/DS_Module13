# EX 1 Display operator precedence in the infix expression.
## DATE : 212223230011
## AIM :
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start
2. Initialize empty stack s and top.
3. Define push() and pop() functions.
4. In evalprefix(), scan expression right to left.
5. If digit → convert and push to stack.
6. If operator (+, *) → pop two values, apply operator, push result.
7. After loop, print top of stack.
8. End

## Program:
```
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by : Aliya Sheema 
RegisterNumber:  212223230011
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

![image](https://github.com/user-attachments/assets/656681b5-cb2d-4ac3-b9d5-33d984ba704c)


## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
