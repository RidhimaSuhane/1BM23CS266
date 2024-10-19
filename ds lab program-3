#include<stdio.h>
#include<string.h>
int top=-1,pos=0,length,index0=0;
char symbol,temp,infix[50],postfix[50],stack[50];
void push(char symbol);
char pop();
void infixtopostfix();
int predefined(char);
void main()
{
    printf("enter the infix expression:\n");
    scanf("%s",infix);
    infixtopostfix();
    printf("infix expression:%s",infix);
    printf("postfix expression:%s",postfix);
}
void infixtopostfix()
{
    length=strlen(infix);
    while(index0<length)
    {
        symbol=infix[index0];
        switch(symbol)
        {
            
            case ')':
                temp=pop();
                while(temp!='(')
                {
                    postfix[pos]=temp;
                    pos++;
                    temp=pop();
                }
               
                break;
            case'(':
                push(symbol);
                break;
            case '*':
            case '/':
            case'^':
            case '+':
            case '-':
                while(pedefined(stack[top])>=predefined(symbol))
                {
                    temp=pop();
                    postfix[pos++]=temp;
                }
                push(symbol);
                break;
            default:
                postfix[pos++]=symbol;
            }
            index0++;
       
    }
     while(top>0)
        {
            temp=pop();
            postfix[pos++]=temp;
        }
}
char pop()
{
    char symb;
    symb=stack[top];
    top--;
    return symb;
}
void push(char symbol)
{
    top++;
    stack[top]=symbol;
}
int predefined(char symbol)
{
    int p;
    switch(symbol)
    {
        case '^':
            p=3;
            break;
        case '*':
        case '/':
            p=2;
            break;
        case '+':
        case '-':
            p=1;
            break;
        case '(':
            p=0;
            break;
        default:
            p=-1;
            break;
           
    }
    return p;
}
