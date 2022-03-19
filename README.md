# stacks-linked-list-
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node*next;
}*newnode,*temp;
struct node*head=NULL;
struct node*tail=NULL;
void push()
{
    int value,ch;
    do{
        newnode=(struct node*)malloc(sizeof(struct node));
        printf("enter the value");
        scanf("%d",&value);
        newnode->data=value;
        newnode->next=NULL;
        if(head==NULL)
        {
            head=newnode;
            tail=newnode;
        }
        else
        {
            newnode->data=value;
            newnode->next=head;
            head=newnode;
        }
        printf("1-continue,0-exit\n");
        scanf("%d",&ch);
    }
    while(ch==1);
}
void pop()
{
    temp=head;
    printf("enter the pop value in stack\n");
    head=head->next;
    temp->next=NULL;
}
void display()
{
    temp=head;
    printf("stack elements are:\n");
    while(temp!=NULL)
    {
        printf("%d",temp->data);
        temp=temp->next;
    }
}
void main()
{
    int choice=0;
    while(choice<4)
    {
       printf("operations on stacks using linked list");
       printf("1-push\n,2-pop\n");
       printf("3-display");
       printf("enter your choice");
       scanf("%d",&choice);
       switch(choice)
       {
           case 1:
           push();
           break;
           case 2:
           pop();
           break;
           case 3:
           display();
           break;
       }
    }
}
