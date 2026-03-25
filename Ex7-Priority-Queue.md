# Ex7 Priority Queue
## DATE:
## AIM:
To formulate the C code to display the elements of the priority queue after insertion and deletion operation.

## Algorithm
1.Start the program
2.Initialize two arrays: one for elements and one for priority
3.Insert elements along with their priorities
4.Arrange elements based on priority (higher priority first)
5.Perform deletion (remove highest priority element)
6.Display queue elements after insertion and deletion
7.Stop  

## Program:
```
/*
Program to display the elements of the priority queue
after insertion and deletion operation
Developed by: SANGAVI S
RegisterNumber: 212222230130
*/

#include<stdio.h>

#define MAX 5

int data[MAX], priority[MAX];
int size = 0;

void insert(int value, int pr)
{
    int i = size - 1;

    while(i >= 0 && priority[i] < pr)
    {
        data[i + 1] = data[i];
        priority[i + 1] = priority[i];
        i--;
    }

    data[i + 1] = value;
    priority[i + 1] = pr;
    size++;
}

void delete()
{
    if(size == 0)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Deleted element: %d\n", data[0]);

    for(int i = 0; i < size - 1; i++)
    {
        data[i] = data[i + 1];
        priority[i] = priority[i + 1];
    }

    size--;
}

void display()
{
    if(size == 0)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Priority Queue:\n");
    for(int i = 0; i < size; i++)
    {
        printf("Value = %d Priority = %d\n", data[i], priority[i]);
    }
}

int main()
{
    insert(10, 2);
    insert(20, 5);
    insert(30, 1);
    insert(40, 4);

    printf("After insertion:\n");
    display();

    printf("\nAfter deletion:\n");
    delete();

    display();

    return 0;
}
```

## Output:

<img width="445" height="546" alt="image" src="https://github.com/user-attachments/assets/7c0c5f11-340e-48c7-8069-197e7ad83ba7" />


## Result:
Thus, the C program to display the elements of the priority queue after insertion and deletion operation is implemented successfully
