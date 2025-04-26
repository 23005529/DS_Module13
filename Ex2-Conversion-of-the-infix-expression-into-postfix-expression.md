# Ex2 Conversion of the infix expression into postfix expression
## DATE : 26.04.2025
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Start and initialize stack with top = -1.
2. Define push(), pop(), and priority() functions.
3. Traverse infix expression in IntoPost().
4. Handle operands, operators, and parentheses during traversal.
5. Pop and print remaining operators from stack, then end

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by : Aliya Sheema 
RegisterNumber:  212223230011
*/

#include<stdio.h>
#include<ctype.h>
char stack[100];
int top = -1;
void push(char x)
{
stack[++top]=x;
}
char pop()
{
if(top==-1)
return 0;
else
return stack[top--];
}
int priority(char x)
{
if(x=='(')
{
return 0;
}
if(x=='&'||x=='|')
{
return 1;
}
if(x=='+'||x=='-')
{
return 2;
}
if(x=='*'||x=='/'||x=='%')
{
return 3;
}
if(x=='^')
{
return 4;
}
return 0;
}
char IntoPost(char *exp)
{
char *e,x;
e=exp;
while(*e!='\0')
{
if(isalnum(*e))
{
printf("%c ",*e);
}
else if(*e=='(')
{
push(*e);
}
else if(*e==')')
{
while((x=pop())!='(')
printf("%c ",x);
}
else
{
while(priority(stack[top])>=priority(*e))
printf("%c ",pop());
push(*e);
}
e++;
}
while(top != -1)
{
printf("%c ",pop());
}return 0;
}
int main()
{
char exp[100]="3%2+4*(A&B)";
IntoPost(exp);
return 1;
}

```

## Output:

![image](https://github.com/user-attachments/assets/7daac1b3-d46c-4fbc-b9c1-0bbe17c13d06)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
