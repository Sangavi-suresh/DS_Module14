# Ex9 Applications of Queue - SJF
## DATE:
## AIM:
To incorporate the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm.
## Algorithm
1.Start the program
2.Read number of processes n
3.Read burst time for each process
4.Sort processes in ascending order of burst time (SJF)
5.Calculate waiting time:
6.First process → waiting time = 0
7.Others → sum of previous burst times
8.Calculate total waiting time
9.Calculate average waiting time
10.Display results
11.Stop   

## Program:
```
/*
Program to find the Total Waiting Time and Average Waiting Time
in Shortest Job First scheduling algorithm.
Developed by: SANGAVI S
RegisterNumber:  212222230130
*/

#include<stdio.h>

int main()
{
    int n, i, j;
    int bt[10], wt[10];
    float total = 0, avg;

    printf("Enter number of processes: ");
    scanf("%d", &n);

    printf("Enter burst times:\n");
    for(i = 0; i < n; i++)
    {
        scanf("%d", &bt[i]);
    }

    // Sorting burst times (SJF)
    for(i = 0; i < n; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(bt[i] > bt[j])
            {
                int temp = bt[i];
                bt[i] = bt[j];
                bt[j] = temp;
            }
        }
    }

    wt[0] = 0;

    for(i = 1; i < n; i++)
    {
        wt[i] = wt[i - 1] + bt[i - 1];
    }

    printf("\nProcess\tBurst Time\tWaiting Time\n");

    for(i = 0; i < n; i++)
    {
        printf("P%d\t%d\t\t%d\n", i+1, bt[i], wt[i]);
        total += wt[i];
    }

    avg = total / n;

    printf("\nTotal Waiting Time = %.2f", total);
    printf("\nAverage Waiting Time = %.2f", avg);

    return 0;
}
```

## Output:

<img width="462" height="437" alt="image" src="https://github.com/user-attachments/assets/78255bb1-e6c9-4673-b0fc-ae57b41a57ea" />


## Result:
Thus, the code to calculate the Total Waiting Time and Average Waiting Time in Shortest Job First scheduling algorithm is implemented successfully.
