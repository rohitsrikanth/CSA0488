#include <stdio.h>
#include <stdlib.h>
struct Process {
    int pid;
    int arrival_time;
    int burst_time;
};
void findWaitingTime(struct Process processes[], int n, int wt[]) {
    wt[0] = 0;
    for (int i = 1; i < n; i++)
        wt[i] = processes[i - 1].burst_time + wt[i - 1];
}
void findTurnAroundTime(struct Process processes[], int n, int wt[], int tat[]) {
    for (int i = 0; i < n; i++)
        tat[i] = processes[i].burst_time + wt[i];
}
void findAvgTime(struct Process processes[], int n) {
    int wt[n], tat[n], total_wt = 0, total_tat = 0;
    findWaitingTime(processes, n, wt);
    findTurnAroundTime(processes, n, wt, tat);
    printf("Processes\tBurst time\tWaiting time\tTurnaround time\n");
    for (int i = 0; i < n; i++) {
        total_wt += wt[i];
        total_tat += tat[i];
        printf("%d\t\t%d\t\t%d\t\t%d\n", processes[i].pid, processes[i].burst_time, wt[i], tat[i]);
    }
    float avg_wt = (float)total_wt / n;
    float avg_tat = (float)total_tat / n;
    printf("\nAverage waiting time = %.2f\n", avg_wt);
    printf("Average turnaround time = %.2f\n", avg_tat);
}
int main() {
    int n = 5; 
    struct Process processes[] = {
        {1, 2, 6},
        {2, 5, 2},
        {3, 1, 8},
        {4, 0, 3},
        {5, 4, 4}
    };
    findAvgTime(processes, n);
    return 0;
}
