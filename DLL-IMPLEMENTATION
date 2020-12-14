#include<stdio.h>
#include<stdlib.h>

struct node
{
	struct node *prev;
	int data;
	struct node *next;
};
struct node *head;
struct node *last;

//Create DLL
void create_list() 
{
	struct node *ptr;
	int i,n,new_data;
	printf("\nEnter the number of nodes:");
	scanf("%d",&n);
	
	if(n>=1)
	{
		head = (struct node *)malloc(sizeof(struct node));
		if(head != NULL)
		{
			printf("\nEnter the value to be inserted for Node 1 :\t");
			scanf("%d",&new_data);
			
			head->data = new_data;
			head->prev = NULL;
			head->next = NULL;
			
			last = head;
			
			for(i=2;i<=n;i++)
			{
				ptr = (struct node *)malloc(sizeof(struct node));
				
				if(ptr != NULL)
				{
					printf("Enter the value to be inserted for Node %d :\t",i);
					scanf("%d",&new_data);
					
					ptr->data = new_data;
					ptr->prev = last;
					ptr->next = NULL;
					
					last->next = ptr;
					last = ptr;
				}
			}
			printf("\n\nLinked List Created!!");
		}
	}
	else
	{
		printf("\n\nInvalid!!Enter valid number of nodes!!");
	}
}

//display
void display_list()
{
	struct node *ptr = head;
	if(ptr == NULL)
	{
		printf("\nList is Empty!!");
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

//Insert at the left of a given node
void insert_left()
{
	int i,pos,new_data;
	struct node *ptr,*temp;
	ptr = (struct node *)malloc(sizeof(struct node));
	
	printf("\nEnter the Node to insert the value: ");
	scanf("%d",&pos);
	printf("\nEnter the value to be inserted: ");
	scanf("%d",&new_data);
	
	ptr->data = new_data;
	
	if(head == NULL)
	{
		printf("\nList is empty!!");
	}
	else
	{
		temp = head;
		i=1;
		while(i<pos-1 && temp!=NULL)
		{
			temp = temp->next;
			i++;
		}
		if(pos == 1)
		{
			ptr->next = head;
			ptr->prev = NULL;
			head->prev = ptr;
			head = ptr;
			printf("\n\nNode Inserted at %d position!!",pos);
		}
		else if(temp == last)
		{
			ptr->next = NULL;
			ptr->prev = last;
			last->next = ptr;
			last = ptr;
			printf("\n\nNode Inserted at %d position!!",pos);
		}
		else if(temp != NULL)
		{
			ptr->next = temp->next;
			ptr->prev = temp;
			if(temp->next != NULL)
			{
				temp->next->prev = ptr;
			}
			temp->next = ptr;
			printf("\n\nNode Inserted at %d position!!",pos);
		}
		else
		{
			printf("\n\nInvalid Position!!");
		}
	}
}

//Delete node by Value
void delete()
{
  struct node* temp = head;
  struct node* ptr = (struct node*) malloc(sizeof(struct node));
  int val;
  printf("\nEnter the Value to be deleted: ");
  scanf("%d",&val);

  if(temp->next == NULL)
  {
    head = NULL;
    free(temp);
    printf("\n\nValue %d, deleted \n",val);
    return;
  }
  
  if(temp!=NULL && temp->data == val)
  {
    head = temp->next; 
    head->prev = NULL;
    free(temp);
    printf("\n\nValue %d, deleted ",val);
	return;
  }
  while(temp!=NULL && temp->data != val) 
  { 
    ptr = temp;
    temp = temp->next;
  }
  if(temp==NULL)
  {
    printf("\n\nValue not found");
    return;
  }
  ptr->next = temp->next;

  if(temp->next == NULL)
  {
    printf("\n\nValue %d, deleted \n",val);
    free(temp);
    return;
  }

  struct node* temp2 = (struct node*) malloc(sizeof(struct node));
  temp2 = temp->next;
  temp2->prev = ptr;
  free(temp);
  printf("Value %d, deleted \n",val);
}

int main()
{
	int choice = 0;
	while(1)
	{
		printf("\n\n*****************MENU****************\n");
		printf("Choose an option from the list:");
		printf("\n[1]CREATE A LIST\n[2]INSERT TO THE LEFT OF A NODE\n[3]DELETE NODE \n[4]DISPLAY\n[5]EXIT\n");
		printf("\nEnter your choice:");
		scanf("%d",&choice);
		switch(choice)
		{
			case 1: create_list();
					break;
			case 2: insert_left();
					break;
			case 3: delete();
					break;					
			case 4: display_list();
					break;
			case 5: exit(1);
			default:
				printf("\nINVALID CHOICE!!!\n");								
		}
	}
}
