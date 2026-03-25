# Ex8 Deque
## DATE:
## AIM:
To write a C function to count the number of elements present in the deque.

## Algorithm
1.Start the program
2.Initialize deque with front = -1 and rear = -1
3.Insert elements into the deque
4.If deque is empty → count = 0
5.Else calculate count using (rear - front + 1)
6.Display number of elements
7.Stop   

## Program:
```
/*
Program to count the number of elements present in the deque
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>

#define MAX 5

int deque[MAX];
int front = -1, rear = -1;

void insertRear(int x)
{
    if(rear == MAX - 1)
    {
        printf("Deque Overflow\n");
        return;
    }

    if(front == -1)
        front = 0;

    deque[++rear] = x;
}

int count()
{
    if(front == -1)
        return 0;
    else
        return (rear - front + 1);
}

void display()
{
    if(front == -1)
    {
        printf("Deque is empty\n");
        return;
    }

    printf("Deque elements: ");
    for(int i = front; i <= rear; i++)
    {
        printf("%d ", deque[i]);
    }
    printf("\n");
}

int main()
{
    insertRear(10);
    insertRear(20);
    insertRear(30);
    insertRear(40);

    display();

    printf("Number of elements in deque = %d", count());

    return 0;
}
```

## Output:

<img width="461" height="193" alt="image" src="https://github.com/user-attachments/assets/5e9d47de-2d63-4df1-a8d5-b706c4246e1b" />


## Result:
Thus, the C code to count the number of elements present in the deque is implemented successfully.
