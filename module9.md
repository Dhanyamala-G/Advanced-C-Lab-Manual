# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
#include <stdio.h>

int stack[100];
int top = -1;

void push(int value) {
    if (top == 100 - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("Pushed %d onto the stack.\n", value);
    }
}

void pop() {
    if (top == -1) {
        printf("Stack Underflow! Nothing to pop.\n");
    } else {
        printf("Popped %d from the stack.\n", stack[top]);
        top--;
    }
}

void display() {
    if (top == -1) {
        printf("The stack is empty.\n");
    } else {
        printf("Current Stack (Top to Bottom):\n");
        for (int i = top; i >= 0; i--) {
            printf("| %d |\n", stack[i]);
        }
        printf("-----\n\n");
    }
}

int main() {
    printf("--- Initializing Stack Operations ---\n\n");

    push(10);
    push(20);
    push(30);
    display(); // Display stack after 3 pushes

    pop();
    display(); // Display stack after 1 pop

    push(40);
    push(50);
    push(60);  // This will trigger overflow if it exceeds MAX
    display(); // Final stack display

    return 0;
}
```
Output:

<img width="313" height="613" alt="image" src="https://github.com/user-attachments/assets/5e7e99b8-5b8c-493d-9002-fe5511157a5b" />



Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>

float stack[100];
int top = -1;

void push(float element) {
    if (top >= 100 - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", element);
    } else {
        top++;
        stack[top] = element;
        printf("Successfully pushed %.2f onto the stack.\n", element);
    }
}

void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
        return;
    }
    printf("Current Stack: ");
    for (int i = 0; i <= top; i++) {
        printf("%.2f ", stack[i]);
    }
    printf("\n");
}

int main() {
    printf("--- Stack Push Operation Demonstration ---\n\n");

    push(10.5);
    push(20.3);
    push(30.8);
    
    display();

    push(40.1);
    push(50.6);
    
    push(60.0); 

    display();

    return 0;
}
```
Output:

<img width="428" height="282" alt="image" src="https://github.com/user-attachments/assets/fe82c7d3-5352-4344-b1b8-8d9ed1d09a66" />




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>

int queue[50];
int front = -1;
int rear = -1;
int i;

void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are: ");
        // Using the global iteration variable 'i'
        for (i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

void enqueue(int value) {
    if (rear == 50 - 1) {
        printf("Queue Overflow! Cannot insert %d\n", value);
    } else {
        if (front == -1) {
            front = 0;
        }
        rear++;
        queue[rear] = value;
        printf("Inserted %d into the queue.\n", value);
    }
}

int main() {
    
    printf("--- Queue Operations ---\n");

    display(); // Displaying empty queue
    
    enqueue(10);
    enqueue(20);
    enqueue(30);
    
    display(); // Displaying queue after insertions
    
    enqueue(40);
    enqueue(50);
    
    display(); // Displaying full queue
    
    return 0;
}
```

Output:

<img width="330" height="242" alt="image" src="https://github.com/user-attachments/assets/47b9d7e3-365b-44c3-9e24-393f2d04642a" />


Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
#include <stdio.h>


float queue[50];
int size;
int front;
int rear;

void enqueue(float element) {
    if (rear == 50 - 1) {
        printf("Queue Overflow! Cannot insert %0.2f\n", element);
        return;
    }
    
    if (front == -1) {
        front = 0;
    }
    
    rear++;
    queue[rear] = element;
    printf("Successfully inserted %0.2f into the queue.\n", element);
}

int main() {
    front = -1;
    rear = -1;
    size = 5; 

    printf("Queue initialized with size %d.\n\n", size);

    enqueue(10.5f);
    enqueue(20.35f);
    enqueue(30.7f);
    enqueue(40.1f);
    enqueue(50.9f);
    
    enqueue(60.0f);

    return 0;
}
```

Output:

<img width="357" height="241" alt="image" src="https://github.com/user-attachments/assets/83ec1d22-0320-40ff-bd7a-2a3005ba13ea" />

Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>


int queue[50];
int front = -1;
int rear = -1;

void dequeue() {
    if (front == -1) {
        printf("Queue Underflow! The queue is empty, no elements to delete.\n");
        return;
    }

    int deleted_element = queue[front];
    printf("Deleted element: %d\n", deleted_element);
    
    front++;

    if (front > rear) {
        front = -1;
        rear = -1;
    }
}
int main() {
    dequeue();
    return 0;
}
```
Output:

<img width="482" height="102" alt="image" src="https://github.com/user-attachments/assets/e24a3912-5bcd-489e-a430-9af605559e57" />


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
