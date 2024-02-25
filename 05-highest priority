#include <stdio.h>
#include <stdlib.h>
struct Process {
    int pid;
    int burst_time;
    int priority;
};
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
int main() {
    int n;
    printf("Enter Number of Processes: ");
    scanf("%d", &n);
    int burst[n], priority[n], index[n];
    for (int i = 0; i < n; i++) {
        printf("Enter Burst Time and Priority Value for Process %d: ", i + 1);
        scanf("%d %d", &burst[i], &priority[i]);
        index[i] = i + 1;
    }
    for (int i = 0; i < n; i++) {
        int highest_priority = priority[i];
        int highest_priority_index = i;

        for (int j = i; j < n; j++) {
            if (priority[j] > highest_priority) {
                highest_priority = priority[j];
                highest_priority_index = j;
            }
        }
        swap(&priority[i], &priority[highest_priority_index]);
        swap(&burst[i], &burst[highest_priority_index]);
        swap(&index[i], &index[highest_priority_index]);
    }
    int t = 0; // Starting time of each process
    printf("Order of process execution:\n");
    for (int i = 0; i < n; i++) {
        printf("P%d is executed from %d to %d\n", index[i], t, t + burst[i]);
        t += burst[i];
    }
    printf("\nProcess ID\tBurst Time\tWait Time\tTurnaround Time\n");
    for (int i = 0; i < n; i++) {
        printf("%d\t\t%d\t\t%d\t\t%d\n", index[i], burst[i], t - burst[i], t);
    }
    return 0;
}
