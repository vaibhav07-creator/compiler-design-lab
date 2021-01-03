#include<stdio.h>
#include<conio.h>
#include<string.h>

char str[]=”A+(C*D)*F”;
char stack[10];
int top=-1;

void push(char s)
{
   top=top+1;
   stack[top]=s;
}

char pop()
{
   char item;
    item=stack[top];
    top--;
    return(item);
}

int precede(char c)
{
   if(c==47)     // Division(/)
    return(5); 

    if(c==42)     // Multiplication(*)
    return(4);

     if(c==43)     //Addition(+)
     return(3);

      else
      return(2);  
}

void main()
{
   char postfix[10];
   int l, i=0, j=0;
   char s, temp;

   printf(“infix string: “);
   puts(str);

   l=strlen(str);
   push(‘#’);

   while(i<l)
   {
      s=str[i];
      switch(s)
       {
           case ‘(‘:
            push(s);
	break;

	case ‘)’:
	temp=pop();
	while(temp!=’(‘)
	 {
	    postfix[j]=temp;
	    j++;
	    temp=pop();
	  }
              break;
           
              case ‘+’:
	  case ‘-‘:
	  case ‘*’:
	  case’/’:
	  while(precede(stack[top])>=precede(s))
	   {
		temp=pop();
		postfix[j]=temp;
		j++;
	    }
	  push(s);
	  break;

	
  default:
	  postfix[j++]=s;
	  break;
      }
   i++;
  }

  while(top>0)
    {
	temp=pop();
	postfix[j++]=temp;
     }

   postfix[j++]=’\0’;

   printf("\npostfix string");
   puts(postfix);
   getch();
}
