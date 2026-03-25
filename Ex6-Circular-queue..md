# Ex6 Dequeue Elements from Circular Queue
## DATE:
## AIM:
To write a C program to delete three elements from the filled circular queue.

## Algorithm
1.Start the program
2.Initialize circular queue with front = -1 and rear = -1
3.Insert elements into the circular queue (enqueue)
4.Perform dequeue operation three times
5.Display the deleted elements
6.Stop the program   

## Program:
```
/*
Program to delete three elements from the filled circular queue
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>

#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

void enqueue(int x)
{
    if((rear + 1) % MAX == front)
    {
        printf("Queue Overflow\n");
        return;
    }

    if(front == -1)
        front = 0;

    rear = (rear + 1) % MAX;
    queue[rear] = x;
}

void dequeue()
{
    if(front == -1)
    {
        printf("Queue Underflow\n");
        return;
    }

    printf("Deleted element: %d\n", queue[front]);

    if(front == rear)
    {
        front = rear = -1;
    }
    else
    {
        front = (front + 1) % MAX;
    }
}

void display()
{
    int i;

    if(front == -1)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements: ");
    i = front;

    while(1)
    {
        printf("%d ", queue[i]);

        if(i == rear)
            break;

        i = (i + 1) % MAX;
    }
    printf("\n");
}

int main()
{
    // Fill the queue
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);

    display();

    // Delete three elements
    printf("\nDeleting three elements:\n");
    dequeue();
    dequeue();
    dequeue();

    display();

    return 0;
}
```

## Output:


<img width="427" height="358" alt="image" src="https://github.com/user-attachments/assets/5a714c92-b412-453d-9cf5-52072aaf038f" />

## Result:
Thus, the C program to delete three elements from the filled circular queue is implemented successfully.
