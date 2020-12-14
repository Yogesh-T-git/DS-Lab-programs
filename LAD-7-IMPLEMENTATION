#include<stdio.h>
#include<stdlib.h>

struct node
{
	int data;
	struct node *next;
};
struct node *head;
struct node *head2;

//stack operations
void push()
{
	struct node *ptr;
	int new_data;
	ptr = (struct node *)malloc(sizeof(struct node));
	
	if(ptr == NULL)
	{
		printf("\nOVERFLOW!!!");	
	}
	else
	{
		printf("\nEnter the Value to be inserted:");
		scanf("%d",&new_data);
		ptr->data = new_data;
		ptr->next = head;
		head = ptr;
		printf("\nNODE INSERTED AT THE TOP OF THE STACK\n");	
	}
}
void pop()
{
	struct node *ptr;
	if(head == NULL)
	{
		printf("EMPTY LIST!!!");
	}
	else
	{
		ptr = head;
		head = ptr->next;
		free(ptr);
		printf("\nNODE DELETED FROM TOP OF THE STACK\n");
	}	
}

//queue operations
void enqueue()
{
	struct node *ptr,*temp;
	int new_data;
	ptr = (struct node *)malloc(sizeof(struct node));	
	
	printf("\nEnter the Value to be inserted:");
	scanf("%d",&new_data);
	ptr->data = new_data;
	if(head == NULL)
	{
		ptr->next = NULL;
		head = ptr;
		printf("\nNODE INSERTED AT REAR OF THE QUEUE\n");	
	}
	else
	{
		temp = head;
		while(temp->next != NULL)
		{
			temp = temp->next;
		}
		temp->next = ptr;
		ptr->next = NULL;
		printf("\nNODE INSERTED AT REAR OF THE QUEUE\n");
	}	
}
void dequeue()
{
	struct node *ptr;
	if(head == NULL)
	{
		printf("EMPTY LIST!!!");
	}
	else
	{
		ptr = head;
		head = ptr->next;
		free(ptr);
		printf("\nNODE DELETED FROM FRONT OF THE QUEUE\n");
	}	
}

//Display List
void display()
{
	struct node *ptr;
	ptr = head;
	if(ptr == NULL)
	{
		printf("EMPTY LIST!!!INSERT FEW ELEMENTS!!");
	}
	else
	{
		printf("\n\nLIST-->");
		while(ptr != NULL)
		{
			printf("\t%d",ptr->data);
			ptr = ptr->next;
		}
	}
}

//sort Linked list in ascending order
void sort()
{
	struct node *ptr = head;
	struct node *temp = NULL;
	int i;
	
	if(head == NULL)
	{
		return;
	}
	else
	{
		while(ptr != NULL)
		{
			temp = ptr->next;
			while(temp != NULL)
			{
				if(ptr->data >temp->data)
				{
					i = ptr->data;
					ptr->data = temp->data;
					temp->data = i;
				}
				temp = temp->next;
			}
			ptr = ptr->next;
		}
	}
}

//reverse Linked List
void reverse()
{
	struct node *prev = NULL;
	struct node *next = NULL;
	struct node *ptr = head;
	while(ptr != NULL)
	{
		next = ptr->next;
		ptr->next = prev;
		prev = ptr;
		ptr = next;
	}
	head = prev;
}

//create list
struct node *create_list(struct node *head)
{
	struct node *ptr,*temp;
	int i,n,new_data;
	
    printf("\nEnter the number of nodes : ");
    scanf("%d",&n);
	head = NULL;
	if(n == 0)
	{
		return head;
	}
	for(i=1;i<=n;i++)
	{
		ptr = (struct node *)malloc(sizeof(struct node));	
		printf("Enter the element to be inserted : ");
		scanf("%d",&new_data);
		ptr->data = new_data;
		if(head == NULL)
		{
			ptr->next = NULL;
			head = ptr;
		}
		else
		{
			temp = head;
			while(temp->next != NULL)
			{
				temp = temp->next;
			}
			temp->next = ptr;
			ptr->next = NULL;
		}	    
	}
	return head;
}


//concatenate two lists
struct node *concatenate(struct node *head, struct node *head2)
{
	struct node *ptr;
	if(head == NULL)
	{
		head = head2;
		return head;
	}
	if(head2 == NULL)
	{
		return head;
	}
	ptr = head;
	while(ptr->next != NULL)
	{
		ptr = ptr->next;
	}
	ptr->next = head2;
	return head;
}



int main()
{
	int choice = 0;
	while(1)
	{
		printf("\n\n*****************MENU****************\n");
		printf("Choose an option from the list:");
		printf("\n-----STACK OPERATIONS-----\n[1]PUSH\n[2]POP");
		printf("\n-----QUEUE OPERATIONS-----\n[3]ENQUEUE\n[4]DEQUEUE");
		printf("\n--------------------------");
		printf("\n[5]DISPLAY\n[6]SORT\n[7]REVERSE\n[8]CONCATENATION\n[9]EXIT\n");
		printf("\nEnter your choice:");
		scanf("%d",&choice);
		switch(choice)
		{
			case 1: push();
					break;
			case 2: pop();
					break;		
			case 3: enqueue();
					break;		
			case 4: dequeue();
					break;
			case 5: display();
					break;
			case 6: sort();
					printf("\nSorted List::");
					display();
					break;
			case 7: reverse();
					printf("\nReversed List::");
					display();
					break;				
			case 8: printf("\nCreate a Second list-->");
					head2 = create_list(head2);
					printf("\nList1:");
					display();
					struct node *ptr;
					ptr = head2;
					if(ptr == NULL)
					{
						printf("LIST2 IS EMPTY!!!");
					}
					else
					{
						printf("\n\nLIST2-->");
						while(ptr != NULL)
						{
							printf("\t%d",ptr->data);
							ptr = ptr->next;
						}
					}
					head = concatenate(head,head2);
					printf("\n\nConcatenated List:");
					display();
					break;
			case 9:	exit(1);
			default:
				printf("\nINVALID CHOICE!!!\n");								
		}
	}
}
