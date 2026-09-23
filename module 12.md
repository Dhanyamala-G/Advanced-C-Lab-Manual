

# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
struct Node   
{  
char data[100];  
struct Node *next;  
}*head;  

void display()  
{  
    struct Node *temp=head;
    while(temp!=NULL){
        printf("%s\n",temp->data);
        temp=temp->next;
    }
    
}
```
Output:

<img width="375" height="342" alt="image" src="https://github.com/user-attachments/assets/36617298-cb11-4572-9042-ab0637b7f512" />


Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
struct Node   
{  
float data;  
struct Node *next;  
}*head;  

void pop()  
{ 
    if(head!=NULL){
        struct Node *temp=head;
        head=head->next;
        free(temp);
    }
    else
        printf("stack is empty");
}
```
Output:

<img width="843" height="450" alt="image" src="https://github.com/user-attachments/assets/5d2175e4-23e3-4e49-8fa4-62973fbe6480" />



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
               struct Node
               {
               char data;
               struct Node *next;
               }*front=NULL,*rear=NULL; 
               void display()
               {
               if(front==NULL)
               {
               printf("queue is empty");
               }
               else
               {
               printf("queue elements:\n"); 
               while(front!=NULL)
               {
               printf("%c\n",front->data); 
               front=front->next;
               }
               }
               }
```
Output:

<img width="399" height="423" alt="image" src="https://github.com/user-attachments/assets/64304734-6944-40fb-9b06-161e52643285" />

Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

```
          struct Node
          {
          int data;
          struct Node *next;
          }*front=NULL,*rear=NULL; 
          void enqueue(int data)
          {
          struct Node *p=(struct Node*)malloc(sizeof(struct Node)); 
          p->data=data;
          p->next=NULL; 
          if(front==NULL)
          {
          front=rear=p;
          }
          else
          {
          rear->next=p; 
          rear=p;
          }
          }
```
Output:

<img width="406" height="427" alt="image" src="https://github.com/user-attachments/assets/aaa526c2-04d7-435c-8b0a-93f50cfb6254" />

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
          struct Node
          {
             char data;
             struct Node *next;
          }*front=NULL,*rear=NULL;
          void peek()
          {
          printf("%c",front->data);
          }
```
Output:

<img width="945" height="668" alt="image" src="https://github.com/user-attachments/assets/3e178789-9c86-4966-9e2c-9aadaebc7722" />



Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


