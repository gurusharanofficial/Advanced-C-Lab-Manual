

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
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
```python
struct Node   
{  
char data[10];  
struct Node *next;  
}*head;  
void display()  
{ 
    struct Node *ptr;
    ptr=head;
    while(ptr!=NULL)
   {
        printf("%s\n",ptr->data);
        ptr=ptr->next;
   } 
}
```
Output:









![image](https://github.com/user-attachments/assets/dfcdefc2-8aa2-47a3-862b-550efde692ce)

Result:


Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:
```python
struct Node   
{  
int data;  
struct Node *next;  
}*head;  
void pop()  
{ 
    struct Node *ptr;
    if(head==NULL)
    {
        printf("stack is empty\n");
    }
    else
    {
        ptr=head;
        head=ptr->next;
        free(ptr);
    }
}
```
Output:









![image](https://github.com/user-attachments/assets/11f34c24-22d0-460f-b1dd-bab0283dbd69)

Result:


Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:
```python
struct Node
{
   float data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void display()
{
    if(front==NULL)    
    {        
        printf("queue is empty\n");    
    }    
    else    
    {    
        printf("Queue elements:\n");
        struct Node *ptr;
        ptr=front;
        while(ptr!=NULL)
        {  
            printf("%.3f\n", ptr->data);
            ptr = ptr->next;
        }    
    }
}
```
Output:








![image](https://github.com/user-attachments/assets/3cfdfb83-258a-4b26-baf5-16efc62179d6)

Result:


Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

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
```python
struct Node
{
   double data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void enqueue(double data)
{
   struct Node *newNode;
   newNode=(struct Node*)malloc(sizeof(struct Node));
   newNode->data=data;
   newNode->next=NULL;
   if(front==NULL)
   {
      front=rear=newNode;
   }
   else
   {
      rear->next=newNode;
      rear=newNode;
   }
}

```
Output:









![image](https://github.com/user-attachments/assets/51adcb10-c8ec-4182-a629-971635f97c2f)

Result:


Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:
The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:
```python
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node* next;
};
struct Queue {
    struct Node* front;
    struct Node* rear;
};
struct Node* newNode(int data) {
    struct Node* temp = (struct Node*)malloc(sizeof(struct Node));
    temp->data = data;
    temp->next = NULL;
    return temp;
}
struct Queue* createQueue() {
    struct Queue* q = (struct Queue*)malloc(sizeof(struct Queue));
    q->front = q->rear = NULL;
    return q;
}
void enqueue(struct Queue* q, int data) {
    struct Node* temp = newNode(data);
    if (q->rear == NULL) {
        q->front = q->rear = temp;
        return;
    }
    q->rear->next = temp;
    q->rear = temp;
}
int peek(struct Queue* q) {
    if (q->front == NULL) {
        printf("Queue is empty!\n");
        return -1;
    }
    return q->front->data;
}
int main() {
    struct Queue* q = createQueue();
    enqueue(q, 10);
    enqueue(q, 20);
    enqueue(q, 30);
    printf("Peek element is: %d\n", peek(q));
    return 0;
}
```
Output:













![image](https://github.com/user-attachments/assets/91840753-fb13-4300-9174-e2613f877ede)

Result:


Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


