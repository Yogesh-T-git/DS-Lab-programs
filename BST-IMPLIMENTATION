#include<stdlib.h>
#include<stdio.h>

struct node 
{
	int key;
	struct node *left;
	struct node *right;
};
struct node *root; 

struct node *create(int data)
{
	struct node *temp;
	temp = (struct node*)malloc(sizeof(struct node));
	temp->key = data;
	temp->left = temp->right = NULL;
	return temp;
}

void insert(struct node *root,struct node *temp)
{
	if(temp->key < root->key)
	{
		if(root->left != NULL)
		{
			insert(root->left,temp);
		}
		else
		{
			root->left = temp;
		}
	}
	if(temp->key > root->key)
	{
		if(root->right != NULL)
		{
			insert(root->right,temp);
		}
		else
		{
			root->right = temp;
		}
	}
}

void display(struct node *root)
{
	if(root != NULL)
	{
		display(root->left);
		printf("%d\t",root->key);
		display(root->right);
	}
}

void inorder(struct node *root)
{
	if(root != NULL)
	{
		inorder(root->left);
		printf("%d\t",root->key);
		inorder(root->right);
	}
}
void preorder(struct node *root)
{
	if(root != NULL)
	{
		printf("%d\t",root->key);
		preorder(root->left);
		preorder(root->right);
	}
}
void postorder(struct node *root)
{
	if(root != NULL)
	{
		postorder(root->left);
		postorder(root->right);
		printf("%d\t",root->key);
	}
}
int main()
{
	char ch;
	struct node *temp;
	root = NULL;
	int choice = 0;
	int data;
	
	while(1)
	{
		printf("\n\n*****************MENU****************\n");
		printf("Choose an option from the list:");
		printf("\n[1]CREATE A TREE\n[2]INORDER TRAVERSAL\n[3]PREORDER TRAVERSAL\n[4]POSTORDER TRAVERSAL\n[5]DISPLAY\n[6]EXIT\n");
		printf("\nEnter your choice:");
		scanf("%d",&choice);
		switch(choice)
		{
			case 1: do{
						printf("\nEnter the value:");
						scanf("%d",&data);
						temp = create(data);
						if(root == NULL)
						{
							root = temp;
						}
						else
						{
							insert(root,temp);
						}
						printf("\nDo you Want to Enter more(Y/N)? ");
						getchar();
						scanf("%c",&ch);
					}while(ch=='y'||ch=='Y');
					break;
			case 2: printf("\nINORDER TRAVERSAL-->\t");
					inorder(root);
					break;
			
			case 3: printf("\nPREORDER TRAVERSAL-->\t");
					preorder(root);
					break;
			
			case 4: printf("\nPOSTORDER TRAVERSAL-->\t");
					postorder(root);
					break;
					
			case 5: display(root);
					break;
					
			case 6: exit(1);
			default:
				printf("\nINVALID CHOICE!!!\n");								
		}
	}
	return 0;
}
